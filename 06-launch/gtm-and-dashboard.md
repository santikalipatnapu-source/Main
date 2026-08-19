# GTM Launch Plan, StreamLine (B2C)

| Field | Value |
|---|---|
| Feature | A1 Spotlight Curated Rail |
| Goal | Awareness |
| Launch tier | L, Multi-channel |

## Goal & Audience
- **Goal:** Awareness, Awareness is the right primary goal for this feature right now because Spotlight Digest Email is fundamentally a top‑of‑funnel activator, not a deep product change. Its core value comes from exposure: users must know curated guidance exists before they can benefit from it.
This feature solves a problem rooted in visibility, not functionality. The Already‑Lost User didn’t fail because the platform lacked content — they failed because they never encountered trustworthy, human-curated picks. Their workaround (competitor emails) proves that awareness of curated options is the missing step that unlocks the rest of the journey.
Choosing Awareness as the goal ensures the experiment is judged on what the feature is actually designed to do:
put the right films in front of users, proactively, repeatedly, and reliably. This aligns the metric, the persona’s pain, and the commercial moment — making awareness the correct and most strategic goal right now.
- **Target audience:** Primary: The Already‑Lost User (Wanderer segment) — low‑engagement mobile users who fail to reach curated content without proactive guidance.
Secondary (optional): Adjacent light‑engagement mobile users who occasionally use curated surfaces but do not reliably discover them.
This gives you a precise, defensible audience tied to goal: AWARENESS.

## Launch Tier
- **L, Multi-channel**, The reach is large enough to meaningfully contact the Wanderer segment (the largest low‑LTV cohort). The revenue impact is high because increasing curated-content awareness can directly shift first‑session behavior, Month‑1 retention, and LTV. The risk of silence is significant: under‑launching a feature whose core purpose is awareness would replicate the exact discovery failure Wanderers already face. A Medium, multi-channel launch ensures visibility without over-investing in a still‑validated feature.

## Channels
1. **Owned: Owned: Spotlight Digest Email Direct, proactive curation. Reaches Wanderers exactly where they respond best.**
2. **Earned: Earned: Word-of-Mouth + Social Mentions Builds trust and ambient awareness for users already frustrated by discovery overload.**
3. **Paid: Paid: Lightweight Retargeting to low-engagement users Ensures Wanderers and adjacent segments actually see the curated promise even if they avoid the app.**

## Enablement & Assets
Sales needs: explainer page, FAQ, screenshot, partner copy
Support needs: training doc, troubleshooting flow, macros, known issues
Customer Success needs: help article, behavioral explainer, weekly rationale
Engineering/Design assets: email template, slot components, deep-links, telemetry, eligibility logic, fallback paths

## Ownership, Budget & Timeline
- **Ownership & budget:** Named owners:

PM: Santi
Eng Build: Riya
Backend/Infra: Daniel
Design: Maya
Editorial: Luis
QA: Jenna
Support: Andre
Customer Success: Priya
GTM Marketing: Julia

Budget:

Core build: $0
Paid retargeting: $3–5K
Design/editorial/support: covered by team capacity
Asset gaps: deep-link schema, eligibility spec, editorial guidelines, troubleshooting flow, Digest screenshot.
- **Timeline:** Phase 1 Beta (Weeks 1–4): Build → QA → Internal test → Limited public beta
Phase 2 Launch Moment (Weeks 5–10): Full A/B activation → multi-channel push → two weekly Digest cycles
Phase 3 Post‑Launch (Weeks 11–12): Readout → Ship / Iterate / Kill → Rollout or closeout

## Success Metrics
- **Metrics:** Success Metrics (Awareness)

Digest Reach Rate (Primary) — Did users see the message?
Open Rate (Secondary) — Did users pay attention to it?
Scroll Depth / View Completion (Secondary) — Did they actually see the curated picks?

These metrics match the goal and avoid the common mistake of judging an awareness campaign by conversion.
- **Bad signal to watch for:** Bad signals to watch for:  Low open rate despite high deliverability High opt-out rate in early cycles Weak scroll depth (users not seeing curated picks) Zero earned chatter or sentiment change No movement in upstream cues (deep-link landings, Spotlight views)  These signals indicate the market is not becoming aware, even if your conversion metrics look fine — which is why they matter for an awareness goal.
- **Likely post-launch decision:** Most likely post‑launch decision: ITERATE Awareness campaigns typically deliver partial wins — good exposure, solid opens, uneven scroll depth. That’s enough signal to show the feature is directionally right, but not enough to meet the conversion‑sized MDE. The right post‑launch action will be a focused iteration cycle on subject lines, ordering of curated picks, clarity of value framing, and email hierarchy before scaling further.
