# SQL concept checks and final test

## Check 1 — SELECT/filter/NULL (10 marks)
1. Find rows where `delivered_at` is missing.
2. Find orders in 2025 with amount >= 1000.
3. Explain `COUNT(*)` vs `COUNT(delivered_at)`.
**Answers:** `IS NULL`; half-open 2025 range and amount predicate; first counts all rows, second counts non-NULL timestamps.

## Check 2 — joins/aggregation (15 marks)
Given invoices and invoice_lines, calculate invoice count and line revenue by month without multiplying invoice count.
**Answer:** aggregate invoices at invoice grain separately from line revenue or count distinct invoice IDs after joining; define status/date rules.

## Check 3 — windows (15 marks)
Return each account's first failed payment and the next successful payment after it.
**Answer approach:** rank/filter failed payments; join to later successful payments; use `MIN(success_ts)` per account or a lateral query; clarify whether “next” is per account or per failure event.

## Final SQL test (45 minutes, 40 marks)
A food delivery company has `restaurants`, `deliveries`, `delivery_events`, `customers`.
1. Compute completed delivery count and median delivery duration by city (10).
2. Find customers with 3+ completed deliveries in 30 days (8).
3. Return latest event per delivery (8).
4. Identify restaurants whose cancellation rate exceeds city average (8).
5. Explain a duplicate join issue and how you validate grain (6).

## Solution notes
- Duration: completed timestamp minus accepted timestamp; exclude/flag negative or missing durations.
- 30-day condition: define rolling 30 days vs calendar month.
- Latest event: `ROW_NUMBER` with event timestamp and event ID tie-break.
- Cancellation rate: cancelled / eligible delivery attempts; guard denominator with `NULLIF`.
- City average: clarify weighted average of all deliveries vs average of restaurant-level rates.
