# Experimentation Plan (Module 5)

## Get your documents ready
- **From M3, your hypothesis sentence:** Based on the qualitative evidence that our Wanderer persona continually bounces through Trending and fails to find relevant curated content, and the quantitative evidence that Wanderers consume 61% Trending and have the lowest LTV at $8.40, I believe that reducing early discovery friction for Wanderers will increase their first‑session engagement and strengthen Month‑1 retention. I expect this initiative to deliver a 10% increase in the percentage of Wanderers who reach a curated title in their first session, while protecting the overall mobile Start‑Playing rate.
- **From M3, your primary success metric & guardrail metric:** Primary success metric (initiative signal): Increase the percentage of Wanderers who reach a curated title within their first session. Guardrail metric (product signal): Maintain or improve overall mobile Start‑Playing rate so that reducing discovery friction does not unintentionally lower the number of users who begin a session.
- **From M4, the feature you scoped in your PRD this is what you're testing:** A1 Spotlight Curated Rail

## Define your experiment parameters
- **Feature under test pull from your M4 PRD:** A1 Spotlight Curated Rail
- **Persona pull your M2 persona:** A low‑engagement mobile user who browses casually and makes quick, low‑commitment content decisions
- **Expected outcome the behaviour change you expect, from your M3 hypothesis:** By helping Wanderers find relevant curated content earlier, we expect them to take more sessions per week and stay in those sessions longer, which increases Month 1 retention, boosts LTV, and reduces early churn across the largest segment of the base.
- **Primary success metric the one number that defines success, from M3:** Primary success metric (initiative signal): Increase the percentage of Wanderers who reach a curated title within their first session.
- **Baseline rate today's rate of your primary metric, from your M3 data:** Wanderers rely on Trending for 61% of their content consumption, and their LTV is only $8.40 — the lowest of all segments — confirming that shallow discovery behavior leads to low engagement and poor retention
- **Guardrail metric & boundary what must not break, and how far it can move before you investigate:** Guardrail metric (product signal): Maintain or improve overall mobile Start‑Playing rate so that reducing discovery friction does not unintentionally lower the number of users who begin a session.
- **Minimum Detectable Effect (MDE) the smallest improvement worth shipping, your floor:** A minimum +10 percentage point increase in the percentage of Wanderers who reach a curated Spotlight title within their first session. Any lift smaller than this is not worth shipping.
- **Sample size per arm use the calculator in the builder, baseline + MDE:** nputs used

Baseline rate: 18%
Target uplift: +10 percentage points → 28%
Alpha: 0.05
Power: 0.80
Test: one‑sided, two-proportion z-test

Output
Required sample size per arm:
≈ 432 users per variant
(431.79 rounded up)
Interpretation
To detect a +10pp improvement in your metric (from 18% → 28%) with 80% power and 5% significance, your experiment must expose at least:

432 users in Control
432 users in Treatment

Minimum total required sample: 864 users.
What this means for A6 Spotlight Digest Email
If your weekly eligible segment is larger than ~900 users, you can run this test in one week.
If smaller, you will need to extend the test window accordingly.
- **Traffic split & test duration 50/50 standard · cover ≥ 2 weekly cycles:** Traffic split & test duration:
50/50 standard split · run for ≥ 2 full weekly cycles to ensure coverage of the complete Digest send cadence and stabilize weekly‑behavior variance.
- **Significance threshold p < 0.05 is standard, explain any deviation:** Significance threshold:
p < 0.05 is standard.
Use this threshold unless you have a compelling reason to deviate (e.g., extremely large sample sizes allowing stricter thresholds like p < 0.01, or very low sample sizes requiring exploratory leniency).

## Define your control and variant
- **Control (A) the current experience, reference your M2 moment of misery and M3 funnel/workflow data:** The current StreamLine mobile experience with no Spotlight Digest Email. Users browse the existing “warehouse” discovery surface, relying heavily on Trending and manual searching. This Control condition directly reflects the M2 moment of misery (overwhelming catalog, low relevance, no proactive curation) and is validated by M3 funnel data showing shallow sessions, low curated-content reach, weak search‑to‑play conversion, and the Month‑0→1 retention cliff.
- **Variant (B) your single change, copy the relevant screens & functional requirements from your M4 PRD:** Users receive the Spotlight Digest Email once per week, containing three curated Spotlight film picks with images and 140‑character blurbs. Each entry deep-links directly into the Spotlight title detail page, allowing immediate play. All functionality, screens, behaviors, and constraints are exactly as specified in the A6 Spotlight Digest Email PRD.
- **Isolation check, what has NOT changed? list everything identical between arms (app version, recommendation engine, notifications, onboarding). If something changed inadvertently, your test is compromised.:** Everything about the product remains identical between arms except the introduction of one weekly Spotlight Digest Email in Variant (B). All discovery surfaces, recommendation engines, navigation flows, client builds, notifications, onboarding, playback, analytics, and Spotlight curation endpoints are unchanged. This guarantees complete attribution: any lift in curated-content engagement can only be caused by the Digest Email.

## Formalize your hypothesis & shipping criteria
- **Your hypothesis (filled in):** I believe that Spotlight Digest Email for the Already‑Lost / Wanderer persona
will result in a meaningful increase in curated‑content engagement and earlier session commitment,
as measured by a +10 percentage point change in the Email Click → Spotlight Play Rate
within a 4–6 week test duration.
We will protect the mobile Start‑Playing rate throughout the test.
- **Your shipping criteria (filled in):** We will SHIP if the Email Click → Spotlight Play Rate (primary metric)
improves by ≥ +10 percentage points (MDE)
at a p < 0.05 significance threshold
and the mobile Start‑Playing rate (guardrail metric)
does not drop by more than 2 percentage points across the test duration
of 4–6 weeks.
We will ITERATE if the direction of lift is positive but below the +10pp MDE,
indicating promise but not enough impact to justify full rollout.
We will KILL if the primary metric shows no improvement or moves negatively,
or if the guardrail metric breaches its −2pp boundary,
indicating user harm or degraded session starts.
The read date is fixed at the end of the 4–6 week test window —
no results are reviewed before this date.
- **Hardest parameter to define, and did it change your hypothesis? quick debrief:** Hardest parameter to define: The Minimum Detectable Effect (MDE), because it required constructing a statistical baseline and sample-size model for a feature that doesn’t exist yet.
Did it change the hypothesis?
No.
The statistical MDE validated that the originally hypothesized +10pp lift is feasible and measurable, so the core hypothesis remained exactly as written.
