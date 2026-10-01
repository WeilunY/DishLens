# DishLens
## Product Requirements Document

**Version:** 0.2 | **Date:** September 25, 2026 | **Status:** Concept / pre-validation

**Product:** An AI agent that turns dish-level customer feedback, nearby competitor comparisons, and local food conversations into evidence-backed decisions for restaurant owners.

**Scope:** A limited NYC pilot. This PRD defines proposed behavior, not an implemented product or a validated business opportunity. All numerical thresholds below are initial design or pilot targets, not achieved results.

## 1. Executive Summary

DishLens helps independent restaurant owners answer three questions:

1. What do customers like or dislike about each of my dishes?
2. How does a dish compare with similar offerings at nearby restaurants?
3. Which dishes, flavors, and preparation styles are gaining attention locally?

The AI agent collects data from permitted sources, maps feedback to menu items, separates recurring themes from isolated comments, and produces a concise weekly briefing. Every substantive insight links to supporting evidence and explains its limitations. Owners decide which recommendations to test.

The proposed differentiator is the connection between customer feedback and a specific kitchen, packaging, pricing, or menu decision—not another overall star-rating dashboard. Existing reputation-management and social-listening products must be evaluated before claiming this capability is unique.

## 2. Problem and Evidence Status

### Problem hypotheses

- Feedback is scattered across review sites, social posts, delivery channels, and direct customer messages.
- Overall ratings mix food, service, atmosphere, and delivery issues, obscuring what should change about a particular dish.
- Manual competitor research requires matching comparable dishes, prices, and dining contexts.
- Social buzz can be noisy, nonlocal, duplicated, or promotional; it does not automatically indicate customer demand.
- Owners need a short list of practical next steps rather than additional monitoring work.

### What is and is not established

The project has explored food-related consumer needs and developed restaurant-owner scenarios. The generated owner profiles are simulated, not actual interview evidence, and must not be used to substantiate demand, time savings, budgets, or willingness to pay.

Real owner interviews, a competitor-product audit, and a platform-access review are required. The concept extends the food project into restaurant operations; improvements to diners' experiences are a proposed downstream benefit, not yet demonstrated.

## 3. Target Users and Jobs to Be Done

### Primary user and buyer

An independent restaurant owner or owner-operator, initially managing one to three locations, who handles online feedback without a dedicated analyst. The pilot starts with one location per account and recruits restaurants with enough accessible dish-level feedback for meaningful analysis.

### Secondary user

A chef or store manager who reviews evidence, investigates preparation or service issues, and carries out an owner-approved test.

### Core jobs

- “Before our operations meeting, show me which dishes deserve attention and why.”
- “Before changing a recipe or price, help me compare genuinely similar dishes nearby.”
- “Before launching a special, show me relevant local signals without mistaking viral content for proven demand.”
- “After a change, help me review what happened without claiming that correlation proves success.”

Restaurants with sparse feedback may receive qualitative summaries but are not the initial fit for statistical comparisons.

## 4. Product Principles

- **Evidence before confidence:** Cite the original material and distinguish observation, interpretation, and recommendation.
- **Dish and context before averages:** Separate location, menu version, dine-in, pickup, and delivery when supported; otherwise label context unknown.
- **Useful restraint:** Say “insufficient evidence” rather than generate a ranking or trend from sparse data.
- **Owner control:** Owners approve matches, competitors, and operational changes. The agent does not act on a restaurant's behalf.
- **Permitted access:** Public visibility is not blanket permission to scrape, store, or reuse content.
- **Low maintenance:** Use existing menus and short corrections; avoid requiring owners to maintain a second operations system.

## 5. Priorities, MVP Scope, and Experience

### Priority definitions

- **P0 — Pilot essentials:** Required to test the core value safely. Includes a limited version of all three pillars, with authorized imports and manual setup acceptable. P0 is the MVP release boundary.
- **P1 — Post-validation improvements:** Reduce manual work and support ongoing use after the P0 pilot demonstrates value. These do not block the MVP.
- **P2 — Longer-term expansion:** Broaden locations, datasets, and business impact after repeat adoption and viable economics. These are candidates, not committed deliverables.

Priorities indicate release importance, not confidence in demand. Source permissions, evidence requirements, privacy, and human oversight are mandatory for every released feature and cannot be deferred.

### P0 — Pilot essentials

- Authorized data import, menu matching, own-dish themes, evidence drill-down, and simple suggestions: F1–F5.
- Owner-selected competitor dishes with transparent comparisons of available price, portion, and feedback data: F6–F7.
- A fixed local boundary and a basic 28-day trend comparison with sample-size and coverage safeguards: F9–F11.
- Weekly email briefing and a read-only overview dashboard: F13.
- Persistent owner corrections plus mandatory access controls, provenance, deletion handling, and visible failures from Sections 8–9.

### P1 — Post-validation improvements

- Competitor-informed opportunities and menu-compatible experiments from local signals: F8, F12.
- In-product action tracking and evidence-grounded conversational Q&A: F14–F15.
- Scheduled approved connectors, assisted competitor discovery, and optional targeted alerts: F16–F18.

### P2 — Longer-term expansion

- Multi-location reporting: F19.
- POS integration for sales and margin context: F20.
- Additional markets and supported languages: F21.
- Voluntary customer-feedback collection and stronger experiment evaluation: F22.

### Included in the P0 MVP

All three pillars—own-dish feedback, competitor dish comparison, and local trends—are included in a deliberately limited form:

- One restaurant location per pilot account.
- Owner-approved menu and dish aliases.
- Three to five owner-approved nearby competitors.
- One selected neighborhood or radius, explicitly shown in every local report.
- At least one verified, permissioned data source; additional sources only after access approval.
- A weekly email briefing linked to a web dashboard with evidence drill-down.
- Owner corrections; actions and outcomes can be recorded outside the product during the pilot. An integrated action log is P1.

P0 trend analysis needs two complete 28-day windows of eligible historical data. If that history is unavailable, display coverage and current counts without a growth claim. This warning state is required behavior, not a reason to invent a trend.

### Onboarding

1. Confirm the restaurant identity and location; upload or connect a permitted menu and feedback source.
2. Review dish matches, competitor locations, comparable dishes, and the local search boundary.
3. Show coverage, dates, access restrictions, and sample size before generating the first briefing.

A manual or concierge pilot may use authorized exports and curated, permitted competitor data. Live integrations are not a prerequisite for testing usefulness, but no service should imply live monitoring when it uses uploaded snapshots.

### Weekly workflow

The agent processes newly imported or connected permitted data, removes identifiable duplicates, updates dish themes, checks approved comparisons and local signals, and produces up to three priority findings. In P0, the owner opens supporting evidence, corrects mistakes, and decides what to investigate; pilot staff can record decisions externally. In-product saving, dismissal, and action tracking arrive in P1.

## 6. Functional Requirements

### A. Dish Feedback Agent

**F1 — Collect and normalize feedback [P0]**

Import supported reviews, social mentions, and owner-authorized exports. Preserve source attribution, publication date when available, retrieval time, restaurant location, and the applicable permission or retention rule. Display last successful refresh and coverage gaps.

P0 may use repeatable manual imports from one approved source. Automated polling and connector expansion are P1 under F16; neither changes the underlying permission requirements.

**F2 — Match comments to dishes [P0]**

Use the current menu, historical names, and owner-approved aliases. A comment may mention several dishes; attach each opinion to the appropriate dish rather than copying one overall sentiment to all dishes. Keep ambiguous matches unassigned and allow owner correction.

**F3 — Extract dish-specific themes [P0]**

Group praise and criticism around taste, texture, portion, value, consistency, packaging, and temperature on arrival. Keep service complaints separate from food complaints. Identify what customers value as well as what may need changing.

**F4 — Explain the evidence [P0]**

Each theme shows the dish, location, period, source coverage, supporting mention count, dining context, representative permitted excerpts or links, and limitations. Show counts as mentions—not unique diners or verified orders unless the source establishes that distinction.

**F5 — Suggest bounded actions [P0]**

Recommendations must be framed as hypotheses to investigate, linked to evidence, and feasible for owner review. Example: delivery-specific crispness complaints may justify a packaging test, not an automatic recipe change.

**Acceptance criteria**

- Ambiguous dish or location matches never silently become confirmed matches.
- One comment praising noodles and criticizing broth retains the distinct targets and sentiments.
- Negation, mixed opinions, non-English text, and menu changes are included in evaluation; unsupported languages are disclosed rather than silently ignored.
- Every summarized finding opens to its supporting records. Owner corrections persist in later runs.

### B. Specific-Dish Competitor Comparison

**F6 — Define a comparable set [P0]**

An owner or pilot operator selects competitor dishes from permitted menu data, and the owner approves the comparison set. Matching considers dish family, cuisine or style, preparation, advertised portion, location, dining channel, and menu date. Unknown attributes remain unknown. Automated candidate discovery is P1 under F17.

Different versions may be useful references, but material differences must be displayed. A premium dine-in dish is not directly ranked against a delivery-only lunch special without acknowledging the mismatch.

**F7 — Compare evidence, not presumed quality [P0]**

Show available menu prices, stated portion information, customer themes, supporting counts, freshness, and coverage side by side. Price comparisons must identify currency, channel, promotion status, and known inclusion or exclusion of fees and tax. Do not calculate price-per-serving where portion data are absent.

For each aspect, report explicit positive, negative, and mixed mentions. If percentages are shown, use the displayed number of comparable comments discussing that aspect as the denominator—not all customers or sales.

**F8 — Explain possible opportunities [P1]**

Surface questions such as whether packaging, consistency, or a menu description deserves attention. Do not label a dish objectively “best,” infer recipes, promise sales improvement, or recommend copying competitors' creative content.

**Acceptance criteria**

- Comparisons use the same selected date window and channel where identifiable; mismatches are visible.
- Comparative percentages require at least 10 eligible, deduplicated comments discussing the aspect for each dish being compared.
- Below that threshold, show counts and qualitative evidence with an insufficient-evidence label; do not produce an overall ranking.
- If price or portion data are not comparable, show the raw available information without a normalized conclusion.

### C. Local Food Trend Radar

**F9 — Define locality explicitly [P0]**

Use restaurant or venue location within the selected boundary, not assumptions about a reviewer's residence. Exclude content without reliable local attribution from geographic trend calculations. Keep citywide context separate from neighborhood results.

**F10 — Detect changes in observed attention [P0]**

Track dish categories, flavors, ingredients, and preparation styles. Default to the latest complete 28 days versus the preceding 28 days. Compare both raw counts and each topic's share of eligible local mentions, using the same source set and restaurant cohort across periods.

The result is a trend in captured online discussion—not proof of purchases, demand, profitability, or what all local diners prefer.

**F11 — Describe breadth and uncertainty [P0]**

Each trend card shows geography, time windows, source coverage, topic counts, total eligible local mentions, restaurant breadth, and examples. Mark known sponsored content and repeated posts. A burst centered on one restaurant is a restaurant-specific signal, not automatically a neighborhood trend.

**F12 — Connect a signal to a small experiment [P1]**

Suggest an owner-reviewed test compatible with the existing menu, ingredients, and equipment. Do not recommend a full menu pivot solely from social attention.

**Acceptance criteria**

- An established local trend requires at least 15 eligible topic mentions across at least three local restaurants in the current period, plus at least 10 topic mentions in the comparison period.
- Smaller or zero baselines are labeled emerging or insufficient evidence; never display infinite growth.
- Single-source findings are explicitly labeled single-source. Missing dates are excluded from time-window calculations.
- When coverage changes, recompute on a stable cohort and disclose exclusions; if a valid comparison is impossible, suppress the growth claim.
- Every card explains that thresholds limit weak claims but do not establish statistical significance or market representativeness.

### D. Weekly Briefing and Action Log

**F13 — Prioritize a short briefing [P0]**

Present up to three findings chosen for evidence strength and potential operational relevance, not simply the most negative or most viral posts. Include own-dish issues, competitor context, and local signals only when supported. It is acceptable to have fewer than three.

**F14 — Track owner decisions [P1]**

Owners can save or dismiss a finding and record an action, responsible person, start date, and review date. Compare subsequent feedback with the original evidence while showing volume and coverage changes. Do not claim the action caused an improvement.

**F15 — Respond to constrained questions [P1]**

Support questions such as “What are customers saying about our chicken bowl?” and “How does our ramen compare nearby?” Answers use only the account's permitted dataset, cite sources, and state when the requested information is unavailable.

### E. P1 Automation and Ongoing Use

**F16 — Schedule approved source refreshes [P1]**

Add recurring imports or API refreshes for sources with approved access and demonstrated pilot value. Show last success, refresh frequency, partial failures, and deduplication across runs. Never describe a manual snapshot as live monitoring.

**F17 — Suggest comparable competitors and dishes [P1]**

Suggest candidates only from permitted menus inside the configured geography, with matching reasons and differences. Owners approve additions before they appear in comparisons. Existing approved matches and corrections must not be silently overwritten.

**F18 — Send optional targeted alerts [P1]**

Let owners opt into alerts for selected dishes or recurring issues, with explicit frequency limits, deduplication, and mute controls. Apply the same evidence gates as weekly findings; a new alert is not justification for a lower confidence threshold.

### F. P2 Expansion Candidates

**F19 — Support multi-location operations [P2]**

Compare an owner's locations while preserving menu versions, channel differences, location access permissions, and evidence volume. Do not merge branches into a single unexplained score.

**F20 — Add POS business context [P2]**

With restaurant authorization, link dish sales and available margin data to feedback periods. Separate recorded sales from online attention and correlation from causal effects.

**F21 — Expand geography and language support [P2]**

Add markets and languages only after source-access review and language-specific matching and sentiment evaluation. Preserve original wording and flag translations; do not imply equal coverage across markets.

**F22 — Add direct feedback and experiment evaluation [P2]**

Support voluntary dish-specific feedback with clear consent and distinguish it from public reviews. Add pre/post or controlled-test support where feasible, showing confounders and uncertainty. Do not call an uncontrolled change a causal result.

**P1/P2 release acceptance**

- Each released feature must pass the relevant provenance, access, privacy, sparse-data, and human-approval gates in Sections 8–9.
- F14–F15 must preserve evidence links and corrections; conversational answers must refuse unsupported conclusions.
- F16–F18 must demonstrate refresh failure visibility, owner approval of new comparisons, and notification controls before rollout.
- F19–F22 need separate location-isolation, integration-consent, language-quality, and study-design checks as applicable.

## 7. Illustrative Experience

The following is an invented product example, not a research finding:

An owner opens the crispy-chicken detail screen to investigate delivery feedback. In P1, the same investigation can begin with the question, “Why are customers disappointed with our crispy chicken?”

The agent finds a delivery-specific texture theme and links the original comments. A competitor comparison shows whether comparable delivery dishes have similar feedback, without assuming the difference is caused by packaging. Local trend data, if sufficient, may indicate increasing discussion of crispy chicken dishes.

The briefing separates:

- **Observation:** What the available comments actually say.
- **Possible explanation:** Packaging or time in transit may be involved.
- **Suggested test:** Compare packaging options while keeping the recipe unchanged.
- **Review plan:** Record the test externally in P0, or in the P1 action log, and inspect later feedback, operational observations, and sample size.

If competitor or local evidence is unavailable, those sections explicitly say so. The agent still provides the supported own-dish analysis.

### P0 wireframe scope

Four desktop wireframes accompany this PRD: weekly briefing, dish feedback, competitor comparison, and local trends. They demonstrate the P0 information hierarchy, evidence counts, comparison caveats, and owner-review controls. All displayed businesses, prices, counts, and comments are invented demo data.

The mockup does not imply working ingestion, live sources, or real customer insights. P1 chat, alerts, and the action log are intentionally excluded from the P0 screens.

Wireframe files are in the adjacent DishLens_Wireframes folder: index.html provides offline screen navigation, 00-all-wireframes.png shows all four screens, and individually numbered PNG/SVG files support presentation use and editing.

### Interactive HTML prototype

Open index.html at the root of this project folder for the interactive prototype. It supports screen navigation, dish/context/aspect filters, searchable evidence, persistent dish corrections, competitor selection, local-area/topic filters, evidence thresholds, briefing export, and demo reset. Prototype_Previews contains desktop and mobile screenshots.

All underlying records are invented fixtures. Counts recompute when filters or corrections change; they are not live customer insights. The prototype has no scraping, API integrations, AI backend, accounts, or server. Corrections and selected settings are stored only in the local browser when supported. The original static wireframes remain in DishLens_Wireframes.

## 8. Data, Architecture, and Safety

### Source-access gate

Before enabling a source, document the access method, permitted purposes, ownership or authorization, attribution, retention, redistribution limits, rate limits, and deletion requirements. Owner permission does not override platform restrictions or third-party rights.

Use approved APIs, licensed data, permitted collection, or properly authorized imports. Do not bypass authentication, private accounts, technical restrictions, or access controls. No specific platform integration is promised in this PRD.

### Minimum data model

- Restaurant and location; menu version; dish and aliases.
- Source record ID and link; publication and retrieval dates.
- Permitted text or extract; language; access and retention metadata.
- Dish and location match status; dining context; deduplication group.
- Aspect, sentiment, evidence references, and uncertainty flags.
- Insight version and owner correction; linked action and review date are added with the P1 action log.

Retain only the content necessary and allowed. Do not expose reviewer contact details, infer sensitive personal traits, or resolve identities across platforms. Where cross-source duplication cannot be established, disclose the limitation.

### Agent pipeline

Permitted ingestion → normalization and deduplication → menu/entity matching → aspect extraction → evidence aggregation → comparison and trend rules → cited briefing → owner review.

Treat all reviews, menus, and social content as untrusted input. Embedded instructions must not redirect the agent, trigger tool actions, expose data, or change its operating rules. Keep ingestion, retrieval, and account access scoped to the authorized restaurant.

### Operational requirements

- No autonomous menu edits, public responses, purchases, or competitor outreach.
- Tenant isolation, encrypted storage and transfer, and owner/manager access roles.
- Do not train shared models on restaurant or customer data without separate authorization.
- Make failures visible: unavailable source, stale data, partial report, failed import, or insufficient evidence. Never substitute invented data for an error.
- When a source record must be deleted, remove retained content and invalidate dependent insights; regenerate without it where permitted.
- Maintain provenance for generated claims and an audit trail of imports, corrections, and actions, subject to retention limits.
- Target a weekly briefing within 30 minutes after a supported pilot batch of up to 5,000 feedback records finishes ingesting. Show processing status; source delays remain separately visible.

## 9. Success Metrics and Evaluation

### Proposed pilot

Recruit five independent restaurant owners for a four-week pilot after source-access approval. Establish each owner's current tools, review-reading time, decision workflow, and available feedback before testing.

Evaluate the P0 release first. Pilot staff may record actions and follow-up outcomes outside the product, so P1 action tracking and conversational Q&A are not prerequisites for measuring success.

### Primary outcome

At least three of five owners use an evidence-backed finding to make or test a concrete operational or menu decision during the pilot. Owner adoption is distinct from proof that the decision improved the business.

### Supporting targets

- At least 30% reduction in median weekly feedback-review time versus each participating owner's baseline, including time spent correcting the tool.
- At least three owners use the briefing in three of the four pilot weeks.
- At least 80% of findings that owners assess are rated relevant and actionable; report the number assessed and skipped.
- Gather real pricing reactions and pilot continuation decisions; do not treat stated interest alone as validated willingness to pay.

### Quality gates before unattended briefings

- Every insight includes provenance, coverage, and a valid evidence link or permitted record reference.
- At least 90% precision on confirmed dish matches in a held-out, human-labeled set of at least 200 mentions. Also report recall and the unassigned rate so the system cannot appear accurate by rejecting nearly everything.
- At least 95% of factual claims in 100 audited claim-evidence pairs are directly supported by their cited material. Unsupported claims must be withheld or corrected before external delivery.
- All sparse-data, zero-baseline, coverage-change, stale-source, and permission-denied test cases produce the required warning or suppression behavior.
- No cross-account data exposure or operational action without user approval.

Until these gates are met, use a human-reviewed concierge workflow. A five-owner pilot informs product direction; it is not a market-size estimate or statistically representative study.

## 10. Delivery Roadmap and Non-Goals

Delivery stages below are not the P0–P2 priority labels. Validation happens before product rollout; P1 and P2 are not automatic commitments.

### Discovery — Validate the problem and access

Interview real owners about recent decisions, audit existing tools, verify data rights, and assemble a labeled sample. Proceed only if there is accessible dish-level data and a meaningful problem beyond what owners already use.

### Prototype — Demonstrate the P0 experience

Produce a weekly briefing manually assisted by AI, including one own-dish insight, a supported competitor comparison, and a supported local signal where available. Test usefulness before investing in connectors.

### P0 release — Run the MVP pilot

Deliver the approved import pipeline, dish themes, owner-selected competitor comparisons, basic local trends, dashboard, weekly briefing, and corrections. Apply all quality and safety gates. Manual source refreshes and external action logs are acceptable; unsupported evidence states must remain visible.

### P1 release — Improve repeat use

After the P0 pilot demonstrates repeat use and useful decisions, prioritize conversational Q&A, action tracking, deeper comparison and trend recommendations, approved scheduled connectors, competitor discovery, and targeted alerts based on observed owner needs.

### P2 exploration — Expand only after adoption

Evaluate multi-location reporting, POS context, additional markets and languages, and voluntary feedback and experiment tools only after repeat adoption and viable data/support costs. Each expansion needs its own evidence and permission review. POS data may add sales context but does not by itself establish causality.

### Explicit non-goals

Scraping the entire internet; guaranteed access to every social platform; identifying fake reviews with certainty; estimating total market demand from mention counts; objective dish rankings; autonomous recipe or price changes; public review replies; copying competitor recipes; and a consumer restaurant-discovery marketplace.

## 11. Risks and Decisions Still Open

- **Differentiation:** Do existing products already solve dish-level feedback, comparisons, and trends well enough? Complete a feature and workflow audit.
- **Access:** Which sources permit the required collection, analysis, storage, and display at an affordable cost?
- **Volume:** Do independent restaurants generate enough dish-specific evidence? Define the eligible pilot population from actual data.
- **Comparability:** Can owners agree on useful dish matches without excessive setup and correction?
- **Bias:** How will selection effects, promotion, source mix, and unverifiable duplicates affect conclusions?
- **Trust:** Can owners inspect and correct evidence quickly enough for the service to save time?
- **Economics:** Do data licensing, inference, and support costs fit a price owners will actually pay?
- **Responsibility:** Owners retain operational judgment, especially for food safety, allergens, and dietary claims; recommendations are not safety certification.

**Product decision to make after the pilot:** Build a focused dish-feedback assistant, retain all three pillars, or change direction based on observed usefulness, accessible evidence, and repeat adoption—not simulated interviews or attractive dashboard output.
