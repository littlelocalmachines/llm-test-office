# Release 1.1.1.1 — common invoice test, group 1

Video: [youtube.com/watch?v=BdjfpzVzEiw](https://www.youtube.com/watch?v=BdjfpzVzEiw)

Four small local models under 2 billion parameters — **MiniCPM 5 1B, Gemma 3 1B, Llama 3.2 1B Instruct, SmolLM2 1.7B Instruct** — on the same 200 synthetic invoices, clean and with simulated scanner noise, against a rule-based program with no model.

**Finding:** on clean invoices the rule-based program reads the five basic fields of 142 invoices out of 200. With scanner noise it drops to 55; MiniCPM 5 1B and SmolLM2 1.7B both keep 91.

## What was measured

- **Tier I:** five basic fields of an invoice. **Tier II:** the full invoice, every line item.
- **Strict:** every requested field right *and* exactly the requested JSON. **Flexible:** the same after stripping code fences and small format slips.
- Every model: the same prompt, temperature 0, thinking off, at most 2048 output tokens, the same invoices (generator seed 42). No model-specific software.
- **Early stop:** if the first 30 answers all fail (strict and flexible), the cell stops at 30. 0/30 does not say what the other 170 would have been.

## Numbers in the video

| Model | Tier I clean | Tier I noisy | Tier II clean | Tier II noisy |
|---|---|---|---|---|
| Rule-based baseline (no model) | 142 | 55 | 142 | 6 |
| MiniCPM 5 1B | 147 | 91 | 0 | 0/30 (stopped) |
| Gemma 3 1B | 0 (flexible 140) | 0 (flexible 103) | 0 (flexible 1) | 0/30 (stopped) |
| Llama 3.2 1B Instruct | 0 (flexible 3) | 0/30 (stopped) | 0 | 0/30 (stopped) |
| SmolLM2 1.7B Instruct | 127 | 91 | 4 | 0/30 (stopped) |

Out of 200 invoices. Full tables, including speed and running several requests at once: [`RESULTS.md`](RESULTS.md) (generated from the data in `package.zip`).

- **Gemma 3 1B** reads the invoices but wraps its JSON in markdown code fences, so it fails the strict rule: 0 strict, 140 flexible on clean invoices.
- **Llama 3.2 1B Instruct** returns numbers as text strings instead of JSON numbers, which fails both rules.
- **SmolLM2 1.7B** is the only model of the group that completed any full invoice (Tier II): 4 out of 200.

## A second clean run (r2, 30.10.2026)

The clean numbers in the video come from a run that kept the strict verdict of every invoice but **not the raw answers**. So that the clean answers can be checked too, we ran the same engine on the same invoices again and kept every answer. The video numbers do not change; r2 is published next to them, with an invoice-by-invoice comparison in `RESULTS.md`.

| Model | Tier I clean, video | Tier I clean, r2 | Same strict verdict, invoice by invoice |
|---|---|---|---|
| MiniCPM 5 1B | 147 | 147 | 186/200 |
| Gemma 3 1B | 0 | 0 | 200/200 |
| Llama 3.2 1B Instruct | 0 | 2 | 198/200 |
| SmolLM2 1.7B Instruct | 127 | 125 | 190/200 |

Between the two runs the LM Studio version (0.4.26 → 0.4.27) and the laptop's power mode changed. We did **not** separate which of the two changed the verdicts that changed. For Gemma 3 1B in r2, the model file used was not recorded unambiguously (two local files with the same quantization matched); see `MODELS.json`.

## Files

| File | What it is |
|---|---|
| `RESULTS.md`, `results.csv` | Every number, computed from the data |
| `MODELS.json` | Model files per run: file name, size, SHA-256, LM Studio version |
| `HARDWARE.json` | ASUS ProArt PX13 (HN7306), AMD Ryzen AI Max+ 395, 128 GB unified memory |
| `FACTS.json` | Every number said in the video, as data |
| `TRANSCRIPT_TR.md`, `seal-tr/` | Turkish transcript and fact list, sealed 2026-10-21 before translation and voice-over |
| `package.zip` | Engine (`llm_test_office/`), raw answers (`data/`), baseline. Password `llm-test-office` |
| `RERUN.md` | How to re-score the answers and re-run a model yourself |
| `STERILIZATION.md` | Scan for personal or internal information |
| `MANIFEST.sha256`, `damga/`, `MANIFEST.sha256.sig` | Seal of this whole folder |

## Not in this release

Image engines, EDI engines, real-document engines, the load-test runner and model weights (download them from Hugging Face; `MODELS.json` gives the SHA-256 to compare). The load test (several requests at once) is published as results only.
