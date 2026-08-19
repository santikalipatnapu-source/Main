# A/B Experiment Brief, StreamLine (B2C)

## Parameters
| Parameter | Decision |
|---|---|
| Feature under test | Spotlight Digest Email — a weekly email containing three curated Spotlight film picks with deep-links into Spotlight title detail pages. |
| Persona | The Already-Lost User (Wanderer segment) |
| Expected outcome | Earlier curated-content reach and stronger session commitment, increasing first‑session engagement and improving Month‑1 retention. |
| Primary success metric | Email Click → Spotlight Play Rate. Increase the percentage of Wanderers who reach a curated title within their first session. |
| Baseline rate | 18% (proxy baseline for click→play behavior) |
| Guardrail metric | Mobile Start‑Playing Rate. Maintain or improve overall mobile Start‑Playing rate so that reducing discovery friction does not unintentionally lower the number of users who begin a session. |
| Guardrail boundary | Must not drop more than 2 percentage points across any two consecutive weeks. |
| Second guardrail | No distinct harm type uncovered that requires a second guardrail. |
| Minimum Detectable Effect | +10 percentage points |
| Sample size per arm | 277 |
| Traffic split | 50 / 50 |
| Test duration | 4–6 weeks (≥ 2 weekly cycles) |
| Significance threshold | p < 0.05 |

## Control vs. Variant
- **Control (A):** The Experience Today
Users receive no Spotlight Digest Email.
They open StreamLine and browse the unchanged discovery experience: large catalog rails, dense Trending rows, and weak curated entry points. This reflects the M2 moment of misery (“It became a warehouse… Volume went up, quality went down”) and is visible in M3 funnel data:

Search → Play conversion dropped 7 points
Session length slipped (31 → 24 min)
Only 11% reach a 30+ min session
Wanderers rely on Trending for 61% of consumption
Month‑0→1 retention cliff persists
- **Variant (B):** Users receive the Spotlight Digest Email once per week.
- **Held constant (isolation check):** All held constant across control & variant:

App version & client build
Spotlight rail (unchanged)
Trending logic
Ranking + ordering of homepage rails
Search, browse, filters
Onboarding
Notifications (none added)
Player UX
Playback logic & errors
Spotlight curator endpoints
Catalog availability (except substitution)
Analytics pipelines (unchanged, only new events added)
User preferences (only opt-out flag introduced)
Weekly system cadence
Infrastructure, backend, APIs
Cross-platform apps (TV, desktop untouched)

Only the Digest Email is added — full attribution guaranteed.

## Hypothesis
> I believe that Spotlight Digest Email — a weekly email containing three curated Spotlight film picks with deep-links into Spotlight title detail pages. for The Already-Lost User (Wanderer segment) will result in Earlier curated-content reach and stronger session commitment, increasing first‑session engagement and improving Month‑1 retention., as measured by a +10 percentage points change in Email Click → Spotlight Play Rate. Increase the percentage of Wanderers who reach a curated title within their first session. within 4–6 weeks (≥ 2 weekly cycles). We will protect Mobile Start‑Playing Rate. Maintain or improve overall mobile Start‑Playing rate so that reducing discovery friction does not unintentionally lower the number of users who begin a session. throughout the test.

## Shipping criteria
> We will **ship** if Email Click → Spotlight Play Rate. Increase the percentage of Wanderers who reach a curated title within their first session. improves by ≥ +10 percentage points at p < 0.05 and Mobile Start‑Playing Rate. Maintain or improve overall mobile Start‑Playing rate so that reducing discovery friction does not unintentionally lower the number of users who begin a session. does not reach Must not drop more than 2 percentage points across any two consecutive weeks. after 4–6 weeks (≥ 2 weekly cycles).
> We will **iterate** if direction is positive but lift is below the MDE.
> We will **kill** if the primary metric shows no improvement or moves negatively.
> The read date is fixed at the end of 4–6 weeks (≥ 2 weekly cycles), no results reviewed before this date.
