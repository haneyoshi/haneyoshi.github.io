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

> A software developer with computer science and electrical engineering training who applies structured problem-solving, technical troubleshooting, and practical software development to real projects.

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

## Technical direction — provisional

Do not finalize until the current repository audit is complete.

Likely target:

- React or Next.js
- TypeScript
- component-based architecture
- responsive CSS or Tailwind CSS
- Framer Motion or lighter motion utilities
- accessible reduced-motion behavior
- optimized images
- automated deployment

GitHub Pages deployment constraints must be considered before choosing Next.js features. Static export may be required unless deployment moves to another host.

## Phased roadmap

### Phase 0 — Research and inventory

- [ ] Complete deep audit of `SarriaXD/blog_site`
- [ ] Audit the current `haneyoshi.github.io` repository
- [ ] Inventory current job experience, education, projects, assets, and resume
- [ ] Identify what can be reused
- [ ] Decide whether to refactor or rebuild

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

- [ ] Create a feature branch
- [ ] Establish project framework and build tooling
- [ ] Create reusable layout and UI primitives
- [ ] Set up content/data files
- [ ] Add linting, formatting, and type checking
- [ ] Confirm local and production builds
- [ ] Confirm GitHub Pages or alternative deployment

**Exit condition:** empty site shell builds and deploys successfully.

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

## Current focus

**Phase 0: Deep audit of `SarriaXD/blog_site`, followed by an audit of the current portfolio repository.**
