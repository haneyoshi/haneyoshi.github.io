# Portfolio Rebuild Master Plan

`docs/PORTFOLIO_REBUILD_PLAN.md` governs project status, roadmap, decisions, architecture, and restrictions. `docs/PORTFOLIO_CONTENT.md` is the authoritative editable public-copy source. `docs/PORTFOLIO_WIREFRAME.md` is the approved page-structure reference. `docs/PORTFOLIO_DESIGN_SYSTEM.md` is the approved Version 1 typography and spacing reference. `docs/PORTFOLIO_COLOR_SYSTEM.md` is the approved Version 1 color-system reference. `docs/PORTFOLIO_COMPONENT_PATTERNS.md` is the approved Version 1 component-pattern reference. `docs/PORTFOLIO_ANIMATION_PRINCIPLES.md` is the approved Version 1 animation-principles reference.

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

Current design-system work is occurring on `feature/portfolio-animation-principles`. GitHub Pages deploys Astro's generated `dist/` output, and the migration has been verified in production. The legacy root files remain preserved in the repository.

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
- [ ] Design mobile-first layouts

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

**Exit condition:** empty site shell builds successfully and the deployment migration is verified.

### Phase 4 — Core implementation

- [ ] Navigation and hero
- [ ] About section
- [ ] MediCheck case study
- [ ] Secondary project section
- [ ] Experience and education paired blocks
- [ ] Skills/evidence section
- [ ] Contact and footer

**Exit condition:** complete responsive site without advanced effects.

### Phase 5 — Signature interaction and polish

- [ ] Add one meaningful signature interaction
- [ ] Add restrained scroll/entry animations
- [ ] Add project mockups and screenshots
- [ ] Improve loading behavior
- [ ] Add reduced-motion support
- [ ] Refine hover, focus, and active states

**Exit condition:** interactions reinforce content rather than distract from it.

### Phase 6 — Quality assurance

- [ ] Mobile, tablet, and desktop review
- [ ] Keyboard navigation
- [ ] Accessibility checks
- [ ] Performance audit
- [ ] SEO and social metadata
- [ ] Broken-link review
- [ ] Copy and grammar review
- [ ] Cross-browser review

**Exit condition:** launch checklist is complete.

### Phase 7 — Launch and maintenance

- [ ] Merge approved pull request
- [ ] Verify production deployment
- [ ] Add analytics only if useful and privacy-appropriate
- [ ] Document how to add future projects
- [ ] Create backlog for later improvements

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
- **2026-07-31:** Astro's generated `dist/` output is now the production GitHub Pages source, the legacy root files remain preserved in the repository, and Phase 3 deployment verification is complete.
- **2026-08-01:** Portfolio copy is maintained separately in `docs/PORTFOLIO_CONTENT.md` as editable Version 1 copy rather than permanently locked text. The public portfolio will use “Software Developer” as the hero title, with junior-level positioning appearing naturally in supporting copy where appropriate. The official education wording is “Bachelor’s degree in Applied Computer Science.” The résumé will remain unavailable until a public-safe universal version is prepared. Home address, phone number, immigration information, sensitive personal email, employer identity, and confidential work information will not be published. EchoTask will use “Interface preview in development” until suitable visuals exist.
- **2026-08-01:** Approve the Version 1 page wireframe and section hierarchy: one Projects section contains MediCheck as the dominant case study and EchoTask as a secondary development preview; Experience and Education use paired blocks; Skills use evidence-based groups; typography and spacing are the next focused Phase 2 task.
- **2026-08-01:** Approve the Version 1 typography and spacing systems: use the system-font strategy, semantic type scale, `52ch` and `68ch` readable measures, nine-token spacing scale, `72rem` container, and responsive page padding; define the color system next.
- **2026-08-01:** Approve the Version 1 color system: use a light-mode-only warm-neutral palette, deep-blue accent, warm-orange focus indicator, semantic tokens, and accessible contrast requirements; define card, button, section, and navigation patterns next.
- **2026-08-01:** Approve the Version 1 component-pattern specification: use content-led project, entry, skill-evidence, action, section, and progressively enhanced navigation patterns with explicit responsive, interaction-state, and accessibility requirements; choose animation principles next.
- **2026-08-01:** Approve the Version 1 animation principles: keep motion restrained, content-supporting, progressively enhanced, performance-aware, and fully usable with reduced motion; design mobile-first layouts next.

## Current focus

**Phase 2: The page wireframe, typography, spacing, color, component-pattern, and animation-principles systems are approved. Next, design mobile-first layouts.**
