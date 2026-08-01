# Portfolio Color System — Version 1

## 1. Document purpose

This document defines the approved Version 1 color system for later visual-system and implementation work. It is a design specification, not source-code implementation.

The system supports professional presentation, restrained visual identity, readable project storytelling, strong accessibility, clear project hierarchy, maintainable semantic tokens, compatibility with the approved typography and spacing systems, and static GitHub Pages deployment.

## 2. Color principles

- Put content and evidence before decoration.
- Use a neutral foundation with controlled accent use and strong text readability.
- Never depend on color alone for meaning, status, selection, or action.
- Keep the number of hues restrained and give every semantic color a consistent meaning.
- Preserve sufficient contrast in every interactive state.
- Avoid an exaggerated tech-neon aesthetic, copied reference-site colors, and visual noise from gradients or application-style status palettes.
- Do not use color to make EchoTask appear more mature, brighter, or more prominent than MediCheck.

These principles reinforce the approved calm professional positioning and the hierarchy of MediCheck as the strongest case-study evidence, EchoTask as a secondary development preview, and the remaining sections as supporting context.

## 3. Version 1 mode decision

Version 1 uses light mode only. This phase includes no automatic dark-mode implementation, dark-mode toggle, duplicate dark palette, or dark-mode tokens. Dark mode may be reconsidered only after the light system has been implemented, reviewed, and tested.

## 4. Overall color direction

Use a warm-neutral foundation, charcoal-blue text, one controlled deep-blue accent, quiet blue-tinted supporting surfaces, and subtle gray dividers. The result should feel modern, calm, credible, and technical without becoming generic; polished without feeling corporate-heavy; and distinct from the reference site.

The page remains primarily light and continuous. Color establishes gentle grouping while typography, spacing, content depth, and visual scale carry the main hierarchy.

## 5. Exact core palette

| Role | Hex | Primary use |
| --- | --- | --- |
| Page background | `#F7F5F1` | Continuous warm-neutral canvas |
| Primary surface | `#FCFBF8` | Project visuals and selected content groups |
| Secondary surface | `#EFEEE9` | Quiet supporting bands and schematic areas |
| Primary text | `#18212B` | Headings and body text |
| Secondary text | `#3F4B57` | Supporting prose |
| Muted text | `#596673` | Metadata and captions |
| Subtle border | `#D6D3CC` | Low-emphasis grouping and dividers |
| Strong border | `#7A8692` | Meaningful boundaries and image frames |
| Primary accent | `#1F5F8B` | Links, actions, and restrained highlights |
| Primary accent hover | `#174B70` | Hover state |
| Primary accent active | `#103A58` | Active/pressed state |
| Accent-soft background | `#E4EEF5` | Selected and quiet evidence emphasis |
| Focus indicator | `#A33A00` | Keyboard focus only |
| Link | `#1F5F8B` | Default text links |
| Link hover | `#174B70` | Hovered text links |
| Selection background | `#BFD8EA` | Selected text background |
| Selection text | `#18212B` | Selected text foreground |

No core color is pure black or pure white. Light text on the primary accent, if a later pattern requires it, uses the primary surface color `#FCFBF8` and has verified contrast; this pairing does not predetermine button styling.

## 6. Neutral hierarchy

Use one mostly continuous `#F7F5F1` page background rather than alternating every section. Apply `#FCFBF8` selectively to project evidence, screenshots, or a small number of grouped content areas. Reserve `#EFEEE9` for quiet supporting regions such as EchoTask's schematic, the portfolio rebuild statement, or a restrained closing band.

Experience and Education blocks and Skills groups should normally remain on the page background or share one surface treatment; they must not each receive a different color. Contact may use a subtle surface shift to mark the close. The footer returns to the page background or continues the Contact surface without introducing a new neutral. Borders and dividers provide occasional grouping. Captions and metadata use muted text, while all essential explanations remain primary or secondary text.

## 7. Primary accent

The deep blue `#1F5F8B` is the single primary accent. It supports primary links, primary actions, selected navigation state, small evidence highlights, and restrained decorative details. Focus uses its own distinct token rather than reusing the accent.

The accent must not fill large page backgrounds, color long passages, appear on every heading or border, or mark all project metadata. Its depth supports a credible technical direction without the neon or cyan-on-black conventions of generic developer portfolios.

## 8. Supporting accent decision

Version 1 has no second strong accent. The blue-tinted `#E4EEF5` is a soft derivative of the primary accent, not a separate accent hue. It is limited to quiet selection, evidence emphasis, and schematic support. It must not create section branding, technology-specific colors, or a competing project identity.

The warm focus indicator is a functional accessibility color, not a decorative supporting accent.

## 9. Text colors

- Primary headings and normal body text use `#18212B`.
- Secondary supporting text uses `#3F4B57`.
- Metadata and captions use `#596673`; this is the lightest approved normal text color.
- Placeholder or temporary-status text uses at least `#3F4B57`, not a faint decorative gray.
- Disabled text, if later required, uses `#596673` with an additional non-color cue and an explicit unavailable state.

Project maturity labels are readable normal text, preferably `#3F4B57` or `#18212B`. Muted text must not carry essential instructions, core project explanations, or the only statement of project status.

## 10. Link colors and text-link behavior

Inline links use `#1F5F8B`; hover uses `#174B70`; active uses `#103A58`. Version 1 does not require a separate visited color because a visually divergent history state would add a second hue without a clear portfolio need. If visited styling is added later, it must remain underlined and pass the same contrast requirements.

Inline links are underlined by default so they remain identifiable without color. Underline offset and thickness are decided with later component patterns. Hover must change more than color alone, such as underline emphasis. Focus-visible uses the focus indicator described below. Navigation links and button-like actions may later use different shapes or text treatments, but they consume these same semantic color roles.

## 11. Interactive states

| State | Semantic color guidance |
| --- | --- |
| Default | `color-accent` for interactive emphasis; readable text remains present |
| Hover | `color-accent-hover` plus a non-color treatment appropriate to the future pattern |
| Active | `color-accent-active` plus a pressed or otherwise perceptible non-color treatment |
| Focus-visible | `color-focus`, visibly separate from hover and active |
| Disabled | `color-text-muted` plus an explicit unavailable cue; do not rely only on opacity |
| Selected/current | `color-accent-soft` with readable text plus structure, underline, marker, or accessible state |

Hover cannot be the only feedback. Focus-visible must remain obvious. Selected states must not depend on color alone, and every state must preserve readable text contrast.

## 12. Focus indicator

Use `#A33A00` as the exact focus-indicator color. Its warm hue is visually distinct from the blue interaction states and has at least 5.72:1 contrast against every approved base surface.

The indicator must remain visible against the page background, both surfaces, and near primary-accent elements. It must never be removed or reduced to a subtle shadow change. A later implementation may use a solid outline plus offset so the surface gap keeps it distinguishable beside accent-colored elements; no CSS is defined here.

## 13. Project hierarchy and color

MediCheck receives the strongest visual evidence and may use the primary accent in restrained links, evidence markers, or framing details. Its maturity remains communicated by the exact content, layout depth, screenshots, and educational-prototype label—not a green success treatment.

EchoTask uses the page neutral, secondary surface, or accent-soft background with less accent density. It retains the exact visible label `Interface preview in development.` It must not use warning or error colors because it is unfinished, use a brighter palette than MediCheck, or imply production readiness through polished status colors.

Do not assign brand colors to either project unless actual project branding later provides a reviewed reason.

## 14. Status and semantic colors

Version 1 does not introduce informational, success, warning, or error palette families. The portfolio is primarily informational and currently has no application-style alerts that justify them.

Project maturity uses normal text, headings, proximity, and explicit labels. Work-in-progress status never relies only on color. Error and success colors remain future token decisions unless a real component requires them. EchoTask's temporary state must never receive red warning styling. Any later semantic color addition requires a concrete need, accessible contrast, a non-color cue, and consistent meaning.

## 15. Borders and dividers

- Use `#D6D3CC` for subtle borders and dividers that organize nearby content without carrying meaning.
- Use `#7A8692` for stronger boundaries, image frames, and meaningful UI or graphic edges. Meaningful borders and graphic boundaries using `color-border-strong` meet the 3:1 non-text contrast target across all approved surfaces: 3.41:1 on the page background, 3.59:1 on the primary surface, 3.20:1 on the secondary surface, and 3.16:1 on the accent-soft surface.
- Use the strong border near focus-adjacent boundaries only when it does not compete with `#A33A00` focus.

Do not outline every content block. Prefer no border where whitespace, heading hierarchy, or a surface change already establishes grouping. Avoid dashboard-like grids of boxed sections.

## 16. Surface usage by section

| Page area | Version 1 surface guidance |
| --- | --- |
| Header | Page background; optional subtle divider only when orientation needs it |
| Hero | Page background with minimal accent details |
| About | Page background; no enclosing panel required |
| Projects introduction | Page background |
| MediCheck | Page background with selective primary surfaces behind visual evidence |
| EchoTask | Page background with a compact secondary-surface or accent-soft schematic |
| Experience and Education | Shared primary surface or page background; paired consistently |
| Skills | Page background; use spacing before borders |
| Portfolio rebuild statement | Secondary surface as a quiet supporting band or block |
| Contact | Primary surface or accent-soft treatment used sparingly to mark the close |
| Footer | Continue the closing surface or return to page background with one divider |

This creates a mostly continuous surface rhythm with selective quiet changes. Spacing and typography—not saturated blocks—provide the strongest emphasis.

## 17. Project visuals and screenshots

MediCheck screenshots retain their authentic interface colors and proportions. Do not recolor, tint, or apply overlays that misrepresent the application. Place screenshots on `#FCFBF8` or another verified neutral that preserves interface readability. Use `#7A8692` only when a frame is needed, and captions use `#596673` on an approved light background.

Browser or desktop-window framing may use approved neutrals and must remain subordinate to the screenshot. Decorative shapes use only neutral, accent, or accent-soft tokens and must not obscure evidence.

EchoTask's preview remains a low-detail schematic on `#EFEEE9` or `#E4EEF5`, with primary or secondary text and restrained blue connectors. It must remain clearly temporary, use the exact visible label, and avoid screenshot-like polish, fabricated application colors, or implied completed functionality.

## 18. Gradients and decorative color

Version 1 requires no gradient. Do not use large or animated gradients, rainbow or multi-hue effects, glow-heavy developer-portfolio styling, or purple-to-pink branding. A very subtle two-stop gradient may be considered later only for a documented structural purpose and after contrast review; it is not part of this approved palette.

## 19. Contrast requirements

- Normal text must have at least 4.5:1 contrast.
- Large text must have at least 3:1 contrast.
- User-interface components and meaningful graphics must have at least 3:1 contrast against adjacent colors.
- Focus indicators must remain clearly visible on every surface.
- Muted text must still pass the requirement applicable to its size and role.
- Hover and active states must preserve text and component contrast.
- Text over images requires a verified, controlled background treatment.
- Never place important text directly over uncontrolled screenshots.
- Color cannot be the only indication of status, selection, or action.

Verified Version 1 text pairs include primary text on the page at 14.94:1; secondary text on the page at 8.19:1; muted text on the page at 5.40:1 and on the primary surface at 5.68:1; accent links on the page at 6.29:1 and on the primary surface at 6.61:1; light text `#FCFBF8` on the accent at 6.61:1; focus on the page at 6.10:1 and on the secondary surface at 5.72:1; and selection text on its background at 11.02:1. The strong border has 3.41:1 contrast on the page background `#F7F5F1`, 3.59:1 on the primary surface `#FCFBF8`, 3.20:1 on the secondary surface `#EFEEE9`, and 3.16:1 on the accent-soft surface `#E4EEF5`. Values are rounded and must be rechecked during implementation with reliable tooling.

## 20. Selection and browser-level colors

Text selection uses `#BFD8EA` behind `#18212B`. The optional browser theme color is the page background `#F7F5F1`, keeping browser chrome aligned with the quiet foundation. A later native form-control accent may use `#1F5F8B`. This specification adds no browser-specific implementation code.

## 21. Semantic color tokens

| Semantic token | Exact value |
| --- | --- |
| `color-bg-page` | `#F7F5F1` |
| `color-bg-surface` | `#FCFBF8` |
| `color-bg-surface-subtle` | `#EFEEE9` |
| `color-text-primary` | `#18212B` |
| `color-text-secondary` | `#3F4B57` |
| `color-text-muted` | `#596673` |
| `color-border-subtle` | `#D6D3CC` |
| `color-border-strong` | `#7A8692` |
| `color-accent` | `#1F5F8B` |
| `color-accent-hover` | `#174B70` |
| `color-accent-active` | `#103A58` |
| `color-accent-soft` | `#E4EEF5` |
| `color-link` | `#1F5F8B` |
| `color-link-hover` | `#174B70` |
| `color-focus` | `#A33A00` |
| `color-selection-bg` | `#BFD8EA` |
| `color-selection-text` | `#18212B` |

These semantic names describe roles, not palette positions or individual components. No CSS declarations are included.

## 22. Token usage rules

- Components consume semantic tokens; do not repeatedly hardcode raw colors.
- Do not name tokens after sections, projects, or technologies.
- Do not introduce technology-logo colors or one-off values without evidence and a documented semantic need.
- Decorative color cannot replace structural hierarchy.
- State colors retain the same meaning across every component.
- Add a token only when an existing role cannot express a repeated, accessible requirement.
- Review any token addition against every approved surface and interactive state.

## 23. Accessibility review checklist

- [ ] Verify all actual foreground/background contrast pairs.
- [ ] Verify hover and active states preserve contrast and non-color feedback.
- [ ] Verify focus-visible on every surface and around accent elements.
- [ ] Verify links remain identifiable without color vision.
- [ ] Verify project statuses remain complete without color.
- [ ] Verify text-selection readability.
- [ ] Verify screenshots, frames, captions, and adjacent backgrounds.
- [ ] Verify browser zoom and text resizing.
- [ ] Verify high-contrast or forced-colors behavior where practical.
- [ ] Verify no content disappears when backgrounds, images, or decorative effects are unavailable.

## 24. Usage examples

- **Hero:** Keep the warm page background, primary text for the title and lead, and blue only for actions or a small evidence detail.
- **MediCheck:** Use primary text and generous neutral space; place authentic screenshots on the primary surface with restrained strong frames and the strongest action emphasis.
- **EchoTask:** Use a smaller secondary-surface or accent-soft schematic, readable status text, and lower accent density while retaining `Interface preview in development.`
- **Experience and Education:** Place both paired blocks on the same neutral treatment with primary headings, secondary body text, and minimal subtle boundaries.
- **Skills:** Keep groups on the continuous page background or one shared surface; use text hierarchy instead of technology colors or badge palettes.
- **Contact:** A primary or accent-soft surface may mark the closing invitation; email and LinkedIn links use the link and focus tokens.
- **Footer:** Use a compact neutral close with muted supporting text that still passes contrast and a subtle divider only if needed.

## 25. Out-of-scope decisions

This task does not finalize dark mode, card styling, button styling, navigation styling, border radii, shadows, component layout, animation, the signature interaction, screenshot selection, EchoTask final artwork, CSS implementation, or Astro source changes.

## 26. Recommended next Phase 2 task

After the color system is reviewed, define card, button, section, and navigation patterns.
