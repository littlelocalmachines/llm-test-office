# Re-run 1.1.1.2 yourself

Python ≥ 3.11 (tested on 3.11 and 3.14), no other package needed: the engine uses only the standard library. Commands below are for a shell opened in this release folder.

## 1. Open the package

```bash
7z x -pllm-test-office package.zip -opkg
cd pkg
```

`pkg/llm_test_office/` is the engine; `pkg/data/` holds the raw answers and verdicts:

| File | Contents |
|---|---|
| `data/noisy_rows.jsonl` | Noisy run, one row per invoice: expected answer, raw model answer, strict/flexible verdict, latency |
| `data/clean_r2_rows.jsonl` | Clean re-run (r2), same fields |
| `data/clean_v1_verdicts.jsonl` | Clean run used in the video: per-invoice strict verdicts (raw answers were not kept) |
| `data/load_runs.jsonl` | Several-requests-at-once runs: summaries |
| `data/baseline.json` | Rule-based baseline, per engine |

## 2. Re-score the published answers (no model needed)

```bash
python -m llm_test_office.yeniden_puanla data/noisy_rows.jsonl
python -m llm_test_office.yeniden_puanla data/clean_r2_rows.jsonl
```

Expected: for every model and engine the re-scored count equals the stored count, 0 rows disagree.

## 3. Rule-based baseline (no model)

```bash
python -m llm_test_office.kos --taban --motor to1_fatura
python -m llm_test_office.kos --taban --motor to1_fatura_gurultu
```

Expected: 142 and 55 out of 200 (Tier II: `to2_fatura` 142, `to2_fatura_gurultu` 6).

## 4. Run a model

Load the model in any OpenAI-compatible server (we used LM Studio; llama.cpp server, vLLM or Ollama's `/v1` also work), context 32,768, then:

```bash
python -m llm_test_office.kos --model <model id in your server> --motor to1_fatura --uc http://127.0.0.1:1234 --cikti my_rows.jsonl
python -m llm_test_office.yeniden_puanla my_rows.jsonl
```

Engines: `to1_fatura` (Tier I clean), `to2_fatura` (Tier II clean), `to1_fatura_gurultu`, `to2_fatura_gurultu` (noisy). The runner uses the same prompt, temperature 0, `reasoning_effort: "none"`, at most 2048 output tokens, the same 200 invoices and the same early stop as our runs. The output file is resumable.

**Use the same model file.** Compare the SHA-256 of your GGUF with `MODELS.json`:

| Model | GGUF file | SHA-256 |
|---|---|---|
| LFM2 1.2B | `LFM2-1.2B-Q4_K_M.gguf` | see `MODELS.json` |
| LFM2.5 1.2B Instruct | Q4_K_M (file hash not recorded in our runs) | — |
| Qwen3 1.7B | `Qwen3-1.7B-Q4_K_M.gguf` | see `MODELS.json` |

## What to expect

Temperature 0 is not full determinism: a different server version, GPU driver, hardware or power mode can change some answers (our own r2 re-run changed up to 57 of the 200 Tier I clean verdicts of a model; see `RESULTS.md`). The generated invoices and the scorer, however, are deterministic: steps 2 and 3 must match exactly.
