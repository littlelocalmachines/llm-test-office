# Release 1.1.1.2 — common invoice test, group 2

Video: not out yet; the link is added here when it is.

Three small local models — **LFM2 1.2B, LFM2.5 1.2B Instruct, Qwen3 1.7B** — on the same 200 synthetic invoices as group 1, clean and with simulated scanner noise, against a rule-based program with no model. Same engine, same prompt, same rules as [1.1.1.1](../1.1.1.1/).

**Finding:** two versions of the same size from the same maker do not perform alike. On clean invoices LFM2 1.2B reads the five basic fields of 77 invoices out of 200, LFM2.5 1.2B Instruct 161. With scanner noise the rule-based program drops from 142 to 55; LFM2.5 keeps 103.

## Numbers in the video

| Model | Tier I clean | Tier I noisy | Tier II clean | Tier II noisy |
|---|---|---|---|---|
| Rule-based baseline (no model) | 142 | 55 | 142 | 6 |
| LFM2 1.2B | 77 (flexible 78) | 56 | 0 | 0/30 (stopped) |
| LFM2.5 1.2B Instruct | 161 | 103 | 12 | 0/30 (stopped) |
| Qwen3 1.7B | 99 (flexible 107) | 68 (flexible 69) | 5 | 0/30 (stopped) |

Out of 200 invoices. Tier I = five basic fields, Tier II = full invoice. Strict = every field right and exactly the requested JSON; flexible = after stripping code fences and small format slips. Early stop: if the first 30 answers all fail, the cell stops at 30. Full tables, including speed and running several requests at once: [`RESULTS.md`](RESULTS.md).

## A second clean run (r2, 30.10.2026)

The clean numbers in the video come from a run that kept the strict verdict of every invoice but **not the raw answers**. We ran the same engine on the same invoices again and kept every answer. The video numbers do not change; r2 is published next to them.

| Model | Tier I clean, video | Tier I clean, r2 | Same strict verdict, invoice by invoice |
|---|---|---|---|
| LFM2 1.2B | 77 | 79 | 158/200 |
| LFM2.5 1.2B Instruct | 161 | 160 | 199/200 |
| Qwen3 1.7B | 99 | 90 | 143/200 |

The totals moved little for LFM2, but 42 of its 200 invoices changed verdict in both directions. Qwen3 1.7B dropped from 99 to 90, with 57 invoices changing verdict. Between the two runs the LM Studio version (0.4.26 → 0.4.27) and the laptop's power mode changed; we did **not** separate which of the two caused these changes. Same model file in all recorded runs for LFM2 and Qwen3 (`MODELS.json`); for LFM2.5 1.2B Instruct none of our runs recorded the file hash, so the exact file cannot be pinned.

## Files

| File | What it is |
|---|---|
| `RESULTS.md`, `results.csv` | Every number, computed from the data |
| `MODELS.json` | Model files per run: file name, size, SHA-256, LM Studio version |
| `HARDWARE.json` | ASUS ProArt PX13 (HN7306), AMD Ryzen AI Max+ 395, 128 GB unified memory |
| `FACTS.json` | Every number said in the video, as data |
| `package.zip` | Engine (`llm_test_office/`), raw answers (`data/`), baseline. Password `llm-test-office` |
| `RERUN.md` | How to re-score the answers and re-run a model yourself |
| `STERILIZATION.md` | Scan for personal or internal information |
| `MANIFEST.sha256`, `damga/`, `MANIFEST.sha256.sig` | Seal of this whole folder |

The public transcript of this video is added with the video.
