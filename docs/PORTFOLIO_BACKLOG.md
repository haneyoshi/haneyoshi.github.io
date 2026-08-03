# Portfolio Improvement Backlog

## Purpose

This document keeps later portfolio improvements small, evidence-led, and separate from the completed rebuild work. It is a prioritized task queue, not a replacement for `docs/PORTFOLIO_REBUILD_PLAN.md` or a large roadmap.

## Prioritization rules

- Preserve factual accuracy, privacy, accessibility, performance, and the current Astro architecture.
- Treat priority as sequence, not automatic approval: an item is ready only when its prerequisites and evidence requirements are satisfied.
- Keep each implementation narrowly scoped and avoid combining unrelated improvements.
- Do not add content, media, interactions, dependencies, or tracking speculatively.

## Prioritized backlog

### Priority 1 — Public-safe résumé

- **Task:** Prepare and publish a universal public-safe résumé, then replace the existing résumé placeholder.
- **Value:** Gives visitors a reviewed, portable summary of qualifications and experience.
- **Scope boundary:** Create and review one universal public résumé and update its final portfolio link only after approval. Do not modify the résumé or placeholder as part of this backlog task.
- **Dependencies or prerequisites:** Final résumé document, stable public URL, and explicit publication approval.
- **Evidence required before implementation:** Privacy and accuracy review; working-link check; confirmation that every role, date, skill, credential, and claim is supported.
- **Likely files or areas involved:** Résumé source/output managed in its separately approved task, `docs/PORTFOLIO_CONTENT.md`, and the résumé action in `src/pages/index.astro`.
- **Completion criteria:** The approved public-safe document is accessible at the verified URL; the placeholder is replaced; privacy, claims, links, accessibility, responsive behavior, and focused checks pass.

### Priority 2 — MediCheck visual review

- **Task:** Decide whether one additional MediCheck screenshot adds meaningful implementation evidence.
- **Value:** A relevant screenshot may clarify the prototype's interface or technical workflow beyond the current image.
- **Scope boundary:** Review preserved MediCheck assets and, only if justified, select at most one additional screenshot. Exclude decorative branding and unreviewed video; video remains out of scope unless privacy, content, accessibility, audio, captions or transcript, performance, and mobile-usability checks later support publication.
- **Dependencies or prerequisites:** Access to the preserved assets and a clearly identified evidence gap in the current case study.
- **Evidence required before implementation:** Side-by-side review showing that the candidate adds non-duplicative implementation evidence and passes privacy, accuracy, relevance, image-quality, accessibility, and representative-status checks.
- **Likely files or areas involved:** Preserved `images/` and `videos/` assets, `docs/PORTFOLIO_CONTENT.md`, the MediCheck section in `src/pages/index.astro`, and any separately approved optimized public image.
- **Completion criteria:** A documented keep-or-decline decision exists; if selected, only one reviewed, optimized, explicitly sized, accessible image is added without overstating the prototype, and responsive and build checks pass.

### Priority 3 — EchoTask visual evidence

- **Task:** Reconsider EchoTask visuals after a reliable public-presentable implementation state exists.
- **Value:** Honest visual evidence could strengthen the project preview once the implementation can support it.
- **Scope boundary:** Keep EchoTask development paused while the portfolio remains the priority. Review visuals only; do not use this item to develop EchoTask or claim completed integration, authentication, testing, production deployment, or organizational adoption.
- **Dependencies or prerequisites:** A reliable implementation state, current verified project status, and separately approved evidence suitable for public presentation.
- **Evidence required before implementation:** Reproducible working interface state; privacy and content review; confirmation that the visual represents implemented behavior and does not imply unsupported maturity.
- **Likely files or areas involved:** EchoTask's separately maintained repository or evidence, `docs/PORTFOLIO_CONTENT.md`, the EchoTask section in `src/pages/index.astro`, and any separately approved optimized public image.
- **Completion criteria:** The temporary presentation is changed only if reviewed evidence exists; status and limitations remain explicit; the visual is accessible, responsive, and accurate; focused checks pass.

### Priority 4 — Optional signature interaction

- **Task:** Consider one restrained interaction that improves project storytelling or navigation.
- **Value:** A purposeful interaction may make important evidence easier to understand or reach without distracting from the content.
- **Scope boundary:** Implement at most one interaction only when a specific user need is demonstrated. Require progressive enhancement, keyboard access, reduced-motion support, and no essential content hidden behind JavaScript; add no dependency unless separately justified.
- **Dependencies or prerequisites:** A documented storytelling or navigation problem that static content does not adequately solve, plus an approved interaction design.
- **Evidence required before implementation:** Clear user benefit, accessible no-JavaScript behavior, interaction and motion specifications, and justification for any proposed dependency.
- **Likely files or areas involved:** The relevant Astro component or `src/pages/index.astro`, existing styles, and narrowly scoped script only if necessary.
- **Completion criteria:** One approved interaction works with keyboard and pointer input, respects reduced motion, preserves all essential content without JavaScript, introduces no unjustified dependency, and passes accessibility, responsive, and build validation.

### Priority 5 — Privacy-appropriate analytics decision

- **Task:** Decide whether analytics provide enough value to justify implementation.
- **Value:** Carefully chosen measurements could answer a defined portfolio question and guide later decisions.
- **Scope boundary:** Produce a decision and recommendation only; do not assume analytics should be installed. Any implementation requires separate approval.
- **Dependencies or prerequisites:** A documented measurement purpose and specific questions that cannot be answered adequately without analytics.
- **Evidence required before implementation:** Privacy review, data-minimization decision, hosting compatibility review, retention and access considerations, and comparison with a no-analytics option.
- **Likely files or areas involved:** Planning documentation first; only a separately approved implementation may affect Astro layout/configuration, privacy disclosure, or deployment settings.
- **Completion criteria:** A documented install-or-decline decision explains purpose, minimum data, privacy implications, hosting compatibility, and approval status; no tracking is added without a separate focused task.

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

## How to select the next task

Future work should normally select only the highest-priority ready item whose prerequisites are satisfied. Each item must become its own focused task, branch, review, validation, and planning update. If the highest-priority item is not ready, record the missing prerequisite and consider the next ready item without changing the priority order.
