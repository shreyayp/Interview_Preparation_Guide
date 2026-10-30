# Module 12 — Role-specific fresher mock interviews

These mocks are intentionally different from the concept exercises. They test whether you can combine skills under time pressure.

## Mock A — Data Analyst / Product Analyst (90 minutes, 100 marks)
1. SQL analysis — 25 marks, 25 min: identify customers whose second purchase occurred within 60 days; calculate repeat rate by signup cohort.
2. Excel/BI — 15 marks, 15 min: propose a report for subscription renewals and explain the model.
3. Statistics — 15 marks, 15 min: interpret a test result with effect size and confidence interval.
4. Product case — 25 marks, 25 min: free-trial activation falls 8 percentage points.
5. Communication — 20 marks, 10 min: present finding, evidence, recommendation and caveat.

### Answer expectations
- SQL must define cohort, completed purchase and date window.
- BI must define fact grain, dimensions, measures and reconciliation.
- Statistics must not confuse p-value with probability the null is true.
- Product case must validate instrumentation, decompose funnel and segment.
- Communication must distinguish fact from hypothesis.

## Mock B — Junior Data Engineer (100 minutes, 100 marks)
1. SQL — 25 marks, 25 min: latest inventory state per SKU/store; detect source duplicates.
2. Python — 20 marks, 20 min: parse nested JSON, validate required fields, quarantine invalid records.
3. DBMS — 15 marks, 15 min: transaction, index and isolation scenario.
4. Pipeline design — 25 marks, 25 min: daily supplier feed with corrections and missing files.
5. Reliability/behavioural — 15 marks, 15 min: explain a failed run, retry and communication.

### Answer expectations
- Deterministic latest-row selection.
- Python separates parsing, validation and persistence.
- DBMS answer includes engine-specific caveat.
- Design includes raw retention, idempotency, late corrections, backfill, alerting and SLA.
- Behavioural response states actual contribution.

## Mock C — Mixed entry-level data role (60 minutes, 60 marks)
- 15 min SQL: rank sellers by region.
- 10 min Python: frequency and deduplication.
- 10 min DBMS: explain ACID and index trade-offs.
- 15 min business case: revenue flat but active buyers down.
- 10 min project defence: architecture and one limitation.

## Marking guide
Award full marks for correct result plus assumptions, edge cases and explanation. Award partial marks for a correct approach with a small syntax issue if the candidate can debug it. Deduct for unsupported assumptions, silent data loss, incorrect metric denominator or fabricated project claims.

## Interview communication framework
For coding: clarify → state approach → code → test → complexity.
For analytics: define metric → validate data → decompose → quantify → recommend.
For design: requirements → architecture → data model → failure handling → monitoring/security → trade-offs.
For behavioural: STAR, with specific personal actions and honest outcomes.

## External timed practice for this module

### Analyst / Product Analyst track
- [DataLemur](https://datalemur.com/questions): complete 10 mixed SQL questions tagged easy/medium, prioritising joins, aggregation, ranking and product metrics.
- [StrataScratch](https://www.stratascratch.com/): complete 5 business-oriented SQL questions; explain assumptions before coding.
- [LeetCode SQL 50](https://leetcode.com/studyplan/top-sql-50/): complete the full plan, then reattempt failed questions under a 45-minute limit.
- [Kaggle Learn](https://www.kaggle.com/learn): complete Python and Pandas exercises; perform one independent dataset analysis.

### Junior Data Engineer track
- [HackerRank SQL](https://www.hackerrank.com/domains/sql): complete 10 mixed SQL problems.
- [LeetCode](https://leetcode.com/problemset/): solve 10 Easy and 3 Medium array/hash-map problems.
- [Exercism Python](https://exercism.org/tracks/python): complete 5 exercises and review edge cases.
- [DataTalksClub Zoomcamp](https://github.com/DataTalksClub/data-engineering-zoomcamp): complete one selected ingestion or warehouse lab and explain the architecture.

### Final rule
Do not count a problem as completed merely because the platform accepted the code. Re-solve it from a blank editor after 3–7 days and explain complexity, grain, assumptions and edge cases aloud.
