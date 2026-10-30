# Python concept checks and final test

## Check 1 — data structures (10 marks)
1. Choose a structure for fast membership checks over unique IDs.
2. Preserve insertion order while removing duplicates.
3. Explain mutable default argument risk.
**Answers:** set; loop with a seen set and output list; default list is reused across calls.

## Check 2 — functions/errors (10 marks)
Write a function to parse a date string and return `None` for invalid input. Explain why catching broad Exception is dangerous.
**Answer:** use `datetime.strptime` in a try/except `ValueError`; catch expected failures only.

## Final Python test (45 minutes, 40 marks)
Input is a list of web click events: `visitor_id`, `page`, `timestamp`, `campaign`.
1. Validate required fields and timestamp (10).
2. Remove duplicate event IDs if present; define tie rule (8).
3. Compute page views by campaign (8).
4. Find visitors who viewed pricing and later viewed checkout (8).
5. Write tests for empty, invalid, duplicate and out-of-order data (6).

## Solution approach
Use a validation function returning `(accepted, rejected)`; parse timestamps to aware datetime; sort per visitor by timestamp; aggregate with dictionaries or pandas. “Later” means strictly later timestamp; define same-timestamp tie handling. Preserve rejected records and reasons.
