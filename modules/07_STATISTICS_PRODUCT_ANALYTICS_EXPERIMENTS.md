# Module 7 — Statistics and product analytics

## Learning outcomes
Define product metrics, interpret distributions, reason about uncertainty and design a basic A/B test.

## 1. Descriptive statistics
Mean is sensitive to extreme values; median is robust to skew. Standard deviation measures spread around the mean. Percentiles describe position in a distribution. IQR = Q3 − Q1 and is useful for robust outlier review.

### Exercise
Delivery times are 12, 14, 15, 16, 93 minutes.
- Mean = 30 minutes.
- Median = 15 minutes.
The mean is pulled up by the 93-minute delay. Report median and p90/p95 as well as mean where tail experience matters.

## 2. Probability and sampling
Understand population, sample, sampling bias, selection bias, survivorship bias, independent events and conditional probability. A large biased sample can still be misleading.

## 3. Confidence intervals and p-values
A confidence interval describes uncertainty under a statistical procedure. A p-value is the probability, assuming the null model, of observing data at least as extreme as what was observed. It is not the probability that the null hypothesis is true. Statistical significance does not guarantee meaningful business impact.

## 4. A/B testing
- Define hypothesis and primary metric.
- Select randomisation unit (user, account, session).
- Define eligibility and exclusion rules.
- Choose minimum detectable effect, alpha and power; estimate sample size.
- Monitor sample ratio, instrumentation and guardrails.
- Avoid unplanned peeking unless using a valid sequential design.
- Report effect size and confidence interval, not just p-value.

## 5. Product metrics
Conversion = converted eligible entities / eligible entities.
Retention requires cohort, return event and time window.
Churn requires a clear cancellation/inactivity rule.
DAU/WAU/MAU require a definition of active and timezone.
ARPU = revenue divided by a stated user base.
Funnel conversion must define event ordering and session/user grain.

## Guided case 1 — Orders are down
A marketplace sees completed orders fall 9% week over week.
Steps:
1. Validate data freshness, tracking and status definitions.
2. Compare traffic, conversion and orders per buyer.
3. Segment by channel, geography, device and new/returning users.
4. Check seasonality, campaigns, release and payment outages.
5. Quantify segment contribution before recommending action.

## Guided case 2 — Feature adoption
A new wishlist feature has 35% adoption among users who saw the prompt.
Ask whether exposure is random, whether users who saw the prompt differ, and whether adoption improves retention or purchase. Adoption alone is not proof of value.

## Independent exercises with answer guidance
1. AOV rises while revenue falls. Explain possible drivers: fewer orders, mix shift, fewer buyers, higher basket value.
2. DAU rises but 7-day retention falls. Segment acquisition cohorts and acquisition channel; check whether low-intent users were acquired.
3. A promotion increases conversion but reduces margin. Calculate incremental contribution, not just conversion lift.
4. An A/B test shows +1.2% conversion with a wide confidence interval crossing zero. State uncertainty; do not claim a proven lift.
5. A dashboard and finance disagree on revenue. Reconcile event status, refunds, timezone, currency, tax, duplicates and recognition rules.

## Product case answer structure
Clarify metric → validate data → decompose → segment → quantify → identify evidence → recommend next action → state caveats.

## Mini assessment (30 minutes, 30 marks)
- Define a retention metric precisely (5).
- Interpret skewed delivery-time data (5).
- Design an A/B test for checkout (10).
- Diagnose a revenue/finance discrepancy (10).

## External practice for this module

1. [Khan Academy — Statistics and Probability](https://www.khanacademy.org/math/statistics-probability) — practise distributions, mean/median, sampling, probability and confidence intervals.
2. [Seeing Theory](https://seeing-theory.brown.edu/) — use the interactive visual explanations for probability, distributions and inference.
3. [StatQuest](https://statquest.org/) — watch the relevant lessons on p-values, confidence intervals, hypothesis tests and statistical power; after each, write a plain-English explanation without replaying the video.
4. [Evan Miller — A/B testing tools and articles](https://www.evanmiller.org/ab-testing/) — study sample size and experiment design; understand assumptions before using a calculator.
5. [DataLemur](https://datalemur.com/questions) — practise business metric SQL questions involving conversion, retention, cohorts and revenue.

**Applied assignment:** choose a public dataset from [Kaggle Datasets](https://www.kaggle.com/datasets), define 3 metrics with explicit denominators, analyse a segment, explain one confounder and write a one-page recommendation. Do not claim causal impact from observational data.

**Exit requirement:** explain mean vs median, sampling bias, confidence interval, p-value, statistical vs practical significance and an A/B test design using a product example.
