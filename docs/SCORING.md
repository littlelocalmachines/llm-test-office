# How answers are scored

The scorer is `llm_test_office/fatura_ortak.py` and `puan.py` in `package.zip`. In plain words:

- **Strict:** the whole answer parses as one JSON object as it stands, and every field matches.
- **Flexible:** a markdown code fence is removed first, then the same check. It does not convert types: `"18.66"` is not `18.66`.
- **Truncated or looping answers** fail both.
- **Text fields:** the vendor name and line-item descriptions ignore case and extra spaces. The invoice number and the dates must match exactly; dates must be `YYYY-MM-DD`.
- **Money:** numeric equality on JSON numbers. `5` equals `5.0`; a string never equals a number.
- **Keys:** a missing or extra key fails the invoice.
- **Line items (Tier II):** order doesn't matter. Items are matched by description, then by quantity and unit price, then in order.

## Noise

Simulated, not real scans. Visually similar characters swap (0↔O, 1↔l/I, 5↔S, 8↔B, 2↔Z) at a 6% rate; a digit never becomes another digit. Whitespace is corrupted at 8%. Line structure stays. **Answers are graded against the original values**, which the noisy text still shows in a recoverable form.

## Early stop

A run stops if its first 30 answers all fail both strict and flexible. The result is then given as 0/30.

## Baseline

A regex program with no model, scored the same way. We wrote its patterns in general invoice language, with no shortcuts for our generator's labels, but we wrote it knowing the generator, so it is optimistic. On clean Tier I all 58 of its misses are the total field, mostly because it picks up the merchandise total.

## Statistics

McNemar on paired invoices against the baseline.
