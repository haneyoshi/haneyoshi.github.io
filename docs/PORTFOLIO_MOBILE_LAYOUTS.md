# Portfolio Mobile-First Layouts — Version 1

## 1. Purpose and scope

This document defines the approved Version 1 direction for mobile-first layout behavior, content order, reflow rules, width and spacing behavior, responsive composition changes, narrow-width navigation, and layout expectations across narrow, intermediate, and wide screens. It is a practical reference for later Astro and CSS work; it does not authorize implementation or application-code changes.

Mobile-first means beginning with the simplest readable one-column experience and adding layout complexity only when the available space and content justify it. The approved content, wireframe, typography, spacing, colors, component patterns, animation principles, accessibility requirements, and project positioning remain authoritative.

## 2. Global layout principles

- Keep one logical DOM order at every width. Reflow content without changing its reading or keyboard order.
- Let content drive layout changes. No essential information may exist only in a wide-screen composition.
- Do not visually reorder content when doing so would separate context from evidence or make navigation unpredictable.
- Never impose fixed heights on text-bearing regions or force unequal content into equal-height boxes.
- Prevent page-level horizontal scrolling. Long text, labels, controls, media, and metadata must wrap or shrink within their containers.
- Use the single approved centered main container with a `72rem` maximum width and `clamp(1rem, 4vw, 3rem)` page-edge padding.
- Keep focused introductions and calls to action near `52ch`; keep long-form project copy near `68ch`.
- Use only the approved spacing tokens: `space-2xs`, `space-xs`, `space-sm`, `space-md`, `space-lg`, `space-xl`, `space-2xl`, `space-section`, and `space-major`.
- Use `space-section` for standard section boundaries and `space-major` for major narrative transitions, including MediCheck to EchoTask. Do not create a competing layout or spacing system.
- Keep images, figures, and media responsive, legible, and within their containers while preserving meaningful proportions.
- Preserve approximately 44-by-44-pixel usable action targets and adequate separation for touch input.
- Introduce columns sparingly and collapse them before text, actions, or media become cramped.
- Treat enhanced compositions, disclosure navigation, sticky positioning, and motion as progressive enhancements. The page remains complete without them.
- Preserve visible focus, reduced-motion behavior, semantic heading order, zoom resilience, and access to all content at every width.

## 3. Responsive strategy

Responsive decisions are content-driven rather than tied to rigid device categories. No exact breakpoint values are approved. Introduce a breakpoint only where the content visibly needs to reflow, and test immediately around that point rather than assuming a named device width.

### Narrow state

- Use one column for all major regions and preserve the approved document sequence.
- Stack or wrap action groups only when intrinsic-width controls cannot remain comfortable and separate; keep the primary action first.
- Place media after the copy that establishes its context. Let media use the available container width without overflowing.
- Keep navigation visible and naturally wrapped when it remains compact and clear. A disclosure is only a conditional enhancement.
- Retain `space-section` and `space-major` for section rhythm, using approved compact gaps within components.
- Apply the `52ch` and `68ch` maximum measures even though the viewport will often be narrower.

### Intermediate state

- Keep one column where it remains clearer. Introduce two columns only for a proven relationship such as a copy-and-image pair, Experience and Education, or Skills groups.
- Allow action groups to become inline when targets and labels have sufficient room; otherwise retain wrapping or stacking.
- Keep explanatory copy adjacent to its related media and preserve the same DOM order used at narrow widths.
- Prefer wrapped navigation before disclosure. If the links and site name fit comfortably, the header may begin moving toward a horizontal composition.
- Use approved column gaps such as `space-xl` or `space-2xl`; do not reduce copy below a readable measure merely to retain columns.

### Wide state

- Use the `72rem` container to create balanced whitespace and stronger evidence presentation, not to stretch prose across the page.
- Permit restrained two-column compositions for Hero, selected MediCheck evidence, EchoTask, Experience and Education, and Skills when each column remains readable.
- Keep actions inline when they retain adequate target size, separation, and unambiguous priority.
- Allow project media to occupy more width than prose where interface detail benefits, while keeping text near `52ch` or `68ch` as appropriate.
- Use a compact horizontal header when the site name and complete navigation fit without crowding.
- Preserve the upper fluid range of approved section spacing without adding empty space that disconnects related content.

## 4. Header and navigation layout

The skip link is the first focusable element and becomes prominent when focused. The header then contains the site name followed by the primary links in this unchanged order: About, Projects, Experience, Skills, Contact. Ordinary anchors are the baseline, and the site name links to the page-top target.

At narrow widths, use a compact stacked or wrapped composition: the name occupies its natural line, and navigation links wrap below or beside it without clipping. Prefer natural wrapping while destinations remain clear and the header does not consume excessive height. Labels may wrap within comfortable targets, but no link may overlap or cause horizontal scrolling.

A disclosure menu is conditional, not mandatory. If later testing justifies one, its toggle is a real button with an accessible name, accurate expanded state, and a valid relationship to the controlled links. The links retain their normal order, keyboard access, and progressive-enhancement fallback.

As space grows, the same DOM order may form a compact horizontal layout with the site name first and navigation following or aligned opposite it. No scroll spy is required. A non-sticky header is the default; sticky positioning remains conditional on later testing. If adopted, it must not cover focused controls or anchor targets, and target spacing must keep headings visible.

## 5. Hero layout

The narrow Hero is one clear column: greeting and name, the `Software Developer` title, approved positioning copy, then primary and secondary actions. Identity and value statement always precede actions. The primary action remains first in both DOM and visual order.

Keep supporting copy near `52ch`. Actions remain intrinsic width and may wrap; stack them when labels or touch targets become cramped. The Hero does not require full viewport height, and no essential content is pushed below an artificial screen-height composition.

At wider widths, a two-column composition is allowed only when the primary text column remains dominant and readable. The secondary column may contain restrained supporting metadata or visual space already supported by the wireframe; it must not introduce a portrait, illustration, metric panel, technology wall, or unsupported asset. Decorative treatment must remain subordinate to the positioning copy.

## 6. About layout

About is text-led: heading, concise introduction, then approved supporting paragraphs in uninterrupted reading order. Keep focused introductory copy near `52ch` and longer paragraphs within a comfortable measure no wider than `68ch`.

Use the approved section rhythm to distinguish About from Hero and the `space-major` narrative transition into Projects. A wider two-column composition is optional only if the approved copy divides into meaningful related parts and neither column becomes narrow. Do not place readable text in a cramped column beside decoration, turn About into unrelated cards, or narrow the professional positioning to frontend work.

## 7. Projects section layout

Projects is one semantic section and keeps this order at every width:

1. Projects introduction
2. MediCheck
3. EchoTask

MediCheck and EchoTask remain separate articles or clearly headed subsections. They must not become a same-size card grid: MediCheck receives greater space, larger evidence, and deeper explanation, while EchoTask remains a compact secondary preview.

## 8. MediCheck layout

The narrow-screen case-study sequence is linear:

1. Projects introduction
2. MediCheck title
3. Educational-prototype, solo-project, and 2024 status metadata
4. Summary and technology information
5. Primary visual with its caption
6. Problem and approach
7. Relational-data and SQL evidence
8. Supporting screenshots immediately after the text they evidence, with meaningful captions
9. `View MediCheck on GitHub`

Context precedes the screenshot it explains, and related text, figure, and caption remain adjacent in reading order. Screenshots use the container width, retain useful detail, and never rely on fixed-height frames. Long-form explanation stays near `68ch`. Desktop-style visual alternation must not create a confusing narrow-screen sequence.

At wider widths, the opening summary and primary visual or selected copy-and-image evidence pairs may become two columns when both remain legible. Preserve DOM order so each pair returns naturally to context followed by evidence. Use `space-xl` between related groups, `space-2xl` between major evidence blocks and copy/media columns, and `space-major` before EchoTask.

Figures receive captions where they add meaning. The repository action remains descriptive and accessible. MediCheck earns the strongest visual weight through space, image size, and evidence depth—not exaggerated animation, status styling, or claims.

## 9. EchoTask layout

EchoTask remains a compact secondary project. Its narrow sequence is: title; active full-stack MVP, solo-project, and work-in-progress status; concise summary and technology; the exact visible label `Interface preview in development.`; an approved schematic or structural preview when available; supported relational-model, selected Flask-route, and React-prototype evidence; the pause note; then `View EchoTask on GitHub`.

Use one column at narrow widths. Keep explanatory copy adjacent to its schematic and never hide or truncate the status or pause note. At wider widths, copy and the restrained schematic may form two columns when useful, while the title and maturity context remain clear before the preview.

Use `space-lg` to `space-xl` internally, a smaller visual, and less accent density than MediCheck. The preview must not imitate a finished application screenshot or imply production readiness, completed integration, or other unsupported maturity.

## 10. Experience and education layout

Use two related blocks with a shared visual treatment. Experience comes before Education in DOM and visual order. Narrow screens stack the blocks with `space-xl` between them. Intermediate or wide screens may place them in two balanced columns using the approved `space-2xl` gap, but the pair collapses before either column becomes cramped.

Titles and dates wrap naturally. Do not use a decorative timeline, fixed heights, forced equal-height content, or CSS reordering.

## 11. Skills layout

Present the four approved evidence-supported groups in their established order:

1. Software development
2. Data and relational systems
3. Workflow analysis and automation
4. Working approach

Narrow screens use one column with `space-md` within each group and `space-xl` between groups. Wider screens may use two columns with `space-xl` gaps when evidence text remains readable. Headings stay connected to their evidence, and CSS must not reorder groups.

Do not create a dense badge wall, technology-logo grid, proficiency bar, rating, or percentage. Do not force groups to equal height.

## 12. Portfolio rebuild statement

Keep the rebuild statement concise and secondary to both projects. At narrow widths it is a simple stacked text block. At wider widths it may remain a focused text measure rather than expanding merely because space is available.

One quiet surface or bordered region is optional, using approved color and spacing patterns. Do not present the rebuild as a third full case study, introduce unsupported claims or metrics, or narrow the overall positioning to frontend-only work.

## 13. Contact layout

Contact closes the page with its heading, concise invitation, email action, LinkedIn action, and a plain unavailable résumé status if that status still applies. It does not need a form.

At narrow widths, actions wrap or stack in priority order when needed; the email action stays primary and closest to the invitation. At wider widths, actions may form an inline group. Preserve comfortable touch targets, descriptive labels, visible focus, and `space-md` between actions. Do not expose private contact information or create an excessive form-like layout.

## 14. Footer layout

The footer contains only approved public authorship, optional build information, and restrained confirmed links. It may stack at narrow widths and distribute or wrap content horizontally at wider widths. Use `space-2xl` before it, `space-lg` internally, and readable link spacing.

Avoid dense navigation duplication. Keep every link keyboard accessible and make the footer visually quieter than Contact.

## 15. Images, figures, and media

- Provide intrinsic dimensions or appropriate aspect-ratio handling to reduce layout shift.
- Constrain media to its container and serve responsive sizes without causing page-level horizontal scrolling.
- Preserve useful interface detail; do not shrink evidence into unreadable thumbnails.
- Use meaningful alternative text when the image conveys information and captions when context or evidence benefits. Decorative images use empty alternative text.
- Do not place important text only inside an image.
- Do not use fixed image heights that crop essential interface evidence. Reviewed crops are allowed only when they preserve meaning and honest context.
- Use optimized formats and Astro image support during later implementation where appropriate.

Final screenshots, frames, and crops are not selected by this specification.

## 16. Action and control layout

Primary and secondary action groups, repository links, mobile-navigation controls, and any future user-controlled image navigation preserve approximately 44-by-44-pixel usable targets with non-overlapping target space. Labels may wrap without clipping, and groups stack before they become cramped.

The primary action remains first. Full-width buttons are allowed where a narrow conversion-focused group benefits, but are not a universal rule. Focus indicators remain visible and unclipped. Controls stay in logical reading and keyboard order; interface-changing controls use real buttons, while destinations use descriptive links.

## 17. Responsive accessibility requirements

- Match DOM, visual, and reading order at every width; avoid CSS visual reordering.
- Preserve one logical heading hierarchy independent of visual composition.
- Keep keyboard order predictable and focus indicators visible and unclipped at all widths.
- Provide no hover-only content or control.
- Maintain sufficient target size and separation for touch, pointer, and enlarged interfaces.
- Support browser zoom and enlarged text without overlap, clipping, horizontal page scrolling, or content loss.
- Preserve all content and functionality at narrow widths.
- Keep reduced-motion behavior intact; layout, navigation, and comprehension never depend on animation.
- Ensure sticky elements, if later approved, do not cover headings, targets, content, or focus indicators.
- If disclosure navigation is used, keep it labeled, keyboard operable, assistive-technology compatible, state-synchronized, and progressively enhanced.

## 18. Layout validation matrix

| Region | Narrow layout | Wider enhancement | Key failure to avoid |
| --- | --- | --- | --- |
| Header/navigation | Compact name plus visible wrapped links or justified disclosure | Compact horizontal name and navigation | Overflow, excessive height, hidden links, or changed order |
| Hero | One text-led column; actions wrap or stack as needed | Optional restrained two-column composition | Full-viewport staging or unsupported visual content |
| About | One measured text column | Optional meaningful text composition | Cramped prose or unrelated cards |
| MediCheck | Linear context-then-evidence sequence | Selected readable copy/image pairs | Equal project weight, unreadable screenshots, or reordered evidence |
| EchoTask | Compact one-column preview with visible status | Restrained copy/schematic pair | Finished-product implication or hidden pause note |
| Experience/Education | Experience then Education, stacked | Two balanced columns | Timeline, cramped columns, or forced equal heights |
| Skills | Four evidence groups in one column | Two-column evidence grid | Badge wall, ratings, or CSS reordering |
| Portfolio rebuild statement | Concise stacked supporting block | Focused quiet surface or bordered region | Third-case-study weight or unsupported claims |
| Contact | Invitation followed by stacked/wrapped actions | Inline action group | Private data, cramped targets, or unnecessary form |
| Footer | Compact stacked or wrapped close | Quiet horizontal distribution | Dense duplicated navigation or competition with Contact |

## 19. Deferred decisions

- Exact content-driven breakpoint values
- Final screenshot selection and crops
- Exact Astro component APIs
- The signature interaction
- Final section-entry animation eligibility
- Whether mobile navigation ultimately needs disclosure
- Whether the header should become sticky
- Final media-viewer behavior
- Detailed cross-browser tuning

These matters belong to future implementation or polish and are not resolved by this Version 1 specification. No new dependency is justified by the approved layout direction.
