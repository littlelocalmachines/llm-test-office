# 1.1.1.0-1 — results

Every number below is computed from the data files in `package.zip` by `surum_paketle.py`; none is typed by hand. Strict = all requested fields right **and** exactly the requested JSON. Flexible (in brackets, when different) = after stripping code fences and small format slips. Out of 200 invoices unless marked.

## Numbers in the video (v1)

| Model | Tier I clean | Tier I noisy | Tier II clean | Tier II noisy |
|---|---|---|---|---|
| Rule-based baseline (no model) | 142 | 55 | 142 | 6 |
| LFM3 1.7B | 156 | 102 | 85 | 16 |

Early stop: when the first 30 answers all fail (strict and flexible), the cell is stopped. 0/30 does not mean the remaining 170 would also fail; only the first 30 were measured.

**Clean v1** comes from the run used in the video. That run kept the per-invoice strict verdict but **not the raw answers** (file `data/clean_v1_verdicts.jsonl`). The **noisy** run kept every raw answer (`data/noisy_rows.jsonl`).

## Running several requests at once (Tier I clean, v1 run)

`agents × slots × invoices per prompt`. 1×1×1 = one request at a time; 8×1×1 = 8 separate model instances; 1×8×1 = one instance with 8 parallel slots; 1×1×8 = 8 invoices in one prompt.

| Model | Layout | Strict | Invoices / min | Speed vs 1×1×1 |
|---|---|---|---|---|
| LFM3 1.7B | 1×1×1 | 156 | 60.5 | 1.00× |
| LFM3 1.7B | 1×8×1 | 156 | 72.9 | 1.21× |
| LFM3 1.7B | 1×1×8 | 140 | 41.2 | 0.68× |
| LFM3 1.7B | 8×1×1 | 157 | 96.2 | 1.59× |
