# Release 1.1.1.0-1 — interim video, Liquid AI LFM3 1.7B

Video: [youtu.be/98IgNmR5VDo](https://youtu.be/98IgNmR5VDo)

A new model from the LFM family — **LFM3 1.7B** (Liquid AI, released 23 October 2026) — on the same 200 synthetic invoices, with the same engine, prompt and rules as [1.1.1.1](../1.1.1.1/) and [1.1.1.2](../1.1.1.2/). Interim video: one new model, compared with the seven models published so far.

**Finding:** on the easy test (Tier I, five basic fields) LFM3 1.7B reads 156 of 200 invoices, close to LFM2.5 1.2B (161); the difference is not statistically significant (paired McNemar test, p = 0.64), nor is the difference from the rule-based program (142, p = 0.16). On the hard test (Tier II, the whole invoice with line items) it reads 85 of 200; LFM2.5 read 12 and none of the seven published models went above 12. The hard-test significance check was added after we saw the results, so we report it as a notable finding, not a verdict.

## Numbers in the video

| Model | Tier I clean | Tier II clean |
|---|---|---|
| Rule-based baseline (no model) | 142 | 142 |
| LFM2 1.2B (from 1.1.1.2) | 77 | 0 |
| LFM2.5 1.2B Instruct (from 1.1.1.2) | 161 | 12 |
| **LFM3 1.7B** | **156** (flexible 156) | **85** (flexible 85) |

Out of 200 invoices, strict scoring. Same run, three input layouts: 156 · 156 · 157 (`RESULTS.md`). Noisy-invoice results of LFM3 are in `RESULTS.md` and the raw answers in `package.zip`; they were not discussed in the video.

**Easy-test losses.** 36 of the 44 lost invoices contain an extra field we did not ask for (7 wrong value, 1 parse error). In the server log, 79 header answers kept the raw date in the date field and wrote the requested year-month-day form into a second field the model named itself; that conversion was correct in 79 of 79. The log rotates and does not map one-to-one to the main run, so this count is partial.

## Limits

Single run · no speed comparison with earlier videos (the laptop's power plan differed) · hard-test significance check added afterward · partial log count · the baseline is optimistic (written by someone who knows the invoice generator) · synthetic English documents only.

## Files

| File | What it is |
|---|---|
| `RESULTS.md`, `results.csv` | Every number, computed from the data |
| `MODELS.json` | Model file: name, size, SHA-256, LM Studio version |
| `HARDWARE.json` | ASUS ProArt PX13 (HN7306), AMD Ryzen AI Max+ 395, 128 GB unified memory |
| `FACTS.json` | Numbers said in the video, as data (published groups and LFM3 only) |
| `package.zip` | Engine (`llm_test_office/`), raw answers (`data/`), baseline. Password `llm-test-office` |
| `RERUN.md` | How to re-score the answers and re-run the model yourself |
| `STERILIZATION.md` | Scan for personal or internal information |
| `MANIFEST.sha256`, `damga/`, `MANIFEST.sha256.sig` | Seal of this whole folder |

`TRANSCRIPT_EN.md` and `TRANSCRIPT_TR.md` are the public transcripts of this video (the English one was voiced in the published video). Unlike 1.1.1.2, they have no separate pre-voice-over seal; they are covered by the seal of this folder.
