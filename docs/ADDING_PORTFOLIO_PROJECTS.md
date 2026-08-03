# Adding Portfolio Projects

## Purpose

Use this guide to add an approved future project while preserving the portfolio's existing structure, accessibility, performance, and professional positioning. It documents the established process for this Astro portfolio; it does not define a new architecture.

## Before implementation

- Confirm that the project is suitable and approved for public presentation.
- Verify the repository or public link, its access, and the project's current status.
- Identify the technologies the implementation actually supports and the evidence that demonstrates them.
- Review screenshots and other media for privacy, accuracy, accessibility, and relevance.
- Remove confidential information and private data. Do not use unsupported claims, invented metrics, or wording that overstates the project's maturity, completeness, adoption, or outcomes.

## Content preparation

Update the human-readable public copy in `docs/PORTFOLIO_CONTENT.md` before changing the site. Include:

- project name and current status;
- a concise summary;
- supported technical details and technologies;
- personal contribution, ownership, or collaboration context;
- implementation evidence;
- a verified public link; and
- applicable limitations or boundaries.

Keep every claim consistent with the actual implementation and current project status. Write for both quick review and readers seeking technical evidence.

## Implementation guidance

- Follow the existing Astro and TypeScript structure.
- Prefer existing components, semantic patterns, design tokens, responsive conventions, and ordinary CSS.
- Preserve logical DOM order and the mobile-first, single-column baseline. Add wider layouts only where the content benefits.
- Do not add React, Tailwind CSS, animation libraries, or other dependencies without a verified requirement and separate approval.
- Keep essential project content available without JavaScript or interaction.

## Project visuals

- Use optimized, relevant images that provide honest evidence of the project.
- Provide meaningful alternative text when an image conveys content; treat truly decorative images appropriately.
- Set explicit image dimensions to reduce layout shift.
- Do not publish unreviewed videos, private data, decorative assets presented as technical evidence, or images that imply greater completeness than the project has reached.

## Accessibility and interaction

- Maintain semantic landmarks, heading hierarchy, and meaningful link text.
- Ensure all interactions are keyboard accessible and retain visible focus states.
- Respect reduced-motion preferences.
- Verify readable contrast, narrow reflow, zoom behavior, and touch-target sizing.
- Communicate project status with explicit text, not color alone.

## Validation

Review the project at representative mobile, tablet, and desktop sizes. Also check keyboard use, narrow reflow, zoom, reduced motion where applicable, media presentation, and all public links.

Run:

```powershell
npm.cmd run check
npm.cmd run build
git diff --check
git status --short
```

Inspect the focused diff and confirm that no unrelated files changed. After an approved merge, verify public links and production behavior when applicable.

## Git workflow

- Work on a focused feature or documentation branch; do not work directly on `main`.
- Do not commit or push until the changes have been reviewed and approved.
- Stage explicit files, for example `git add src/pages/index.astro`, rather than using `git add .`.
- Keep production live and preserve legacy files until a separate cleanup is approved.

## Completion checklist

- [ ] Public suitability, privacy, status, links, technologies, and evidence verified
- [ ] Public copy updated first in `docs/PORTFOLIO_CONTENT.md`
- [ ] Claims, ownership, evidence, and limitations are accurate
- [ ] Existing Astro, TypeScript, component, token, CSS, and responsive patterns followed
- [ ] Visuals are reviewed, optimized, accessible, explicitly sized, and representative
- [ ] Semantics, keyboard access, focus, contrast, reduced motion, reflow, zoom, touch targets, and status text checked
- [ ] Mobile, tablet, and desktop layouts reviewed
- [ ] Checks and production build pass
- [ ] Focused diff and `git status --short` contain no unrelated changes
- [ ] Changes reviewed and approved before explicit staging, commit, push, or merge
- [ ] Public links and production behavior verified after merge when applicable
