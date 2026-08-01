# Portfolio Component Patterns — Version 1

## 1. Purpose and scope

This document defines the approved Version 1 reusable visual and interaction patterns for YuShan's portfolio. It is a practical reference for later implementation with Astro components, TypeScript where data structures require it, semantic HTML, ordinary responsive CSS, and browser-native behavior.

These patterns extend the approved content, wireframe, typography, spacing, and color systems. They are design direction, not finished application code, and this document does not authorize implementation during this task.

## 2. Shared principles

- Establish hierarchy through semantic structure, typography, spacing, content depth, and visual scale before adding decoration.
- Keep related elements consistent without making projects, entries, skills, and actions look identical.
- Put readable content and factual evidence first. Decoration must not obscure, replace, or exaggerate evidence.
- Use restrained borders, surfaces, accent color, and elevation. Do not turn every section into a floating panel.
- Provide distinct default, hover, focus-visible, active, current, and expanded states wherever those states apply.
- Preserve logical DOM and keyboard order at every width; core content and links remain usable without JavaScript wherever practical.
- Reflow content before introducing breakpoint-specific composition changes. Do not use fixed heights for text-bearing components.
- Keep motion optional and compatible with reduced-motion preferences; no component depends on motion for meaning.
- State project maturity in visible text. Visual polish must not imply completion, deployment, adoption, or production readiness.

The result should remain professional and lightweight while supporting software development, full-stack development, application support, systems analysis, technical analyst, and related roles. The component system must not frame the entire site as a frontend-only portfolio.

## 3. Card patterns

“Card” describes a reusable content grouping, not a requirement for a raised box. Static content containers must not gain pointer, hover, focus, or link affordances. A whole card is clickable only when it has one unambiguous destination and can be implemented as one valid, descriptive link without nested interactive controls.

### 3.1 Featured project or case-study card

- **Purpose:** Present MediCheck as the dominant, detailed case study and strongest available project evidence without overstating it.
- **Required content:** project title; explicit `Educational desktop software prototype` status; solo-project and 2024 metadata; supported summary; problem and approach; relational-data evidence; technology; meaningful visual evidence when approved; and `View MediCheck on GitHub` action.
- **Optional content:** additional reviewed screenshots and captions, internal subsection links when a useful visible destination exists, and supporting evidence sections. Do not add a live-demo action or unsupported claims.
- **Hierarchy:** Projects heading and introduction precede the article; title and status establish context before the primary visual; problem, approach, and evidence follow in a readable sequence; the repository action closes or clearly accompanies the evidence. Give MediCheck more space, larger visual evidence, and stronger action emphasis than EchoTask, but no success styling or production claims.
- **Semantic structure:** use an `<article>` or a clearly headed project subsection inside the Projects `<section>`. Use sequential headings, ordinary text for status and metadata, `<figure>` and `<figcaption>` for meaningful visuals, and a descriptive `<a>` for the repository.
- **Spacing:** use `space-xl` between related groups and `space-2xl` between major evidence blocks, with `space-major` separating MediCheck from EchoTask. Long-form copy stays within `68ch`; visuals may use the full `72rem` container when legibility requires it.
- **Surface, border, and elevation:** keep the article primarily on `color-bg-page`. Use `color-bg-surface` selectively behind screenshots or evidence. Use `color-border-strong` only for meaningful frames and `color-border-subtle` for quiet grouping. No default shadow is required; if later optical separation requires elevation, it must be subtle, static, and subordinate to evidence.
- **Interaction:** the case-study container is static. Only its explicit actions are interactive. If a future compact variant has one destination and makes the whole card a link, it must expose a descriptive accessible name, a visible `color-focus` indicator, and the same affordance to keyboard and pointer users; it must not contain nested links or buttons.
- **Narrow screens:** preserve the approved sequence: context before the primary image, then each explanation with its supporting image and caption. Stack copy and visuals before either becomes cramped. Actions may stack while retaining their priority.
- **Content length:** allow genuine case-study depth without fixed height, truncation, hidden essential content, or equal-height pressure. Break long explanations into meaningful headed groups rather than shrinking type.

### 3.2 Secondary project or work-in-progress card

- **Purpose:** Present EchoTask as a credible secondary development preview with less visual weight than MediCheck.
- **Required content:** project title; solo-project, active full-stack MVP, and work-in-progress context; the exact visible label `Interface preview in development.`; supported summary; verified current implementation evidence; pause note; supported technology; and `View EchoTask on GitHub` action.
- **Optional content:** the approved low-detail structural diagram and concise architecture or workflow explanation. Do not add a live demo, fabricated interface detail, or production-readiness cues.
- **Hierarchy:** place title, maturity label, and pause context near one another. Follow with summary, schematic or current evidence, technology, and repository action. Use the same project-title role as MediCheck but a smaller visual, more compact content, and lower accent density.
- **Semantic structure:** use a separate `<article>` or headed subsection within Projects. Render status as normal selectable text, not image-only content. Use a figure only if the schematic conveys information; decorative diagram elements need no alternative text.
- **Spacing:** use `space-lg` to `space-xl` internally. Keep the presentation polished but intentionally more compact than MediCheck.
- **Surface, border, and elevation:** use `color-bg-page` for the article and `color-bg-surface-subtle` or `color-accent-soft` for the preview. Status text uses readable primary or secondary text, never a warning or error color. A subtle border may group the preview; no shadow or screenshot-like chrome is required.
- **Interaction:** the container remains static and the repository link is explicit. If a future compact whole-card link is justified, it follows the same single-destination, focus, keyboard, and no-nested-controls rules as the featured pattern.
- **Narrow screens:** use one column in logical order, keep the status visible near the title, and place explanatory text adjacent to the schematic it explains.
- **Content length:** allow normal wrapping and modest supporting detail, but keep it materially shorter than MediCheck. Never truncate the status or pause note.

### 3.3 Experience or education entry

- **Purpose:** Supply professional and academic context without suggesting a long chronology or competing with project evidence.
- **Required content:** a sequential heading, date or completion metadata, and approved concise description. Education also includes the institution; experience must remain public-safe.
- **Optional content:** no action is required. Add a link only when a confirmed destination materially supports the entry.
- **Hierarchy:** entry title first, metadata second, then supporting text. Experience precedes Education in visual and DOM order.
- **Semantic structure:** use two headed content blocks within the Experience and Education `<section>`. A list is appropriate only if the entries form an actual list; do not use a timeline solely for decoration.
- **Spacing:** use standard heading-to-copy relationships, `space-md` internally, `space-2xl` between desktop columns, and `space-xl` when stacked.
- **Surface, border, and elevation:** both entries share the same treatment: normally `color-bg-page` or one shared `color-bg-surface`. Use whitespace first and a subtle border only if grouping remains unclear. Do not give each entry a different color or raised-card treatment.
- **Interaction and focus:** entries are static. Only any justified descendant link receives interactive states and focus.
- **Narrow screens:** stack Experience before Education; do not reorder visually with CSS.
- **Content length:** allow dates, titles, and enlarged text to wrap. Do not use fixed heights or force equal copy length.

### 3.4 Skill-evidence item

- **Purpose:** Connect a concise capability group to visible, supported evidence without ratings or unsupported proficiency claims.
- **Required content:** one of the four approved group titles and one or two evidence statements.
- **Optional content:** a descriptive link to relevant visible page evidence when useful.
- **Hierarchy:** group heading followed by plain-language evidence. Technology names remain within supporting sentences rather than becoming a badge wall.
- **Semantic structure:** use a headed group in a list or grouped section, according to the surrounding content. Use links only for real destinations.
- **Spacing:** use `space-md` internally and `space-xl` between items or grid cells.
- **Surface, border, and elevation:** prefer the continuous page background and spacing. One shared surface or restrained divider is acceptable; individual floating cards, technology colors, and shadows are not.
- **Interaction and focus:** the item is static. Evidence links retain their own visible focus and descriptive labels.
- **Narrow screens:** change a multi-column arrangement to a single-column sequence in approved evidence order before text becomes cramped.
- **Content length:** let evidence wrap naturally; do not crop text, equalize heights, or reduce font size.

## 4. Button and link-action patterns

Use only the variants below. Labels describe destinations or outcomes: `View projects`, `Contact me`, `View MediCheck on GitHub`, `View EchoTask on GitHub`, and `Send an email` are preferable to vague or repeated labels such as “Click here” or “Learn more.”

Use `<a>` for navigation, downloads, email, and external destinations. Use `<button>` for an action that changes the current interface, such as opening or closing a mobile menu. Do not style one semantic element as the other merely for convenience.

All action targets should provide a minimum usable area of approximately 44 by 44 CSS pixels, either through the control box or surrounding non-overlapping target space. Wrapped labels must not reduce target height or overlap neighboring actions.

### 4.1 Primary action

- **Use:** the single highest-priority destination in a local action group, such as `View projects`, `View MediCheck on GitHub`, or `Send an email`.
- **Do not use:** for every link, multiple equally emphasized actions in one group, unavailable destinations, or actions unsupported by approved content.
- **Appearance:** highest action emphasis, using `color-accent` with verified `color-bg-surface` text when filled, or an equally clear restrained treatment using approved tokens. Keep the shape and weight consistent across sections.
- **States:** default is plainly actionable; hover uses `color-accent-hover` plus a border, underline, or other structural change; focus-visible uses a distinct `color-focus` outline with offset; active uses `color-accent-active` plus a perceptible pressed treatment; a disabled `<button>` retains readable text and an explicit unavailable cue, not opacity alone.
- **Responsive behavior:** keep intrinsic width when practical; allow full width in narrow, conversion-focused groups such as Contact or when stacking improves target separation.

### 4.2 Secondary action

- **Use:** a valid alternative of lower priority, such as `Contact me` beside `View projects` or LinkedIn beside email.
- **Do not use:** as decorative duplication of a nearby navigation link or when the hierarchy is actually equal.
- **Appearance:** quieter than the primary action, normally using accent text with a visible border or another non-filled structural boundary. It must remain distinct from ordinary inline links.
- **States:** provide the same visible hover, focus-visible, and active clarity as the primary action. A disabled state applies only to a real `<button>`, never an `<a>`.
- **Responsive behavior:** wrap or stack after the primary action in the same DOM order. It may become full width when the group requires it, not as a site-wide rule.

### 4.3 Text link

- **Use:** lower-emphasis standalone navigation or supporting destinations, including optional LinkedIn and restrained footer links.
- **Do not use:** for interface state changes or as an ambiguous generic call to action.
- **Appearance:** accent-colored text with a persistent underline or another equally explicit non-color affordance. It has less visual weight than button-like actions.
- **States:** hover strengthens the underline or another structural cue while using `color-link-hover`; focus-visible uses the focus outline; active uses `color-accent-active` and a perceptible structural change.
- **Responsive behavior:** allow wrapping without clipping; preserve a comfortable target when the link functions as a standalone action.

### 4.4 Inline content link

- **Use:** a destination embedded in prose where its label makes sense in the sentence.
- **Do not use:** for primary calls to action, icon-only controls, or repeated generic wording.
- **Appearance and states:** underline by default. Hover changes underline emphasis as well as color; focus-visible remains distinct; active remains readable. Do not remove the underline solely for visual quietness.
- **Responsive behavior:** wrap naturally with surrounding text and never create horizontal scrolling.

### 4.5 Icon-supported link

- **Use:** an optional enhancement when a familiar icon adds information, such as communicating an external destination. The text label remains present.
- **Do not use:** when the icon is decorative, duplicates obvious text, or becomes the only understandable label. Icon-only links are not part of the default action set.
- **Appearance and states:** inherit the underlying primary, secondary, or text-link hierarchy. Keep icon and label together with approved inline spacing; state changes apply to the complete target.
- **Responsive behavior:** prevent the icon from separating ambiguously from its label; allow the complete label to wrap safely.

External links use descriptive labels and should be communicated consistently, through visible wording such as `on GitHub`, an accessible external-link cue, or both. If a new tab is deliberately used, disclose that behavior; opening a new tab is not required. Never use disabled links: omit an unavailable link or present non-interactive text such as an explicit unavailable résumé status.

## 5. Section patterns

Every major content area follows this reusable order when its content supports each part:

1. A semantic `<section>` associated with its heading, or a more specific landmark where appropriate.
2. An optional eyebrow or category label that adds context rather than repeating the heading.
3. A section heading at the next logical level.
4. Optional concise introductory copy, normally constrained to `52ch`.
5. The main content region in logical reading order.
6. An optional descriptive section-level action when the wireframe identifies a useful destination.

Use the centered `72rem` maximum page container and `clamp(1rem, 4vw, 3rem)` page-edge padding. Long-form project content stays near `68ch`; focused introductions stay near `52ch`. Use `space-section` for normal major boundaries and `space-major` for About-to-Projects, MediCheck-to-EchoTask, or another approved major narrative transition. Left-align long-form copy. Centered alignment is limited to concise content, such as a focused closing invitation, when reading remains comfortable.

Background and grouping choices follow content needs:

- **Default page background:** the normal choice for Hero, About, Projects framing, Skills, and other areas already separated by headings and whitespace.
- **Subtle alternate surface:** use selectively for EchoTask's schematic, the portfolio rebuild statement, or Contact's closing shift. Do not alternate every section.
- **Inner bordered region:** use for meaningful screenshot frames, a schematic, or a content group whose boundary would otherwise be unclear. Prefer `color-border-subtle`; reserve `color-border-strong` for meaningful visual or interface boundaries.
- **No additional container decoration:** use when typography, spacing, and proximity already establish the group. This is preferred for most prose, skill groups, and section introductions.

Alternating copy-and-visual layouts are permitted only when evidence and readable measures support them; they are not a decorative rule. Keep DOM order coherent and do not require alternating left-right projects. At narrow widths, stack content before columns become cramped, preserve the approved order, and retain section spacing. The complete reading flow remains Hero, About, Projects with MediCheck then EchoTask, Experience and Education, Skills, portfolio rebuild statement, Contact, and Footer. Sections must read as one page, not isolated dashboard panels.

## 6. Navigation patterns

### 6.1 Site header and internal section navigation

- Use a header landmark containing the `YuShan` name link to `#top` and a `<nav>` with an accessible name.
- Use the exact primary labels and destinations in this order: `About` (`#about`), `Projects` (`#projects`), `Experience` (`#experience`), `Skills` (`#skills`), and `Contact` (`#contact`). MediCheck and EchoTask do not become top-level navigation items.
- Use ordinary anchor links so destinations work without JavaScript. Keep the displayed order and DOM order identical.
- A separate primary header action is not required because Contact already appears in navigation. If later testing justifies one, it remains subordinate and must not create confusing duplicate meaning.
- Keep the desktop header compact and horizontal when space permits. Links may wrap before a mobile disclosure becomes necessary.

### 6.2 Current-section indication

A current indicator is optional. Do not add scroll-spy behavior for Version 1: the approved plan and wireframe do not require it, and native anchor navigation does not reliably establish a continuously current section. If a current page or location is known, use `aria-current` with the correct value plus an underline, marker, weight, or shape change; never rely on color alone. Do not apply `aria-current` speculatively to several links.

### 6.3 Mobile navigation

- Prefer always-visible wrapped links when they remain understandable and compact. If space requires a disclosure, use a real `<button>` with an accessible name, `aria-expanded`, and `aria-controls` referencing the menu container.
- With JavaScript unavailable, keep the navigation links exposed wherever practical. Enhancement may collapse them only after the control is operational.
- Opening places the menu in the normal keyboard sequence; do not move focus automatically unless the chosen disclosure behavior creates a genuine focus-management need.
- Closing returns focus to the toggle when closure would otherwise leave focus in hidden content. Escape closes an expanded menu and returns focus to the toggle.
- Selecting an in-page link navigates to the destination and closes the expanded menu. Focus must not be trapped; the destination remains understandable through its heading and normal document flow.
- Pointer, touch, and keyboard users receive the same destinations and state information. The toggle supports Enter and Space through native button behavior.

### 6.4 Skip link, scrolling, and position

The first focusable control is `Skip to main content`, targeting the main landmark. It becomes visually prominent on focus and uses the approved focus color.

A non-sticky header is the acceptable default. Use sticky positioning only if later testing shows improved orientation without obscuring anchored headings, consuming excessive narrow-screen space, or causing distracting scroll transitions. Account for header overlap at in-page targets if sticky positioning is adopted.

Native instant scrolling is sufficient. Optional smooth scrolling must not be required for navigation and must be disabled or reduced when the user prefers reduced motion. Header visibility, menu state, current state, and access to content must not depend on scroll animation or JavaScript-heavy behavior.

## 7. Interaction-state matrix

| State | Links | Buttons | Navigation items | Interactive cards | Status indicators |
| --- | --- | --- | --- | --- | --- |
| Default | Descriptive label and visible link affordance | Clear action hierarchy and boundary | Readable destination label | Link purpose and full-card affordance are explicit | Visible status text |
| Hover | Color plus underline or structural change | Color plus border, surface, or elevation change | Color plus underline or marker | Subtle boundary or surface change; no essential reveal | Not applicable |
| Focus-visible | Distinct `color-focus` indicator | Distinct `color-focus` indicator | Distinct `color-focus` indicator | Indicator encloses the complete linked area | Not applicable unless independently interactive |
| Active / pressed | Active color plus structural feedback | Active color plus pressed feedback | Active feedback during activation | Perceptible activation feedback | Not applicable |
| Current / selected | Only where a destination is current; non-color cue | Only for a genuine toggle or selectable button | `aria-current` when accurate plus non-color cue | Only for a genuinely selectable collection | Not applicable; status is not selection |
| Disabled | Never use a disabled link; omit it or use plain status text | Native disabled behavior plus readable unavailable cue | Avoid disabled navigation destinations | Not applicable to linked cards | May state unavailability in text without pretending to be a control |
| Expanded / collapsed | Not normally applicable | Mobile-menu toggle uses `aria-expanded` | Menu visibility matches toggle state | Not currently justified | Not applicable |
| Work in progress | Destination label does not imply completion | Action label does not imply a live product | Not applicable | EchoTask retains its explicit maturity copy | Exact visible `Interface preview in development.` label; neutral treatment, not warning styling |

Hover must never be the only way to reveal essential information. Status indicators are informational text, not controls, unless a future approved interaction gives them a real action.

## 8. Responsive rules

- Start with content reflow and natural wrapping before applying breakpoint-specific redesign.
- Use the breakpoint approach already implied by the approved mobile-first design system; this document introduces no new breakpoint values.
- Never use fixed card heights for text-bearing patterns or force unequal content into equal-height boxes.
- Allow long titles, metadata, navigation labels, and action labels to wrap without clipping, overlap, or page-level horizontal scrolling.
- Stack actions when they cannot preserve comfortable target size and separation. Full-width actions are appropriate for narrow conversion-focused groups, not mandatory everywhere.
- Preserve `52ch` focused and `68ch` long-form readable measures, and stack copy-and-visual layouts before copy becomes too narrow.
- Maintain approximately 44-by-44-pixel targets and adequate separation at every width.
- Keep images, schematics, and frames within their containers while preserving meaningful intrinsic proportions.
- Keep mobile navigation destinations in the same order and ensure the open or wrapped state is immediately understandable.
- Preserve logical DOM order, heading order, project evidence sequence, and Experience-before-Education order across layouts.

Detailed mobile-first section compositions remain deferred to the approved mobile-layout task.

## 9. Accessibility requirements

- Use native semantic elements: landmarks, `<nav>`, `<main>`, `<section>`, `<article>`, headings, links, buttons, lists, and figures according to their meaning.
- Keep one `h1` and a logical, sequential heading structure independent of visual type size.
- Make every interactive element reachable and operable by keyboard in a predictable DOM order.
- Show a distinct `color-focus` focus-visible indicator on every approved surface; never remove focus without an accessible replacement.
- Use only approved foreground and background tokens in verified combinations. Normal text requires at least 4.5:1 contrast; large text and meaningful component boundaries require at least 3:1.
- Pair every state color with text, underline, border, shape, marker, or another non-color cue.
- Give links labels that identify their destination or outcome without relying on surrounding layout alone.
- Give any exceptional icon-only control an accessible name. Prefer visible text when space permits, and hide purely decorative icons from assistive technology.
- Remove, simplify, or avoid nonessential motion under `prefers-reduced-motion`; navigation and content remain complete without animation.
- Use `aria-current` only for a link whose current relationship is accurate, normally with `page` or `location` as appropriate.
- If mobile navigation uses disclosure, its button uses `aria-expanded` and `aria-controls` with a valid control relationship; the visible menu state must agree with the attribute.
- Avoid redundant roles and unnecessary ARIA when native HTML already communicates the correct name, role, state, and keyboard behavior.

## 10. Pattern inventory

| Implementation-neutral pattern | Version 1 status | Scope note |
| --- | --- | --- |
| Section wrapper | Required for initial implementation | Shared container, page padding, and section rhythm |
| Section heading | Required for initial implementation | Heading plus optional eyebrow and introduction |
| Project card | Required for initial implementation | Supports distinct featured and secondary presentations without forcing identical layouts |
| Experience / education entry | Required for initial implementation | Paired static content blocks |
| Skill-evidence item | Required for initial implementation | Four supported groups with ordinary evidence text |
| Action link | Required for initial implementation | Primary, secondary, standalone text, and inline link hierarchy |
| Button | Required for initial implementation | Needed only if mobile navigation uses a disclosure control |
| Status label | Required for initial implementation | Explicit project maturity, including EchoTask's exact preview label |
| Site navigation | Required for initial implementation | Header links, mobile treatment, and skip link |
| Figure with caption | Conditional | Use for approved screenshots or an informative EchoTask schematic |
| Interactive whole-card link | Conditional | Only for one unambiguous destination with no nested controls |
| Primary header action | Conditional | Add only if later layout testing justifies duplication of Contact |
| Current-section tracker / scroll spy | Not currently justified | Static anchors provide sufficient Version 1 navigation |
| Timeline | Not currently justified | Approved content uses paired Experience and Education blocks |
| General-purpose card library | Not currently justified | The small set of content patterns does not require an abstract UI library |

## 11. Deferred decisions

The following belong to later approved tasks and are not resolved here:

- animation principles and exact motion behavior
- detailed mobile-first layouts for each section
- the one signature interaction
- final MediCheck screenshot selection, framing, crops, and mockup treatment
- final EchoTask schematic artwork and later screenshot treatment
- implementation-specific Astro component boundaries, properties, data types, and APIs

