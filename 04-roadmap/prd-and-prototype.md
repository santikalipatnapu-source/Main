# A6 · Spotlight Digest Email, Simplified PRD (StreamLine)

**Author:** Me · **Status:** Draft · **Target:** High-Fidelity Prototype · **Persona:** The Already-Lost User

## 1. The Big Picture
- **Vision:** A streaming experience where every user instantly receives a small number of hand‑picked films they can trust, turning each evening into high‑quality viewing without the overwhelm.
- **Press release:** For too long, users like Tom have opened StreamLine and felt overwhelmed by a warehouse of choices—endless rows, countless categories, and no clear path to a great evening. He didn’t just get frustrated; he left and found a service that hand‑picked two films a week for him. Today, we’re fixing the problem he already lived. With Spotlight Digest Email, we deliver three carefully chosen films directly to your inbox every week—no algorithms, no digging, no decision fatigue. Just the exact level of curation Tom trusted elsewhere.
This feature restores what was lost: confidence, simplicity, and the feeling of being personally guided toward high‑quality viewing. Spotlight Digest Email cuts through the chaos and gives the Already‑Lost User a small number of great films he can start immediately—preserving our Start‑Playing rate while finally solving the moment of misery that drove users like Tom away. This isn’t more content; it’s the right content, delivered right when you need it.
- **Success metric:** Increase the percentage of users who click from the Spotlight Digest Email into a curated Spotlight title (email click‑to‑Spotlight‑play rate).
- **Guardrail:** Maintain or improve the overall mobile Start‑Playing rate to ensure that proactive curation does not reduce the number of users who begin a session.

## 2. The Details
### User stories
- As an Already‑Lost User, I want to receive three hand‑picked film recommendations in my inbox each week so that I don’t have to sift through a warehouse of choices.
- As an Already‑Lost User, I want each pick to feel human and intentional so that I trust the recommendations enough to start watching immediately.
- As an Already‑Lost User, I want the email to link directly to the films so that I can begin a session without navigating the app.
- As an Already‑Lost User, I want an easy opt‑out so that the emails never become another source of frustration.
### Screens to build
- Entry Point – Email Preview
- The user opens the weekly Spotlight Digest Email and immediately sees three curated film picks with images and short blurbs.
- Feature Core – Spotlight Title Detail Page (Deep Link)
- When the user clicks a film from the email, they land directly on that Spotlight title’s detail page, with play button, synopsis, curator blurb, and Spotlight mark.
- Success / Confirmation – Playback Start Confirmation
- After tapping Play, the user sees a lightweight confirmation state (in-app video player launch) showing that the curated recommendation successfully led to a started session.
### Functional requirements
- The system must send one Spotlight Digest Email every week to all eligible users on a fixed cadence.
- The email must contain exactly three Spotlight‑selected film titles drawn from the curated Spotlight list.
- Each film entry must include a title, image, and a short curator blurb no longer than 140 characters.
- Each film entry must deep‑link directly to the Spotlight title’s detail page inside the mobile app.
- The system must allow users to opt out of the Spotlight Digest Email through a single-tap control in Settings.
- The email must render correctly on mobile and desktop clients using a single responsive layout.
- The system must apply basic eligibility logic (Spotlight users + Wanderer segment) before including a user in the weekly send.
- The system must log basic telemetry (email sent, delivered, clicked) for measurement of the primary success metric.
### Smart behaviors (Situation → Outcome)
- If a user opens the Spotlight Digest Email → then log an “email opened” event.
- If a user clicks a film in the email → then deep‑link them directly into that Spotlight title’s detail page.
- If a user has opted out of Spotlight Digest → then exclude them from the weekly send automatically.
- If a user has clicked a curated pick in the last two weeks → then prioritize films similar to those picks (lightweight personalization).
- If a user’s region does not support a selected title → then replace that pick with the next Spotlight item on the curator list.
- If the email fails to deliver → then send a retry once within 24 hours.
- If a user starts playback from a Digest click → then increment the “Digest‑driven Start‑Play” metric for measurement.
### Technical constraints
- No new backend services or microservices; use only existing Spotlight curation endpoints.
- No machine‑learning models, no AI taste profiles, no personalization engine.
- No database schema changes; only permitted to read existing Spotlight lists.
- No new APIs; the email system must call existing internal content feeds only.
- No user preference storage beyond a single opt‑out flag (Boolean only).
- No dynamic send-time optimization or scheduling intelligence—fixed weekly cadence.
- No in-app inbox, notifications center, or messaging UI—email only.
- No cross-platform parity features (TV, desktop apps); mobile app deep-linking only.
- No heavy analytics pipelines—simple event logging only (open, click, start-play).
- No modular design for future email formats; one template only for V1.

## 3. The Logistics
### Features out
- Full taste‑model AI personalization
- Dynamic email templates or variable send-time optimization
- New backend services or microservices
- In-app inbox or notification center for Spotlight messages
- Multi-language support
- Trailer embeds, GIF previews, or autoplay media
- User-created lists or social sharing
- Watch Party integrations or cross-feature hooks
- Additional Spotlight curator workflows (beyond existing curated list)
- Cross-platform parity features (TV, desktop apps)
### Edge cases & safety guard
- If the email fails to deliver → system retries once within 24 hours, then logs a failure without spamming the user.
- If a Spotlight title becomes unavailable in the user’s region → automatically substitute the next Spotlight pick so the persona never sees a dead recommendation.
- If the deep link breaks → user is redirected to the Spotlight category page rather than a generic home page.
- If the user hasn’t watched anything recently → default to the hand‑picked Spotlight rail (no forced personalization).
- If the user unsubscribes → immediately remove them from all future sends; never send “confirmation” follow‑ups.
- If a user repeatedly ignores the email → system continues sending for 8 weeks, then suppresses quietly to avoid becoming part of the “warehouse” noise.
### Decision log
- 1. Excluded all dynamic personalization and taste-model features.
- I explicitly removed AI recommendations, preference learning, mood-based inputs, and dynamic send-time optimization because they create a second discovery layer. The persona needs fewer choices, not smarter algorithms, and the team cannot support ML complexity in a 3‑week sprint.
- 2. Limited the email to exactly three curated picks in a single fixed template.
- I cut rich curator profiles, trailer embeds, multiple formats, regional variants, and new backend services. Keeping a single template with three titles protects the design/engineering team from multiplying UI states and preserves the core promise: “a small number of well‑chosen films,” not more content to sift through.
### Evals
- 1. Accuracy Target (Content Accuracy / Relevance %)
- ≥ 80% of weekly Digest picks must match the user’s recent taste signals (light heuristics only).
- This ensures the email feels hand‑picked and avoids the “warehouse of irrelevant choices” that caused Tom to churn.
- 2. Time‑on‑Task Target (Speed from Email → Start‑Playing)
- Median time from email click → Start‑Playing must be ≤ 30 seconds.
- This confirms the feature is reducing friction and decision overhead, not adding new steps.
- 3. Safety Target (Start‑Playing Guardrail)
- Mobile Start‑Playing rate must not drop more than 2 points across any 2 consecutive weeks.
- If Digest causes annoyance, misfires, or negative behavioral loops, you halt rollout immediately.

## MoSCoW scope
- **Must:** A1 · Spotlight Curated Rail; A5 · Personalized Spotlight Queue
- **Should:** A9 · Advanced Filter Engine
- **Could:** A3 · Hidden Gem Badge
- **Won't (now):** A8 · Watch Party (Spotlight),

---
**Builder hook:** Build a working prototype based on this PRD. Use the User Story as the core flow, Functional Requirements as build constraints, and prioritize speed and clarity over visual complexity.
