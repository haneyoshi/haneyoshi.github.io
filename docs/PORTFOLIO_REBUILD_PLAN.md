# Portfolio Rebuild Master Plan

This document is the **single source of truth** for rebuilding YuShan's portfolio. Update it whenever we make a major design, content, architecture, or scope decision.

## Project goal

Build an original, professional portfolio that reaches a similar level of care and polish as `sarria.ca`, without copying its identity or overstating experience.

The portfolio should demonstrate:

- thoughtful frontend engineering
- clear project storytelling
- strong responsive design
- maintainable code organization
- honest professional positioning
- one memorable interactive feature
### EchoTask

EchoTask is an active full-stack MVP exploring how a caretaking operations team could coordinate attendance, work locations, and supply requests through a shared web application.

I am developing the project with React, Flask, SQLAlchemy, and SQLite. The current implementation includes a relational data model for buildings, work areas, users, attendance, snow logs, and supply requests, along with selected Flask API routes and a React prototype for searching supplies, selecting quantities, and reviewing a request summary.

The project grew from analyzing operational workflows and determining how information should be structured, stored, and accessed across different user roles. My current focus is completing one reliable end-to-end supply-request workflow, improving API consistency, and connecting the frontend to persistent backend data.

**Status:** Active MVP and work in progress.

## Current positioning

YuShan currently has:

- computer science education
- electrical engineering background
- a current technical role
- one substantial project: MediCheck
- one smaller or incomplete project
- an existing GitHub Pages portfolio

The strategy is **depth over volume**. MediCheck will become a detailed case study, and the portfolio rebuild itself will become evidence of frontend ability.

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

## Proposed portfolio direction

**Working positioning statement:**

> A software developer with computer science and electrical engineering training who brings structured problem-solving and technical troubleshooting to practical software projects.

This will be refined after the content inventory.

## Proposed site structure

- [ ] Hero: name, role direction, concise value statement, primary actions
- [ ] About: multidisciplinary background and current development journey
- [ ] Featured case study: MediCheck
- [ ] Secondary project or work-in-progress
- [ ] Experience and education timeline
- [ ] Skills supported by actual evidence
- [ ] Signature interactive feature
- [ ] Resume and contact section

## Technical direction — selected

- Astro with TypeScript
- component-based architecture
- responsive CSS
- accessible reduced-motion behavior
- optimized images
- static hosting through GitHub Pages

React, Tailwind CSS, animation libraries, and other unnecessary dependencies are not part of the initial foundation. They may be considered later only if a verified content or interaction requirement justifies them.

The rebuild is occurring on `feature/portfolio-rebuild`. The legacy root site and existing deployment workflow remain unchanged until the Astro build is verified. The generated `dist/` directory is not deployed yet.

## Phased roadmap

### Phase 0 — Research and inventory

- [x] Complete deep audit of `SarriaXD/blog_site`
- [x] Audit the current `haneyoshi.github.io` repository
- [x] Inventory current job experience, education, projects, assets, and resume
- [x] Identify what can be reused
- [x] Decide whether to refactor or rebuild

**Exit condition:** architecture choice, content inventory, and scope are approved.

### Phase 1 — Positioning and content

- [ ] Finalize target role and audience
- [ ] Write hero copy
- [ ] Write concise personal story
- [ ] Build MediCheck case-study content
- [ ] Define secondary-project presentation
- [ ] Rewrite experience and education descriptions
- [ ] Select supported skills only

**Exit condition:** all page content exists in draft form before visual implementation.

### Phase 2 — Information architecture and visual system

- [ ] Create page wireframe
- [ ] Define typography scale
- [ ] Define spacing system
- [ ] Define color system
- [ ] Define card, button, section, and navigation patterns
- [ ] Choose animation principles
- [ ] Design mobile-first layouts

**Exit condition:** every section has a clear purpose and approved layout.

### Phase 3 — Technical foundation

- [x] Create the `feature/portfolio-rebuild` branch
- [x] Establish Astro with TypeScript and build tooling
- [x] Create initial reusable layout and UI primitives
- [x] Set up the initial content/data structure
- [x] Add Astro and TypeScript checking
- [ ] Add linting and formatting when justified by the project needs
- [x] Confirm local checks and production build
- [ ] Migrate GitHub Pages deployment to the Astro `dist/` build

**Exit condition:** empty site shell builds successfully and the deployment migration is verified.

### Phase 4 — Core implementation

- [ ] Navigation and hero
- [ ] About section
- [ ] MediCheck case study
- [ ] Secondary project section
- [ ] Experience and education timeline
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

## Current focus

**Phase 3: Verify and review the Astro technical foundation before deployment migration.**
