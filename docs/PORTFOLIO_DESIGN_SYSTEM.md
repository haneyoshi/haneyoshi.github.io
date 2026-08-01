# Portfolio Typography and Spacing System — Version 1

## 1. Document purpose

This document defines the approved Version 1 typography and spacing foundations for later visual-system and implementation work. It is a design specification, not source-code implementation.

The system supports professional presentation, readable project storytelling, responsive layouts, accessible text, maintainable CSS, and a restrained visual hierarchy. Public wording remains governed by `docs/PORTFOLIO_CONTENT.md`; page structure and reading order remain governed by `docs/PORTFOLIO_WIREFRAME.md`.

## 2. Design principles

- Put readability before decoration.
- Create clear hierarchy with a small, reusable set of type styles.
- Use generous but controlled spacing to express content relationships.
- Apply consistent rhythms across the approved single-page sequence.
- Start with mobile sizes and scale only where added space improves comprehension.
- Keep typography proportionate to the evidence; do not exaggerate experience or project maturity.
- Avoid excessive display text, overly compressed layouts, and unnecessary visual complexity.
- Do not make layout success depend on an exact viewport height.
- Give MediCheck more visual breathing room than EchoTask without creating disconnected empty space.

## 3. Font strategy

Version 1 will use one high-quality system sans-serif stack. The exact approved value for `font-family-sans` is `system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif`. The exact approved value for `font-family-mono` is `ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, "Liberation Mono", "Courier New", monospace`; use it only for technical identifiers. No external runtime font service or font download is required.

This choice minimizes page weight, layout shift, privacy concerns, dependency complexity, licensing uncertainty, and GitHub Pages deployment risk. It also avoids blocking text while a web font loads. The repository currently contains a provisional Inter-first source token, but no local font files were found. The later implementation should revise that token to the approved system stack rather than assume Inter is installed or download it as part of this task.

Use the same primary sans-serif family throughout Version 1. Do not add a decorative display face. A self-hosted font can be reconsidered only in a later reviewed task with a demonstrated visual need, confirmed license, and measured performance impact.

## 4. Font roles

| Role | Family | Purpose |
| --- | --- | --- |
| Body text | Primary system sans | Paragraphs, lists, project explanations, and supporting copy |
| Headings | Primary system sans | Hero, sections, projects, and content-group hierarchy |
| Navigation | Primary system sans | Short orientation labels with medium weight |
| Buttons and links | Primary system sans | Concise actions and inline links; distinguish links through more than weight alone |
| Metadata | Primary system sans | Project status, date, role, and technology information as normal readable text |
| Captions | Primary system sans | Short explanations associated with project visuals |
| Technical identifiers | Platform monospace stack, only when needed | Literal anchors, filenames, tokens, or code identifiers; never normal prose |

## 5. Typography scale

Use this exact Version 1 scale. Only the display, section-title, project-title, and body-large roles scale fluidly; other roles remain stable to reduce complexity.

| Token | Intended use | Mobile | Larger screens / range | Line height | Weight | Limits |
| --- | --- | --- | --- | --- | --- | --- |
| `font-size-display` | Sole hero title | `2.5rem` | `clamp(2.5rem, 6vw, 4.5rem)` | `1.05` | 700 | Hero only; two lines is a normal-layout target, not an accessibility constraint |
| `font-size-section` | Major section titles | `2rem` | `clamp(2rem, 3.5vw, 2.75rem)` | `1.15` | 700 | Reuse across primary sections; do not create section-specific sizes |
| `font-size-project` | MediCheck and EchoTask titles | `1.75rem` | `clamp(1.75rem, 3vw, 2.25rem)` | `1.2` | 700 | Project titles only; visual weight may differ through spacing, not a new size |
| `font-size-group` | Internal subsection, paired-block, and Skills group titles | `1.25rem` | `1.25rem` | `1.3` | 600 | Use for compact content hierarchy, not ordinary labels |
| `font-size-body-lg` | Hero lead and selected section introductions | `1.125rem` | `clamp(1.125rem, 1.5vw, 1.25rem)` | `1.55` | 400 | Reserve for concise introductory copy |
| `font-size-body` | Default prose | `1rem` | `1rem` | `1.65` | 400 | Default for project narrative and normal content |
| `font-size-body-sm` | Supporting prose and compact secondary details | `0.9375rem` | `0.9375rem` | `1.6` | 400 | Do not use for primary explanations |
| `font-size-meta` | Dates, status, role, and technology metadata | `0.875rem` | `0.875rem` | `1.5` | 500 | Keep as readable text; avoid repetitive badge treatment |
| `font-size-caption` | Screenshot captions | `0.875rem` | `0.875rem` | `1.5` | 400 | Never reduce further; keep adjacent to its visual |

## 6. Heading hierarchy

Semantic heading levels follow the wireframe and remain separate from visual roles:

| Page content | Semantic role | Visual token |
| --- | --- | --- |
| `Software Developer` | Sole `h1` | `font-size-display` |
| About, Projects, Experience and Education, Skills, portfolio rebuild, Contact | Primary section headings at the next logical level | `font-size-section` |
| MediCheck and EchoTask | Project headings inside the Projects section | `font-size-project` |
| Internal project subsections | Next sequential heading level | `font-size-group` |
| Experience and Education block headings | Sequential headings within their section | `font-size-group` |
| Skills group headings | Sequential headings within Skills | `font-size-group` |
| Contact heading | Primary section heading | `font-size-section` |
| Footer text | Not a heading unless it introduces a real subsection | `font-size-body-sm` |

Do not choose heading levels to obtain a desired visual size. Apply a visual token to the correct semantic heading instead, without changing the wireframe hierarchy.

## 7. Body copy and readable measure

- Set default prose at `1rem` with `1.65` line height.
- Use body-large only for the concise hero lead and selected section introductions.
- Constrain long-form project explanations to `68ch` maximum.
- Use a narrower `52ch` measure for hero, About, Contact, and other focused introductory blocks.
- Paragraphs beside visuals must retain a practical minimum width; stack the layout before copy becomes narrow or produces excessive short lines.
- Keep long-form paragraphs left aligned. Do not center or justify them.
- Separate consecutive paragraphs with `space-md`; use larger content-group spacing for a new idea or subheading.
- Keep captions at `0.875rem`, close to their image, and generally within the image width.
- Keep metadata at `0.875rem` with normal wrapping. Status and technology must read coherently without becoming a dense tag wall.
- Avoid artificially sparse prose layouts that make concise approved content occupy excessive vertical space.

## 8. Font weights and emphasis

Use four weight roles at most:

- `font-weight-regular` — `400`: body copy, captions, and supporting text.
- `font-weight-medium` — `500`: navigation, links where appropriate, metadata, and short labels.
- `font-weight-semibold` — `600`: group titles and restrained emphasis.
- `font-weight-bold` — `700`: display, major section, and project titles where clear hierarchy is required.

Do not place several nearly indistinguishable weights next to one another. Use italics sparingly for conventional emphasis, not long passages. Meaningful status, link purpose, or hierarchy must remain understandable through wording, structure, and placement rather than font weight alone.

## 9. Typography responsiveness

- Small mobile screens use every mobile minimum in the scale; no text falls below the specified metadata and caption sizes.
- Larger mobile screens retain the same base sizes while fluid display and heading roles may begin scaling.
- Tablets and desktop allow the four fluid roles to grow within their defined caps.
- Wide desktop retains the maximum sizes and gains whitespace, not larger typography.
- Let the hero title wrap naturally without forcing nonbreaking text; keep the title within its `4.5rem` cap. Two lines is the normal-layout target, but enlarged text, narrow screens, longer text, or localization may produce additional lines and must never be clipped or forced into a smaller size.
- Allow section and project titles to wrap without clipping, overlap, or manual line breaks that fail at other widths.
- Do not size text with viewport units alone; every fluid value has a `rem` minimum and maximum.
- Navigation and action labels remain readable and may wrap when needed. Do not shrink them to preserve one line.
- Metadata wraps as normal text and maintains meaningful separators or list structure across lines.
- Long project titles and localized or user-enlarged labels must not create horizontal scrolling.
- Support browser zoom and text resizing without using fixed-height text containers.

## 10. Spacing principles

Spacing communicates relationship and hierarchy rather than filling empty space arbitrarily. Related items use smaller intervals; new groups and sections use progressively larger intervals. The same relationship should use the same token throughout the page.

- **Inline spacing:** separation within a line, such as an icon from a label or metadata items.
- **Control spacing:** space between interactive targets and between their content and bounds.
- **Component internal spacing:** padding and gaps inside a future navigation, project, or contact component.
- **Content-group spacing:** separation among a heading, prose, metadata, actions, and visuals that form one idea.
- **Section spacing:** separation between adjacent major sections.
- **Page-edge spacing:** the responsive gutter that protects content from viewport edges.

Touch usability and readable grouping take priority over fitting more controls into a row. Mobile reduces large intervals but preserves the relative hierarchy between inline, component, group, and section spacing.

## 11. Base spacing unit and scale

Use a `0.25rem` base unit and this exact Version 1 scale:

| Token | Value | Typical use |
| --- | --- | --- |
| `space-2xs` | `0.25rem` | Very small inline alignment adjustment |
| `space-xs` | `0.5rem` | Closely related inline items and metadata |
| `space-sm` | `0.75rem` | Compact control or caption relationships |
| `space-md` | `1rem` | Paragraph separation and standard internal gap |
| `space-lg` | `1.5rem` | Heading-to-copy and action-group relationships |
| `space-xl` | `2rem` | Component padding and compact content groups |
| `space-2xl` | `3rem` | Large content groups and mobile section rhythm |
| `space-section` | `clamp(4rem, 8vw, 6rem)` | Standard major-section separation |
| `space-major` | `clamp(5rem, 10vw, 8rem)` | Major narrative transition or featured-project breathing room |

Use tokens rather than one-off values. A custom spacing value is permitted only when intrinsic media geometry, accessible control sizing, or verified optical alignment cannot be expressed by this scale; document the reason and do not create a reusable token for a single accidental case.

## 12. Page container and horizontal padding

Use one centered page container with a maximum width of `72rem`. Apply responsive page-edge padding through one `page-padding-inline` value: `clamp(1rem, 4vw, 3rem)`. This starts at `1rem`, grows through larger mobile and tablet layouts, and stops at `3rem` on desktop.

Within the main container:

- Long-form text uses a `68ch` readable sub-container.
- Focused introductory text uses a `52ch` narrow sub-container.
- Copy-and-visual compositions share the container but must preserve the copy measures.
- Project visuals may use the full container width when their evidence needs legibility.
- Background treatments may extend full width later, but their content remains constrained and padded.
- Wide screens add outer margin after the `72rem` cap rather than spreading text or grids farther apart.

## 13. Section spacing

| Relationship | Version 1 guidance |
| --- | --- |
| Header to hero | Use `space-2xl` minimum; increase only when the header is non-sticky and the hero remains visible without viewport-height assumptions. |
| Hero internal spacing | `space-sm` from eyebrow to title, `space-lg` from title to lead, and `space-lg` from lead to actions. |
| Hero to About | Use `space-section`; avoid a dramatic empty screen. |
| About to Projects | Use `space-major` to mark the transition from context to primary evidence. |
| MediCheck internal case study | Use `space-xl` between related groups and `space-2xl` between major evidence blocks; this is the page's most generous internal rhythm. |
| MediCheck to EchoTask | Use `space-major` while retaining the shared Projects-section context. |
| EchoTask internal spacing | Use `space-lg` to `space-xl`; polished but more compact than MediCheck. |
| EchoTask to Experience and Education | Use `space-section`. |
| Skills groups | Use `space-lg` within a group and `space-xl` between stacked groups; grids use `space-xl` gaps. |
| Portfolio rebuild statement | Use `space-xl` internal spacing and standard `space-section` separation; keep it visually lighter than projects. |
| Contact | Use `space-section` before it and `space-xl` among invitation and actions. |
| Footer | Use `space-2xl` above it and `space-lg` internal spacing; keep the close compact. |

## 14. Component and content-group spacing

| Content relationship | Guidance |
| --- | --- |
| Navigation links | Use at least `space-lg` horizontally on desktop; use `space-md` vertically when stacked. |
| Hero actions and button groups | Use `space-sm` to `space-md` between controls; preserve the same order when stacked. |
| Control content | Use enough internal space to support comfortable touch targets; final control styling remains out of scope. |
| Metadata lines | Use `space-xs` between closely related items and `space-sm` between separate metadata groups. |
| Heading and body copy | Usually `space-lg`; compact group headings may use `space-sm` or `space-md`. |
| Paragraph groups | Use `space-md` between paragraphs and `space-xl` before a new conceptual group. |
| Project image and caption | Use `space-sm`, keeping the caption visually attached to the image. |
| Project copy and visual | Use `space-xl` when stacked and `space-2xl` as the desktop column gap. |
| Experience and Education blocks | Use `space-xl` between stacked blocks and `space-2xl` as the desktop pair gap. |
| Skills evidence groups | Use `space-md` internally and `space-xl` between groups or grid cells. |
| Contact actions | Use `space-md`; keep the primary email action closest to the invitation. |
| Footer links | Use `space-md` horizontally and `space-sm` vertically when wrapping. |

These values define relationships, not final component appearance.

## 15. Mobile spacing behavior

Mobile is the baseline. `space-section` and `space-major` remain the default tokens for full section boundaries and major narrative transitions on mobile and larger screens; their fluid values already provide the approved responsive range. Normal major-section boundaries continue to use `space-section` on mobile. Reserve `space-2xl` for explicitly compact relationships identified by this specification: header-to-hero separation, footer separation, and compact internal transitions that are not boundaries between full major sections.

- Stack hero and project actions when they cannot retain comfortable target spacing in one row.
- Preserve `space-sm` to `space-md` separation between touch targets.
- Keep screenshot captions directly beneath their images with `space-sm` separation.
- Use `space-xl` between a project visual and the next explanatory group.
- Stack Experience before Education with `space-xl` between blocks.
- Stack Skills groups with `space-xl` between them.
- Give mobile navigation links clear vertical separation without creating a full screen of decorative whitespace.
- Keep inline and caption relationships constant; allow page padding, large content-group gaps, section spacing, and major spacing to scale responsively.
- Do not compress heading-to-copy relationships or project evidence merely to shorten the page.
- Do not add oversized empty gaps that extend scrolling without improving hierarchy.

## 16. Desktop spacing behavior

Desktop increases section rhythm and column gaps while retaining the same content relationships and DOM order. Use the upper range of `space-section` and `space-major` only where adjacent sections remain visually connected.

Copy-and-visual layouts use `space-2xl` between columns and preserve readable copy measures. Experience and Education may form paired blocks with the same gap. Skills may form a restrained grid using `space-xl` gaps. MediCheck receives the most breathing room; EchoTask remains more compact.

Do not require alternating left-right project layouts. Prefer consistent evidence placement over decorative variation. If a composition appears empty or disconnected, reduce the gap or constrain the grouping rather than enlarging typography or adding unsupported content.

## 17. Accessibility requirements

- Keep default body text at least `1rem`; metadata and captions remain at least `0.875rem`.
- Support text resizing to at least 200% and normal browser zoom without clipped, overlapping, or missing content.
- Use the specified line heights and adequate paragraph spacing for readable prose.
- Keep long-form text near `68ch` or less and focused text near `52ch`.
- Do not convey meaning only through size, weight, capitalization, position, or another typographic treatment.
- Make links visibly distinguishable from surrounding text; the later color system must supply accessible contrast and focus treatment.
- Preserve comfortable control spacing and touch separation when labels wrap.
- Prevent text, metadata, and controls from causing horizontal page scrolling.
- Support longer labels and enlarged text without fixed-height containers.
- Keep typography and spacing independent of animation and reduced-motion settings.
- Preserve logical DOM and reading order at every layout width.
- Avoid all-uppercase treatment for sentences or long labels.
- Do not use thin font weights for body content.
- Do not require exact viewport height for content visibility or navigation.

## 18. Recommended design tokens

Token names describe roles rather than specific elements so the system stays reusable.

| Category | Recommended tokens and exact mappings |
| --- | --- |
| Font family | `font-family-sans` → `system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif`; `font-family-mono` → `ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, "Liberation Mono", "Courier New", monospace` |
| Font size | `font-size-display`, `font-size-section`, `font-size-project`, `font-size-group`, `font-size-body-lg`, `font-size-body`, `font-size-body-sm`, `font-size-meta`, `font-size-caption` |
| Line height | `line-height-tight` → `1.05`; `line-height-heading` → `1.2`; `line-height-body` → `1.65`; `line-height-compact` → `1.5` |
| Font weight | `font-weight-regular`, `font-weight-medium`, `font-weight-semibold`, `font-weight-bold` |
| Text measure | `measure-text`, `measure-text-narrow` |
| Spacing scale | `space-2xs`, `space-xs`, `space-sm`, `space-md`, `space-lg`, `space-xl`, `space-2xl`, `space-section`, `space-major` |
| Relationship aliases | `gap-inline` → `space-xs`; `gap-control` → `space-md`; `gap-component` → `space-xl`; `gap-content-group` → `space-2xl`; `gap-section` → `space-section` |
| Page geometry | `page-padding-inline`, `container-max`, `container-text`, `container-text-narrow` |

The section-title role retains its approved `1.15` line height directly from the typography table; it does not require another global token. Other role-specific values in that table may likewise remain direct assignments when none of the four shared tokens applies. Relationship aliases reference the core spacing scale and never introduce new numeric values. Implementation may map existing provisional token names to these approved roles, but this document does not provide CSS.

## 19. Usage examples

- **Hero:** Use the display role for the sole `h1`, body-large within the narrow text measure for the approved lead, and `space-lg` before the ordered action group.
- **MediCheck case study:** Use a section heading for Projects, the project role for MediCheck, body text within `68ch`, and the most generous content-group spacing around primary and supporting evidence.
- **EchoTask preview:** Reuse the project and metadata roles, but use more compact `space-lg` to `space-xl` group spacing so its secondary maturity remains clear.
- **Experience and Education:** Use group titles inside paired blocks, body or body-small supporting text, and `space-2xl` between desktop columns or `space-xl` when stacked.
- **Skills groups:** Use the group-title role, concise body text, and a consistent `space-xl` grid or stack gap without ratings or badge-heavy metadata.
- **Contact:** Use the section-title role, approved copy within the narrow measure, and `space-xl` before clearly separated email and LinkedIn actions.

## 20. Out-of-scope decisions

This specification does not finalize:

- Colors
- Borders
- Shadows
- Card styles
- Button appearance
- Navigation appearance
- Image framing
- Animation
- Signature interaction
- Final component layouts
- Exact CSS breakpoint implementation
- Font-file acquisition

## 21. Recommended next Phase 2 task

After this typography and spacing specification is reviewed, define the Version 1 color system.
