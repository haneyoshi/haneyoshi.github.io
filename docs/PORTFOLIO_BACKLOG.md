# Portfolio Improvement Backlog

## Purpose

This document keeps later portfolio improvements small, evidence-led, and separate from the completed rebuild work. It is a prioritized task queue, not a replacement for `docs/PORTFOLIO_REBUILD_PLAN.md` or a large roadmap.

## Prioritization rules

- Preserve factual accuracy, privacy, accessibility, performance, and the current Astro architecture.
- Treat priority as sequence, not automatic approval: an item is ready only when its prerequisites and evidence requirements are satisfied.
- Keep each implementation narrowly scoped and avoid combining unrelated improvements.
- Do not add content, media, interactions, dependencies, or tracking speculatively.

## Prioritized backlog

All four current priority items have been reviewed. None authorizes implementation under current evidence, and no priority item is currently ready for further work.

### Priority 1 — MediCheck visual review — Reviewed

- **Task:** Decide whether one additional MediCheck screenshot adds meaningful implementation evidence.
- **Status:** Review complete. Keep the current single screenshot; do not create an image implementation task. `docs/MEDICHECK_VISUAL_REVIEW.md` is the governing review record.
- **Decision:** No preserved additional still image provides non-duplicative implementation evidence. `images/mediBranding.webp` was declined because it is decorative and could imply unsupported product or medical maturity. The existing `images/Medi_main_window.png` remains the only approved MediCheck visual.
- **Value:** A relevant screenshot may clarify the prototype's interface or technical workflow beyond the current image.
- **Scope boundary:** Review preserved MediCheck assets and, only if justified, select at most one additional screenshot. Exclude decorative branding and unreviewed video; video remains out of scope unless privacy, content, accessibility, audio, captions or transcript, performance, and mobile-usability checks later support publication.
- **Dependencies or prerequisites:** Access to the preserved assets and a clearly identified evidence gap in the current case study.
- **Evidence required before implementation:** Side-by-side review showing that the candidate adds non-duplicative implementation evidence and passes privacy, accuracy, relevance, image-quality, accessibility, and representative-status checks.
- **Likely files or areas involved:** Preserved `images/` and `videos/` assets, `docs/PORTFOLIO_CONTENT.md`, the MediCheck section in `src/pages/index.astro`, and any separately approved optimized public image.
- **Completion criteria:** A documented keep-or-decline decision exists; if selected, only one reviewed, optimized, explicitly sized, accessible image is added without overstating the prototype, and responsive and build checks pass.

### Priority 2 — EchoTask visual evidence — Reviewed

- **Task:** Reconsider EchoTask visuals after a reliable public-presentable implementation state exists.
- **Status:** Review complete. The decision is `Not ready for portfolio visual evidence`. `docs/ECHOTASK_VISUAL_READINESS_REVIEW.md` is the governing review record. Retain `Interface preview in development.` and do not create a screenshot or implementation task.
- **Decision:** The inspected EchoTask state does not provide a reliable, reproducible, privacy-approved, integrated, public-presentable interface. The main blockers are no frontend-to-backend integration; simulated submission only; no established clean reproducible setup; untracked required supply seed data; no current proof that all 52 tests pass; unresolved privacy provenance for operationally shaped data; tracked secret configuration requiring removal and rotation; and no approved public-presentable visual state. Satisfying these blockers would require EchoTask development or repository maintenance, which remains paused.
- **Value:** Honest visual evidence could strengthen the project preview once the implementation can support it.
- **Scope boundary:** Keep EchoTask development paused while the portfolio remains the priority. Review visuals only; do not use this item to develop EchoTask or claim completed integration, authentication, testing, production deployment, or organizational adoption.
- **Dependencies or prerequisites:** A reliable implementation state, current verified project status, and separately approved evidence suitable for public presentation.
- **Evidence required before implementation:** Reproducible working interface state; privacy and content review; confirmation that the visual represents implemented behavior and does not imply unsupported maturity.
- **Likely files or areas involved:** EchoTask's separately maintained repository or evidence, `docs/PORTFOLIO_CONTENT.md`, the EchoTask section in `src/pages/index.astro`, and any separately approved optimized public image.
- **Completion criteria:** The temporary presentation is changed only if reviewed evidence exists; status and limitations remain explicit; the visual is accessible, responsive, and accurate; focused checks pass.

### Priority 3 — Optional signature interaction — Reviewed

- **Task:** Determine whether one restrained interaction is justified by a material storytelling, navigation, orientation, or evidence-inspection problem.
- **Status:** Review complete.
- **Decision:** `No interaction justified`. `docs/SIGNATURE_INTERACTION_JUSTIFICATION_REVIEW.md` is the governing record. No interaction implementation or design task should be created under the current evidence.
- **Value:** A purposeful interaction may make important evidence easier to understand or reach without distracting from the content.
- **Scope boundary:** Reconsider only if a specific material storytelling, navigation, orientation, or evidence-inspection problem is observed and static corrections are first shown insufficient. Accessibility, progressive enhancement, keyboard access, reduced motion, and dependency constraints still apply.
- **Dependencies or prerequisites:** Evidence meeting the reconsideration threshold, followed by a separately approved interaction design.
- **Evidence required before implementation:** An observed material problem, evidence that static corrections are insufficient, accessible no-JavaScript behavior, interaction and motion specifications, and justification for any proposed dependency.
- **Likely files or areas involved:** The relevant Astro component or `src/pages/index.astro`, existing styles, and narrowly scoped script only if necessary.
- **Completion criteria:** One approved interaction works with keyboard and pointer input, respects reduced motion, preserves all essential content without JavaScript, introduces no unjustified dependency, and passes accessibility, responsive, and build validation.

### Priority 4 — Privacy-appropriate analytics decision — Reviewed

- **Task:** Decide whether analytics provide enough value to justify implementation.
- **Status:** Review complete.
- **Decision:** `No analytics justified`. `docs/PORTFOLIO_ANALYTICS_DECISION.md` is the governing review record. No analytics requirements or implementation task should be created under current evidence.
- **Value:** Carefully chosen measurements could answer a defined portfolio question and guide later decisions.
- **Scope boundary:** Do not create analytics requirements, vendor research, or implementation work under current evidence.
- **Dependencies or prerequisites:** One specific material content, navigation, or maintenance decision; a defined measurement and decision threshold; evidence that non-tracking methods are inadequate; and enough sustained relevant traffic or observation volume.
- **Evidence required before implementation:** Proportionate privacy, retention, access, disclosure, and GitHub Pages requirements, followed by a separate approved requirements review before implementation.
- **Likely files or areas involved:** Planning documentation first; only a separately approved implementation may affect Astro layout/configuration, privacy disclosure, or deployment settings.
- **Completion criteria:** The decline decision remains in effect unless every reconsideration prerequisite is supported and separately reviewed; no tracking is added under the current evidence.

## Deferred or excluded work

Keep the following outside the active backlog unless new evidence establishes a requirement:

- broad redesign;
- dark mode;
- React migration;
- Tailwind CSS;
- animation libraries;
- state-management tools;
- broad component refactors;
- deployment migration or workflow replacement;
- legacy-file cleanup;
- branded Safari testing without access to the required environment;
- speculative performance optimization;
- unsupported content expansion; and
- unrelated EchoTask development.

The portfolio remains a single-page public professional profile containing important public professional information without reproducing the full résumé. A résumé PDF, résumé download link, and dedicated résumé webpage are excluded. Private master and job-specific résumés remain outside this public portfolio backlog and workflow.

## How to select the next task

All four current priority items have been reviewed, none authorizes implementation under current evidence, and no new speculative priority item should be added. Resume selection only when new evidence satisfies a documented prerequisite; any resulting work must remain a focused task, branch, review, validation, and planning update without changing the priority order.
