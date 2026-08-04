# Portfolio Rebuild Master Plan

`docs/PORTFOLIO_REBUILD_PLAN.md` governs project status, roadmap, decisions, architecture, and restrictions. `docs/PORTFOLIO_CONTENT.md` is the authoritative editable public-copy source. `docs/PORTFOLIO_WIREFRAME.md` is the approved page-structure reference. `docs/PORTFOLIO_DESIGN_SYSTEM.md` is the approved Version 1 typography and spacing reference. `docs/PORTFOLIO_COLOR_SYSTEM.md` is the approved Version 1 color-system reference. `docs/PORTFOLIO_COMPONENT_PATTERNS.md` is the approved Version 1 component-pattern reference. `docs/PORTFOLIO_ANIMATION_PRINCIPLES.md` is the approved Version 1 animation-principles reference. `docs/PORTFOLIO_MOBILE_LAYOUTS.md` is the approved Version 1 mobile-first layout reference.

## Project goal

Build an original, professional portfolio that reaches a similar level of care and polish as `sarria.ca`, without copying its identity or overstating experience.

The portfolio should demonstrate:

- thoughtful frontend engineering
- clear project storytelling
- strong responsive design
- maintainable code organization
- honest professional positioning
- one memorable interactive feature

## Current positioning

YuShan is positioned as a software developer with experience in IT operations, data reporting, workflow analysis, automation, and technical problem-solving. The portfolio supports software development, full-stack development, application support, systems analysis, technical analyst roles, and related technical work without positioning YuShan exclusively as a frontend developer.

The strategy is **depth over volume**. MediCheck is the dominant case study, EchoTask is a secondary development preview whose active implementation is temporarily paused while the portfolio rebuild is the priority, and the portfolio rebuild itself provides evidence of frontend ability.

## Reference site

Reference: `https://sarria.ca/`

Visible source repository currently associated with that site: `SarriaXD/blog_site`

### Transferable lessons from the reference

- sections are built as focused React components
- content is stored as data and mapped into reusable presentation components
- images are optimized through Next.js
- animations are tied to scroll position and viewport entry
- mobile behavior is intentionally different from desktop behavior
- project screenshots are treated as the main visual evidence
- reusable UI primitives create consistency
- technical claims are supported by interactive demonstrations

### What we will not copy

- exact layout
- wording
- gradients or visual identity
- project claims
- source code
- the number or breadth of technologies presented

## Approved site structure

The approved Version 1 page structure and section hierarchy are defined in `docs/PORTFOLIO_WIREFRAME.md`.

## Technical direction — selected

- Astro with TypeScript
- component-based architecture
- responsive CSS
- accessible reduced-motion behavior
- optimized images
- static hosting through GitHub Pages

React, Tailwind CSS, animation libraries, and other unnecessary dependencies are not part of the initial foundation. They may be considered later only if a verified content or interaction requirement justifies them.

The Astro site is live at `https://haneyoshi.github.io/`. GitHub Pages is configured to use GitHub Actions, the existing Astro deployment workflow completed successfully, and the generated `dist/` site is being served in production. Production verification was completed with no launch blocker found. The legacy root files remain preserved until a separate reviewed cleanup is approved. Do not restart deployment research unless new evidence shows a problem.

## Phased roadmap

### Phase 0 — Research and inventory

- [x] Complete deep audit of `SarriaXD/blog_site`
- [x] Audit the current `haneyoshi.github.io` repository
- [x] Inventory current job experience, education, projects, assets, and resume
- [x] Identify what can be reused
- [x] Decide whether to refactor or rebuild

**Exit condition:** architecture choice, content inventory, and scope are approved.

### Phase 1 — Positioning and content

- [x] Finalize target role and audience
- [x] Write hero copy
- [x] Write concise personal story
- [x] Build MediCheck case-study content
- [x] Define secondary-project presentation
- [x] Rewrite experience and education descriptions
- [x] Select supported skills only

**Exit condition:** all page content exists in draft form before visual implementation.

All required page content now exists in draft form in `docs/PORTFOLIO_CONTENT.md`.

### Phase 2 — Information architecture and visual system

- [x] Create page wireframe
- [x] Define typography scale
- [x] Define spacing system
- [x] Define color system
- [x] Define card, button, section, and navigation patterns
- [x] Choose animation principles
- [x] Design mobile-first layouts

**Exit condition:** every section has a clear purpose and approved layout.

#### Approved Version 1 wireframe decisions

- Use one semantic single-page structure in this order:
  1. Header and navigation
  2. Hero
  3. About
  4. Projects
     - MediCheck
     - EchoTask
  5. Experience and education
  6. Skills supported by evidence
  7. Portfolio rebuild statement
  8. Contact
  9. Footer
- Use the primary navigation anchors `#about`, `#projects`, `#experience`, `#skills`, and `#contact`.
- Give MediCheck, the dominant featured case study, the strongest visual weight.
- Present EchoTask as the secondary development preview with the temporary label `Interface preview in development.`
- Use paired Experience and Education blocks rather than a timeline.
- Organize Skills into four evidence-supported groups without ratings or proficiency claims.
- Preserve logical DOM order and the approved linear project sequences on mobile.
- Keep core content accessible without JavaScript and do not hide essential content behind accordions or interactions.

#### Approved Version 1 typography decisions

- Use `system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif` as the single primary sans-serif stack; do not use an external runtime font service or download font files for Version 1.
- Use nine semantic typography roles and four supported weights: `400`, `500`, `600`, and `700`.
- Use `1rem` default body text; keep metadata and captions at no less than `0.875rem`.
- Use `52ch` for focused text and `68ch` for long-form project content.
- Allow fluid scaling only for display, section, project, and introductory text.
- Keep semantic heading levels independent from visual type styles.

#### Approved Version 1 spacing decisions

- Use a `0.25rem` base unit and the approved nine-token spacing scale.
- Use a `72rem` maximum main container and `clamp(1rem, 4vw, 3rem)` responsive page-edge padding.
- Use `space-section` for standard full-section boundaries and `space-major` for major narrative transitions.
- Give MediCheck more generous evidence spacing while keeping EchoTask compact, polished, and readable.
- Restrict one-off values to documented accessibility, media, or optical needs.
- Preserve logical DOM order and mobile-first spacing behavior.

#### Approved Version 1 color decisions

- Use light mode only for Version 1; defer dark mode and a dark-mode toggle.
- Use a warm-neutral foundation with charcoal-blue text, one deep-blue primary accent, and no second strong decorative accent. Reserve warm orange for keyboard focus only.
- Keep page backgrounds mostly continuous with selective quiet surfaces. Do not require gradients or full application-style status palettes without a real requirement.
- Use semantic color tokens rather than repeated raw values. Color must not be the only indicator of state, project maturity, selection, or action.
- Give MediCheck stronger evidence emphasis. Keep EchoTask quieter and do not use warning colors for its unfinished status.

| Core role | Approved value |
| --- | --- |
| Page background | `#F7F5F1` |
| Primary surface | `#FCFBF8` |
| Secondary surface | `#EFEEE9` |
| Primary text | `#18212B` |
| Secondary text | `#3F4B57` |
| Muted text | `#596673` |
| Primary accent / link | `#1F5F8B` |
| Accent hover | `#174B70` |
| Accent active | `#103A58` |
| Accent-soft background | `#E4EEF5` |
| Focus indicator | `#A33A00` |
| Subtle border | `#D6D3CC` |
| Strong border | `#7A8692` |

Normal text requires at least `4.5:1` contrast; large text and meaningful interface or graphic boundaries require at least `3:1`. Inline links remain identifiable without color alone, focus-visible remains distinct on every approved surface, and project maturity remains explicit text. `color-border-strong` meets at least `3:1` against every approved surface. Revalidate all contrast during implementation.

**Implementation note:** The provisional Inter-first source token must be reconciled to the approved system-font stack during implementation. Do not download font files merely to preserve the provisional Inter reference.

### Phase 3 — Technical foundation

- [x] Create the `feature/portfolio-rebuild` branch
- [x] Establish Astro with TypeScript and build tooling
- [x] Create initial reusable layout and UI primitives
- [x] Set up the initial content/data structure
- [x] Add Astro and TypeScript checking
- [ ] Add linting and formatting when justified by the project needs
- [x] Confirm local checks and production build
- [x] Migrate GitHub Pages deployment to the Astro `dist/` build

**Exit condition met:** the technical foundation builds successfully, and the GitHub Pages migration to the Astro `dist/` build has been verified in production.

### Phase 4 — Core implementation

- [x] Navigation and hero
- [x] About section
- [x] MediCheck case study
- [x] Secondary project section
- [x] Experience and education paired blocks
- [x] Skills/evidence section
- [x] Contact and footer

**Exit condition met:** all core responsive sections are implemented. Advanced effects and optional polish remain deferred.

#### Experience and Education implementation status

- Implemented in `src/pages/index.astro` as a semantic `#experience` section with a linked `h2`.
- Experience precedes Education in DOM order, and both are presented as equal-status paired blocks.
- The layout is mobile-first and single-column on smaller screens, changing to a balanced two-column layout from `48rem`.
- The section reuses the existing typography, spacing, color, surface, and border tokens, includes direct-anchor scroll spacing, and adds no JavaScript or dependencies.
- Approved public Experience content: **IT Operations Analyst**, **June 2025–Present**, with current technical work involving IT operations, data reporting, workflow analysis, automation, and technical problem-solving.
- Approved public Education content: **Bachelor’s degree in Applied Computer Science**, **University of Winnipeg**, **Completed in 2023**.
- Do not publish the employer name or confidential systems, processes, or private data. Do not invent responsibilities, metrics, achievements, clients, users, or business outcomes. Do not shorten the credential to only “Computer Science,” and do not feature individual academic assignments.
- Long-form text remains left-aligned, the main container width remains unchanged, and no page-wide centering or global column redesign has been introduced. The local two-column treatment is sufficient for this section; broader right-side whitespace and full-page composition will be reviewed during later full-page polish after all Phase 4 core sections exist. This deferred work is not a defect.

#### Skills/evidence implementation status

- Implemented in `src/pages/index.astro` as a semantic `#skills` section with a visible linked `h2`, directly after Experience and Education in DOM order. A short introduction precedes four equal-status evidence groups in this exact order: Software development; Data and relational systems; Workflow analysis and automation; Technical operations and problem-solving.
- The groups use evidence-based prose rather than an unsupported technology list. Software development connects Python and MySQL to MediCheck, JavaScript, React, and Flask to EchoTask, and Astro and TypeScript to the portfolio rebuild. Data and relational systems connects MediCheck relational database design and SQL retrieval with EchoTask relational modeling using SQLAlchemy and SQLite.
- Workflow analysis and automation connects public-safe current-role experience involving workflow analysis and small automation tools with EchoTask's translation of operational workflow ideas into data structures and application responsibilities. Technical operations and problem-solving connects IT Operations Analyst experience, a Bachelor's degree in Applied Computer Science, independent software projects, and iterative portfolio rebuilding work.
- The mobile-first layout is single-column on smaller screens and becomes a balanced two-column grid from `48rem`. It reuses the existing typography, spacing, color, surface, border, and layout conventions, includes direct-anchor scroll spacing, and adds no JavaScript, links, packages, or dependencies.
- Do not add proficiency ratings; skill meters, percentages, progress bars, stars, or level labels; a generic technology-logo wall; unsupported tools or technologies; years-of-experience claims; invented achievements, responsibilities, clients, users, metrics, or business outcomes; employer identity or confidential work details; or individual academic assignments. Do not shorten the credential to only "Computer Science."
- Manual browser review was completed and the section looked good across the previously required viewport and zoom conditions. Astro checking passed with 0 errors, 0 warnings, and 0 hints; the production build completed successfully; `git diff --check` passed; and only `src/pages/index.astro` changed in the implementation.
- Long-form text remains left-aligned, the main container width remains unchanged, and no page-wide centering or global column redesign has been introduced. Broader right-side whitespace and full-page composition remain deferred until later full-page polish after all Phase 4 core sections exist; this deferred work is not a defect.

#### Contact and Footer implementation status

- Contact appears after Skills in the page structure, ordered as heading, invitation, visible email, then LinkedIn.
- The public email, `pokemonbotno001@gmail.com`, remains visible and copyable as ordinary inline contact information through a `mailto:` link.
- LinkedIn is the only styled Contact action and continues to link to `https://www.linkedin.com/in/yushan-hung-266273212/`.
- The shared Footer contains `Designed and built by YuShan.` and the supporting line `Portfolio rebuild in progress. Core experience and project information is available.` The rebuilding note is visually quieter than the authorship line.
- The page has exactly one footer landmark. No new dependency, JavaScript, contact form, copyright year, animation, or deployment change was added.
- Astro checking and the production build passed.
- The implementation was committed as `402c69b Complete contact and footer sections` and merged into `main` through merge commit `483a1ef Merge pull request #14 from haneyoshi/feature/portfolio-experience-education`.

### Phase 5 — Signature interaction and polish

- [x] Assess whether one meaningful signature interaction is justified — review complete; no interaction is currently justified
- [ ] Add restrained scroll/entry animations
- [ ] Add project mockups and screenshots
- [ ] Improve loading behavior
- [ ] Add reduced-motion support
- [ ] Refine hover, focus, and active states

**Exit condition:** interactions reinforce content rather than distract from it.

Phase 5 polish may continue incrementally while the production site remains live.

#### Signature-interaction review status

`docs/SIGNATURE_INTERACTION_JUSTIFICATION_REVIEW.md` is the governing review record. The accepted decision is `No interaction justified`: the current static portfolio already provides adequate storytelling, navigation, project distinction, evidence connections, keyboard access, and no-JavaScript access. Returning from deep content was the only plausible friction, but its significance was not established; if evidence later shows a material problem, static contextual or back-to-top links are the first remedy. No interaction, JavaScript, animation, dependency, or interaction-design task is authorized under the current evidence.

#### MediCheck wide-screen visual-polish status

- Merged through pull request #18. From `64rem`, MediCheck uses a two-column composition with the project header spanning both columns; the summary, technical details, and GitHub action appear in the left column, while the existing screenshot and caption appear in the right column. The original single-column presentation remains below `64rem`, with unchanged semantic DOM and accessible reading order.
- The screenshot remains uncropped and capped at its intrinsic 700px width. No JavaScript, dependency, content, asset, or EchoTask change was introduced; this work improved the presentation of an existing approved screenshot and did not add a mockup or screenshot.
- Mobile, tablet, breakpoint-boundary, desktop, narrow-reflow, and 200% zoom conditions were reviewed. Astro checking and the production build passed.

### Phase 6 — Quality assurance

- [x] Mobile, tablet, and desktop review
- [x] Keyboard navigation
- [x] Accessibility checks
- [x] Performance audit
- [x] SEO and social metadata
- [x] Broken-link review
- [x] Copy and grammar review
- [x] Cross-browser review

**Exit condition met:** the Phase 6 quality-assurance checklist is complete.

Phase 6 quality assurance is complete. Future maintenance may include additional environment-specific checks without reopening the completed launch checklist unless new evidence identifies a problem.

#### Cross-browser-audit status

- The audit used synchronized `main` with a clean working tree and reviewed the current Astro source, fresh local production builds, generated output where useful, and live production.
- Representative engine coverage included Google Chrome `150.0.7871.187` using Chromium/Blink, Mozilla Firefox `153.0.1` using Gecko, and Playwright `1.62.1` WebKit `26.5` bundled revision `2336` on Windows.
- Testing covered representative mobile, tablet, desktop, breakpoint, narrow-reflow, and effective 200%-zoom layout conditions. Chrome was reviewed from `320 × 800` through `1440 × 900`; Firefox covered the required responsive widths and breakpoint transitions; and WebKit covered both local and production at every requested viewport.
- The `48rem` and `64rem` responsive transitions behaved consistently. No required correction, recommended refinement, horizontal overflow, rendering defect, failed site request, page-console error, or meaningful browser-specific inconsistency was found.
- Astro checking, the production build, and repository validation passed, and no application correction task was required.
- Representative Chromium, Gecko, and WebKit engine coverage is complete. Playwright WebKit on Windows is not branded Safari; branded Safari on macOS and actual Safari browser zoom were not tested. Actual interactive Firefox 200% zoom and some fully reliable automated keyboard-focus visualization were limited by the automation environment. These limitations did not reveal or establish a reproducible site defect and are not blockers for Phase 6 completion. This review does not claim full coverage of every browser, operating system, assistive technology, or device.

#### Performance-audit status

- The audit reviewed synchronized `main`, a fresh local production build, generated `dist` output, and live production.
- Lighthouse 13.0.1 was used as a temporary one-time tool without adding a project dependency. Valid mobile and desktop runs against local preview and production each scored `100` for Performance.
- Measured results were approximately `0.2–0.9 s` for FCP, LCP, and Speed Index, with Total Blocking Time of `0 ms` and CLS of `0`.
- The production page loads without client-side JavaScript, Astro hydration, external fonts, analytics, tracking, or third-party requests. A normal page load used approximately four requests and about `30 KiB` transferred.
- The MediCheck image is small, lazy-loaded, asynchronously decoded, and has explicit dimensions that prevent layout shift. The metadata-only social-preview image is the largest generated asset but is not downloaded during a normal page visit.
- No meaningful performance defect, regression, failed request, blocking script, excessive main-thread work, unused-CSS problem, duplicate asset, or production layout shift was found.
- A smaller responsive variant or modern format for the MediCheck image may be considered during future image or visual-polish work, but estimated mobile savings of about `5 KiB` do not justify a dedicated correction task.
- GitHub Pages' observed `max-age=600` cache policy is hosting behavior and does not justify a deployment change. Real-user Core Web Vitals field data was unavailable, so the completed results are controlled lab measurements.
- The Performance audit checklist item is complete, and no correction branch is required.

#### Responsive-review status

- Pull request #25 was merged, and production was verified to contain the responsive corrections and copy updates. The Responsive review is fully complete.
- Review was completed on `qa/portfolio-responsive-review` at `320 × 800`, `390 × 844`, `768 × 1024`, the `1023 × 900` and `1024 × 900` breakpoint transition, `1440 × 900`, `1920 × 1080`, narrow reflow, and a `720 × 450` CSS viewport representing the layout space available at 200% zoom from `1440 × 900`.
- One confirmed narrow-width overflow issue was found. The global `body` minimum width was removed, the header navigation received `min-width: 0`, and its narrow-screen column gap was reduced so links can wrap safely.
- Post-correction checks found no page-level horizontal overflow or overflowing descendants at the reviewed widths. The MediCheck wide-screen composition, semantic order, keyboard behavior, and other responsive layouts remained intact, with no unresolved responsive issue remaining.
- This focused review does not constitute cross-browser testing; the separate Cross-browser review remains open.

#### Copy-and-grammar review status

- Pull request #25 was merged, and production was verified to contain the approved wording corrections. The Copy and grammar review is fully complete.
- Public copy was compared among `src/pages/index.astro`, `docs/PORTFOLIO_CONTENT.md`, the professional-positioning and claim restrictions in this planning document, and live production where useful.
- Three small wording corrections were applied consistently: clearer About-role wording; removal of “involving experience in” from the Experience description; and parallel wording for workflow analysis and automation.
- The exact credential remains `Bachelor’s degree in Applied Computer Science`. MediCheck and EchoTask descriptions remain accurate to their approved scope and maturity.
- No employer identity, confidential information, unsupported metrics, or overstated claims were found or introduced. The copy-and-grammar review has no remaining blocker.

#### Accessibility-audit status

- The audit reviewed synchronized `main`, a fresh production build served locally, and live production where useful. Production was confirmed to include pull request #25's responsive and copy changes.
- Lighthouse 13.0.1 was used as a temporary one-time tool against the fresh local Astro preview. It scored `100`, and no automated accessibility audit failed.
- Manual checks covered document language and title; landmarks; heading hierarchy; semantic sections and articles; accessible link names; skip-link behavior; internal anchors; image alternative text and caption relationship; decorative separators and `aria-hidden`; focus visibility; text resizing and 200% zoom; narrow reflow; reduced motion; touch-target sizing; status wording; duplicate IDs; ARIA references; hidden content; and obvious semantic misuse.
- No required accessibility correction was found. All implemented text, link, button, focus-indicator, and strong-border combinations passed their applicable contrast requirements.
- Subtle decorative borders measured approximately `1.29:1` to `1.44:1`, but they do not identify controls, communicate state, or serve as the only means of grouping information. They remain an optional refinement rather than a confirmed WCAG failure.
- The Accessibility checks item is complete, and no correction branch is required.

#### Keyboard-navigation audit status

- A complete keyboard-navigation audit was performed across the page's interactive focus order.
- `Tab` and `Shift+Tab` were tested at mobile, tablet, desktop, and 200% reflow conditions.
- Focus indicators remained visible, the skip link remained functional, and internal anchor navigation was verified.
- One issue was found: global `scroll-behavior: smooth` caused rapid keyboard focus movement to leave the focused element temporarily off-screen while scrolling caught up.
- The global smooth-scrolling rule was removed from `src/styles/global.css`, restoring instant native browser scrolling for keyboard focus, skip-link navigation, internal anchors, and browser-driven scrolling.
- The fix did not affect the MediCheck wide-screen layout and was merged through pull request #20.
- Validation passed: `npm.cmd run check`, `npm.cmd run build`, and `git diff --check`.

#### Broken-link audit status

- A read-only audit reviewed the current Astro source, fresh generated `dist/` output, and live production site.
- All internal fragment links resolve to existing unique IDs. The skip link and navigation, hero, project, contact, and back-to-top links were reviewed.
- The MediCheck and EchoTask GitHub repository links returned valid responses. The public email link is correctly formed as a `mailto:` link; mailbox delivery was outside the audit scope.
- The generated stylesheet and optimized MediCheck image resolve successfully in local output and production.
- No local-development paths, missing legacy-file links, accidental parent-directory links, or broken `.html` links were found.
- LinkedIn blocked automated requests with `405` or `999`, so automated verification was inconclusive; this was not evidence of a broken profile link.
- No confirmed broken links were found. `npm.cmd run check`, `npm.cmd run build`, and `git diff --check` passed. The repository remained clean and no files were modified during the audit.
- There is currently no explicit canonical link or favicon reference; their absence belongs to the separate SEO and social metadata audit, not the broken-link review.

#### SEO and social metadata status

- The existing title and description remained accurate, and one canonical URL was added.
- Open Graph type, title, description, URL, image, and image alt were added.
- An original favicon and a 1200 × 630 social-preview image were added.
- `npm.cmd run check` and `npm.cmd run build` passed, and generated metadata appeared exactly once.
- Production returned `200`; the canonical URL, favicon reference, and Open Graph metadata were verified live.
- `/favicon.svg` and `/social-preview.png` both returned `200`.
- Twitter-specific metadata, JSON-LD, `robots.txt`, and a manifest remain intentionally deferred.

### Phase 7 — Launch and maintenance

- [x] Merge approved launch-related pull request
- [x] Verify production deployment
- [ ] Add analytics only if useful and privacy-appropriate
- [x] Document how to add future projects
- [x] Create backlog for later improvements

The minimum staged launch is complete. Incremental polish, QA, documentation, and eventual legacy-file cleanup remain separate reviewed work.

`docs/ADDING_PORTFOLIO_PROJECTS.md` now documents the established process for preparing content, reviewing claims and visuals, following the existing Astro structure, preserving accessibility and responsive behavior, validating changes, and using the approved Git workflow. The guide introduces no application, dependency, deployment, asset, or legacy-file changes.

`docs/PORTFOLIO_BACKLOG.md` contains four prioritized, evidence-driven future improvements covering MediCheck visual review, EchoTask visual evidence, one optional signature interaction, and a privacy-appropriate analytics decision. Each item must remain a separate focused task with its own prerequisites, review, validation, and planning update. The backlog introduces no résumé-related implementation task.

#### Private résumé source-reference status

`docs/PUBLIC_RESUME_REQUIREMENTS.md` inventories the reviewed résumé-related source material and distinguishes current authoritative sources from outdated, external, unreadable, or uncertain legacy material. It preserves confirmed facts, privacy restrictions, evidence rules, unresolved fact-verification notes, project claim limits, and readiness criteria for maintaining a private master résumé and preparing job-specific résumés outside the public portfolio workflow.

The portfolio remains a single-page public professional profile containing important public professional information without reproducing the full résumé. It will have no résumé PDF, no résumé download link, and no dedicated résumé webpage. Private master and job-specific résumés remain outside the public portfolio workflow.

## Working method

1. Discuss goals and decisions in ChatGPT.
2. Record important decisions in this document.
3. Turn the next unchecked item into a small implementation specification.
4. Use Codex in VS Code or a feature branch to implement it.
5. Review the result before merging.
6. Update this checklist and decision log.

## Decision log

- **2026-07-30:** Use `sarria.ca` as a quality reference, not a template to copy.
- **2026-07-30:** Prioritize depth of evidence over number of projects.
- **2026-07-30:** Use this repository document as the living source of truth.
- **2026-07-30:** Do not change production code until reference and current-repository audits are complete.
- **2026-07-31:** Use `WebAppMVP` as the secondary featured project.
- **2026-07-31:** Do not feature individual school assignments in the main project section.
- **2026-07-31:** Keep the project architecture flexible so future projects can be added easily.
- **2026-07-31:** `WebAppMVP`, presented publicly as EchoTask, will be the secondary featured project.
- **2026-07-31:** EchoTask will be labeled as an active full-stack MVP and work in progress.
- **2026-07-31:** EchoTask’s strongest portfolio angle is translating operational workflows into a relational data model and React/Flask application.
- **2026-07-31:** Academic coursework projects will not appear in the main project section.
- **2026-07-31:** EchoTask will not be promoted prominently until one complete frontend-to-backend workflow works reliably and security/privacy issues are addressed.
- **2026-07-31:** Use Astro with TypeScript for the rebuild and continue static hosting through GitHub Pages.
- **2026-07-31:** Build and verify the Astro foundation on `feature/portfolio-rebuild` before changing the legacy root site or deployment workflow.
- **2026-07-31:** Keep React, Tailwind CSS, animation libraries, and unnecessary dependencies out of the initial foundation.
- **2026-07-31:** Handle the GitHub Pages deployment migration as a separate reviewed task, and keep the legacy production site intact until the Astro deployment is verified.
- **2026-07-31:** Do not run the deployment workflow on pull requests; verify it after the reviewed pull request is merged into `main`.
- **2026-07-31:** Keep Astro's generated `dist/` output as the intended GitHub Pages source, preserve the legacy root files, and handle deployment migration and production verification as separate reviewed launch work.
- **2026-08-01:** Portfolio copy is maintained separately in `docs/PORTFOLIO_CONTENT.md` as editable Version 1 copy rather than permanently locked text. The public portfolio will use “Software Developer” as the hero title, with junior-level positioning appearing naturally in supporting copy where appropriate. The official education wording is “Bachelor’s degree in Applied Computer Science.” Home address, phone number, immigration information, sensitive personal email, employer identity, and confidential work information will not be published. EchoTask will use “Interface preview in development” until suitable visuals exist.
- **2026-08-01:** Approve the Version 1 page wireframe and section hierarchy: one Projects section contains MediCheck as the dominant case study and EchoTask as a secondary development preview; Experience and Education use paired blocks; Skills use evidence-based groups; typography and spacing are the next focused Phase 2 task.
- **2026-08-01:** Approve the Version 1 typography and spacing systems: use the system-font strategy, semantic type scale, `52ch` and `68ch` readable measures, nine-token spacing scale, `72rem` container, and responsive page padding; define the color system next.
- **2026-08-01:** Approve the Version 1 color system: use a light-mode-only warm-neutral palette, deep-blue accent, warm-orange focus indicator, semantic tokens, and accessible contrast requirements; define card, button, section, and navigation patterns next.
- **2026-08-01:** Approve the Version 1 component-pattern specification: use content-led project, entry, skill-evidence, action, section, and progressively enhanced navigation patterns with explicit responsive, interaction-state, and accessibility requirements; choose animation principles next.
- **2026-08-01:** Approve the Version 1 animation principles: keep motion restrained, content-supporting, progressively enhanced, performance-aware, and fully usable with reduced motion; design mobile-first layouts next.
- **2026-08-01:** Approve the Version 1 mobile-first layouts: use a content-driven one-column baseline, preserve DOM order, introduce columns only when useful, keep MediCheck dominant and EchoTask compact, and retain responsive accessibility without adding dependencies.
- **2026-08-01:** Implement and manually review the Version 1 navigation and hero across mobile-emulated, tablet, desktop, keyboard-focus, and zoom conditions. The implementation uses ordinary anchor navigation in an always-visible wrapping layout, with no disclosure menu and a non-sticky header; preserves the approved hero content and action order; reconciles the approved warm-neutral, deep-blue, system-font, spacing, and focus tokens; and adds no JavaScript or new dependencies.
- **2026-08-01:** Implement and manually review the Version 1 About section across mobile, tablet, desktop, 200% zoom, anchor navigation, and overflow conditions. The implementation uses a semantic `#about` section with an `h2`, the exact approved About copy, a single-column text-led layout, a `52ch` introductory measure and `68ch` supporting measure, and the approved reusable section-heading token; it adds no JavaScript, new dependencies, imagery, cards, or unrelated sections.
- **2026-08-01:** Approve, implement, review, validate, and commit MediCheck on `feature/portfolio-medicheck` as a solo 2024 Python and MySQL desktop educational software prototype focused on clinic workflow management, relational modeling, and SQL queries across related historical records. Approve `images/Medi_main_window.png` as the primary visual evidence; exclude `images/mediBranding.webp` because it provides no implementation evidence and `videos/mediCheckDemo.mp4` because its content, privacy, audio, accessibility, and claims were not fully verified.
- **2026-08-01:** Approve the EchoTask secondary-project section implemented on `feature/portfolio-echotask`, reviewed across mobile, tablet, desktop, and 100% and 200% zoom, and validated by Astro checking and a production build. It follows MediCheck as a semantic `#echotask` article, presents the paused solo React, Flask, SQLAlchemy, and SQLite full-stack MVP as a compact, text-led work in progress with `Interface preview in development.` and the approved GitHub repository link, and adds no image, mockup, video, JavaScript, or dependency. Projects remains the strongest heading, with MediCheck slightly more prominent than EchoTask and both project titles reduced to remain subordinate. Long-form text remains left-aligned and the wider desktop layout was unchanged; selective columns, wider evidence areas, right-side whitespace, and other page-level composition adjustments are deferred full-page polish after all Phase 4 core sections exist, not an EchoTask defect. The MediCheck demonstration video remains excluded and may be reconsidered during later project-visuals or polish work only after privacy, content and claims, audio, captions or transcript, accessibility, performance, and mobile usability review, without any commitment to publish it.
- **2026-08-01:** Approve Experience and Education as equal-status paired blocks that remain single-column on smaller screens and become two columns from `48rem`; broader desktop page composition remains deferred until all Phase 4 core sections exist.
- **2026-08-01:** Approve Skills as four evidence-based groups rather than ratings or a generic technology list; keep the section single-column on smaller screens and use two columns from `48rem`, while broader desktop page composition remains deferred until all Phase 4 core sections exist.
- **2026-08-01:** Approve and merge the Contact and Footer implementation, completing Phase 4 core implementation and all planned core content sections. Defer optional Phase 5 interaction and polish work until after the minimum staged launch. Because résumés have already been submitted, launch readiness is the immediate priority; this decision does not indicate that the Astro site has been deployed or is publicly live.
- **2026-08-03:** The Astro portfolio is live at `https://haneyoshi.github.io/`. GitHub Pages uses GitHub Actions, the existing deployment workflow succeeded, and production verification was completed. The minimum staged launch is complete with no launch blocker found. Legacy root files remain preserved pending a separate reviewed cleanup. Phase 5 polish and broader Phase 6 QA will continue incrementally without intentionally taking the live site offline.
- **2026-08-03:** The MediCheck project section received a restrained wide-screen composition improvement while preserving its existing content, asset, responsive single-column baseline, and accessible source order.
- **2026-08-03:** The keyboard-navigation audit was completed, and global smooth-scrolling behavior was removed because it interfered with rapid keyboard focus tracking. Native instant scrolling is retained for accessible keyboard and anchor navigation. The Phase 6 Keyboard navigation checklist item is complete; broader accessibility checks remain open.
- **2026-08-03:** The broken-link audit was completed with no confirmed broken links, and the Phase 6 Broken-link review item was completed. LinkedIn automation blocking was treated as inconclusive rather than a defect; canonical-link and favicon absence remained for the separate SEO and social metadata audit.
- **2026-08-03:** The Phase 6 SEO and social metadata item is complete after source, build, and production verification.
- **2026-08-03:** The Phase 6 accessibility audit completed with no required correction. Lighthouse scored 100 on a fresh local production build, manual semantic and interaction checks passed, and subtle decorative-border contrast remains an optional non-blocking refinement.
- **2026-08-03:** The Phase 6 performance audit completed with Lighthouse Performance scores of 100 on valid local and production mobile and desktop runs. No required correction was found, and optional MediCheck image optimization is deferred to future image-related work.
- **2026-08-03:** Phase 6 cross-browser review completed with representative Chromium, Gecko, and WebKit coverage, and no browser-specific correction was required. Branded Safari on macOS and actual Safari browser zoom remain documented environment limitations. Phase 6 quality assurance is complete.
- **2026-08-03:** Small, low-risk corrections may be bundled into a larger related QA task rather than requiring separate branches and pull requests, provided the combined scope remains focused and the complete diff is reviewed.
- **2026-08-03:** Approve `docs/ADDING_PORTFOLIO_PROJECTS.md` as the established guide for adding future portfolio projects while preserving the existing architecture, quality requirements, and reviewed Git workflow.
- **2026-08-03:** Approve `docs/PORTFOLIO_BACKLOG.md` as the small prioritized maintenance backlog for evidence-driven future portfolio improvements.
- **2026-08-03:** The portfolio will remain a single-page public professional profile with important public professional information but without reproducing a full résumé. It will provide no résumé PDF, résumé download link, or dedicated résumé webpage. `docs/PUBLIC_RESUME_REQUIREMENTS.md` is retained as a private source inventory and fact-verification reference for maintaining a private master résumé and preparing job-specific résumés outside the public portfolio workflow. Portfolio and tailored-résumé wording may differ while remaining factual and supported.
- **2026-08-03:** Completed the MediCheck still-image review recorded in `docs/MEDICHECK_VISUAL_REVIEW.md` and declined adding another screenshot. No preserved additional still image provides non-duplicative implementation evidence, and `images/mediBranding.webp` remains declined because it is decorative and could imply unsupported product or medical maturity. The existing `images/Medi_main_window.png` remains the only approved MediCheck visual. No asset, application, content, dependency, deployment, workflow, video, or legacy-file change was justified.
- **2026-08-03:** Completed the EchoTask visual-readiness assessment recorded in `docs/ECHOTASK_VISUAL_READINESS_REVIEW.md` with the decision `Not ready for portfolio visual evidence`. The review found substantial backend source evidence but no reliable, reproducible, privacy-approved, integrated interface state. The repository contains 52 discoverable test methods, but 52 passing tests are not verified because the tests were not executed and no current CI result or test report was found. `Interface preview in development.` remains the approved portfolio label. No EchoTask development, screenshot, asset, portfolio application, dependency, deployment, workflow, or legacy-file change was authorized.
- **2026-08-03:** Accepted the signature-interaction review in `docs/SIGNATURE_INTERACTION_JUSTIFICATION_REVIEW.md` with the decision `No interaction justified`. The current static portfolio adequately supports its content and access tasks, and the only plausible friction—returning from deep content—has no established material significance and has static remedies to test first. No interaction, JavaScript, animation, dependency, or interaction-design task is authorized under the current evidence.

## Current focus

**Phase 7: Assess readiness for the highest-priority remaining evidence-led portfolio maintenance task.**

The privacy-appropriate analytics decision is the highest-priority remaining backlog item ready for assessment. Analytics are not approved for implementation; the next task is documentation only, to determine whether analytics answer a defined portfolio question that cannot be addressed adequately without tracking. EchoTask development remains paused, its portfolio label remains `Interface preview in development.`, and no EchoTask screenshot or implementation task is active. Do not create, publish, host, or link a résumé through the portfolio; private master and job-specific résumés remain separate work.
