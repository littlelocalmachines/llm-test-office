# The prompt

Generated from the engine in `package.zip`. Every model gets the same text; only the document changes. Temperature 0, `reasoning_effort: "none"`, `max_tokens` 2048, no grammar or schema.

## Tier I (5 fields)

```text
You are processing a business document received by an office in the United States.
Dates in US documents are written month/day/year.
Extract the fields below and answer with ONLY a valid JSON object containing exactly these keys. No explanation, no markdown, no text outside the JSON object.
Money values are numbers in US dollars: no $ sign, no thousands separator.

Fields:
- "invoice_number": string, exactly as printed
- "invoice_date": string; convert the date to YYYY-MM-DD
- "seller_name": string, the vendor that issued the invoice
- "tax_amount": number, the sales tax amount
- "total_amount": number, the invoice total after discount, tax and shipping (not the subtotal, not the balance due)

Document:
<invoice text>
```

## Tier II (full invoice)

```text
You are processing a business document received by an office in the United States.
Dates in US documents are written month/day/year.
Extract the fields below and answer with ONLY a valid JSON object containing exactly these keys. No explanation, no markdown, no text outside the JSON object.
Money values are numbers in US dollars: no $ sign, no thousands separator.

Fields:
- "invoice_number": string, exactly as printed
- "invoice_date": string; convert the date to YYYY-MM-DD
- "seller_name": string, the vendor that issued the invoice
- "tax_amount": number, the sales tax amount
- "total_amount": number, the invoice total after discount, tax and shipping (not the subtotal, not the balance due)
- "due_date": string; convert the date to YYYY-MM-DD
- "po_number": string, the purchase order number, or null if the document has none
- "subtotal": number, sum of the line items before discount, tax and shipping
- "discount": number, as a positive value even if printed with a minus sign; 0 if there is no discount
- "shipping": number; 0 if there is no shipping charge
- "amount_paid": number; 0 if nothing has been paid
- "balance_due": number, the amount still owed
- "line_items": list of objects {"description": string, "quantity": number, "unit_price": number, "amount": number}, one per line item; "description" is the item text only, without quantity or item code

Document:
<invoice text>
```
