# 1.1.1.2 — results

Every number below is computed from the data files in `package.zip` by `surum_paketle.py`; none is typed by hand. Strict = all requested fields right **and** exactly the requested JSON. Flexible (in brackets, when different) = after stripping code fences and small format slips. Out of 200 invoices unless marked.

## Numbers in the video (v1)

| Model | Tier I clean | Tier I noisy | Tier II clean | Tier II noisy |
|---|---|---|---|---|
| Rule-based baseline (no model) | 142 | 55 | 142 | 6 |
| LFM2 1.2B | 77 (78) | 56 | 0 | 0/30 (stopped) |
| LFM2.5 1.2B Instruct | 161 | 103 | 12 | 0/30 (stopped) |
| Qwen3 1.7B | 99 (107) | 68 (69) | 5 | 0/30 (stopped) |

Early stop: when the first 30 answers all fail (strict and flexible), the cell is stopped. 0/30 does not mean the remaining 170 would also fail; only the first 30 were measured.

**Clean v1** comes from the run used in the video. That run kept the per-invoice strict verdict but **not the raw answers** (file `data/clean_v1_verdicts.jsonl`). The **noisy** run kept every raw answer (`data/noisy_rows.jsonl`).

## Clean re-run with raw answers (r2, 30.10.2026)

Same engine, same invoices and same model keys, run again so the clean answers can be checked too. The LM Studio version and the power mode differ from v1 (see `MODELS.json`), so latencies are not comparable with v1, and where a verdict changed we did **not** separate which of the two caused it. The video numbers stay v1; r2 is published next to them.

| Model | Tier I clean r2 | Tier II clean r2 | Same strict verdict as v1, Tier I | Tier II |
|---|---|---|---|---|
| LFM2 1.2B | 79 | 0/30 (stopped) | 158/200 | 30/30 |
| LFM2.5 1.2B Instruct | 160 | 14 | 199/200 | 196/200 |
| Qwen3 1.7B | 90 (95) | 0/30 (stopped) | 143/200 | 30/30 |

## Running several requests at once (Tier I clean, v1 run)

`agents × slots × invoices per prompt`. 1×1×1 = one request at a time; 8×1×1 = 8 separate model instances; 1×8×1 = one instance with 8 parallel slots; 1×1×8 = 8 invoices in one prompt.

| Model | Layout | Strict | Invoices / min | Speed vs 1×1×1 |
|---|---|---|---|---|
| LFM2 1.2B | 1×1×1 | 77 | 46.1 | 1.00× |
| LFM2 1.2B | 1×8×1 | 82 | 58.6 | 1.27× |
| LFM2 1.2B | 1×1×8 | 0 | 29.2 | 0.63× |
| LFM2 1.2B | 8×1×1 | 84 | 91.3 | 1.98× |
| LFM2.5 1.2B Instruct | 1×1×1 | 161 | 59.2 | 1.00× |
| LFM2.5 1.2B Instruct | 1×8×1 | 161 | 80.0 | 1.35× |
| LFM2.5 1.2B Instruct | 1×1×8 | 0 | 44.5 | 0.75× |
| LFM2.5 1.2B Instruct | 8×1×1 | 160 | 106.2 | 1.79× |
| Qwen3 1.7B | 1×1×1 | 99 | 37.3 | 1.00× |
| Qwen3 1.7B | 1×8×1 | 103 | 84.3 | 2.26× |
| Qwen3 1.7B | 1×1×8 | 8 | 27.1 | 0.73× |
| Qwen3 1.7B | 8×1×1 | 104 | 88.9 | 2.38× |
