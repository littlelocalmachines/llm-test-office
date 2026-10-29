# 1.1.1.1 — results

Every number below is computed from the data files in `package.zip` by `surum_paketle.py`; none is typed by hand. Strict = all requested fields right **and** exactly the requested JSON. Flexible (in brackets, when different) = after stripping code fences and small format slips. Out of 200 invoices unless marked.

## Numbers in the video (v1)

| Model | Tier I clean | Tier I noisy | Tier II clean | Tier II noisy |
|---|---|---|---|---|
| Rule-based baseline (no model) | 142 | 55 | 142 | 6 |
| MiniCPM 5 1B | 147 | 91 | 0 | 0/30 (stopped) |
| Gemma 3 1B | 0 (140) | 0 (103) | 0 (1) | 0/30 (stopped) |
| Llama 3.2 1B Instruct | 0 (3) | 0/30 (stopped) | 0 | 0/30 (stopped) |
| SmolLM2 1.7B Instruct | 127 | 91 | 4 | 0/30 (stopped) |

Early stop: when the first 30 answers all fail (strict and flexible), the cell is stopped. 0/30 does not mean the remaining 170 would also fail; only the first 30 were measured.

**Clean v1** comes from the run used in the video. That run kept the per-invoice strict verdict but **not the raw answers** (file `data/clean_v1_verdicts.jsonl`). The **noisy** run kept every raw answer (`data/noisy_rows.jsonl`).

## Clean re-run with raw answers (r2, 30.10.2026)

Same engine, same invoices and same model keys, run again so the clean answers can be checked too. The LM Studio version and the power mode differ from v1 (see `MODELS.json`), so latencies are not comparable with v1, and where a verdict changed we did **not** separate which of the two caused it. The video numbers stay v1; r2 is published next to them.

| Model | Tier I clean r2 | Tier II clean r2 | Same strict verdict as v1, Tier I | Tier II |
|---|---|---|---|---|
| MiniCPM 5 1B | 147 | 0/30 (stopped) | 186/200 | 30/30 |
| Gemma 3 1B | 0 (143) | 0/30 (stopped) | 200/200 | 30/30 |
| Llama 3.2 1B Instruct | 2 (7) | 0/30 (stopped) | 198/200 | 30/30 |
| SmolLM2 1.7B Instruct | 125 | 0/30 (stopped) | 190/200 | 30/30 |

## Running several requests at once (Tier I clean, v1 run)

`agents × slots × invoices per prompt`. 1×1×1 = one request at a time; 8×1×1 = 8 separate model instances; 1×8×1 = one instance with 8 parallel slots; 1×1×8 = 8 invoices in one prompt.

| Model | Layout | Strict | Invoices / min | Speed vs 1×1×1 |
|---|---|---|---|---|
| MiniCPM 5 1B | 1×1×1 | 147 | 164.7 | 1.00× |
| MiniCPM 5 1B | 1×8×1 | 148 | 146.9 | 0.89× |
| MiniCPM 5 1B | 1×1×8 | 1 | 167.4 | 1.02× |
| MiniCPM 5 1B | 8×1×1 | 149 | 295.3 | 1.79× |
| Gemma 3 1B | 1×1×1 | 0 | 80.5 | 1.00× |
| Gemma 3 1B | 1×8×1 | 0 | 70.5 | 0.88× |
| Gemma 3 1B | 1×1×8 | 0 | 87.9 | 1.09× |
| Gemma 3 1B | 8×1×1 | 0 | 102.7 | 1.28× |
| Llama 3.2 1B Instruct | 1×1×1 | 0 | 104.1 | 1.00× |
| Llama 3.2 1B Instruct | 1×8×1 | 1 | 104.3 | 1.00× |
| Llama 3.2 1B Instruct | 1×1×8 | 0 | 25.8 | 0.25× |
| Llama 3.2 1B Instruct | 8×1×1 | 0 | 193.2 | 1.86× |
| SmolLM2 1.7B Instruct | 1×1×1 | 127 | 41.9 | 1.00× |
| SmolLM2 1.7B Instruct | 1×8×1 | 128 | 37.6 | 0.90× |
| SmolLM2 1.7B Instruct | 1×1×8 | 0 | 21.6 | 0.52× |
| SmolLM2 1.7B Instruct | 8×1×1 | 127 | 97.2 | 2.32× |
