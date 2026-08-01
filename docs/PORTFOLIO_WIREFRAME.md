# Portfolio Page Wireframe — Version 1

## 1. Document purpose

This document defines the Version 1 page-level information architecture for YuShan's single-page portfolio. It specifies content hierarchy, reading flow, responsive behavior, and structural accessibility requirements so later design and implementation work can proceed from one approved structure.

This is a Phase 2 structural reference. It does not define final colors, typography values, detailed component styling, animation implementation, or Astro source code. The repository rebuild plan confirms that the current focus is Phase 2: defining the information architecture and visual system from the approved Version 1 content before implementing the complete page.

## 2. Approved page section order

The complete page will use this exact order:

1. Site header and primary navigation
2. Hero
3. About
4. Featured project — MediCheck
5. Secondary project — EchoTask
6. Experience and education
7. Skills supported by evidence
8. Portfolio rebuild statement
9. Contact
10. Footer

MediCheck and EchoTask are two parts of one Projects destination even though each receives its own project article or subsection. This order introduces YuShan's direction, adds concise professional context, leads with the primary project with the strongest available evidence, accurately distinguishes the work-in-progress project, and then supplies experience, education, and skills as supporting proof. The lighter portfolio-rebuild statement adds current frontend evidence before the page closes with a direct contact opportunity.

## 3. Global navigation and anchors

| Label | Exact target | Destination |
| --- | --- | --- |
| About | `#about` | About section |
| Projects | `#projects` | The single Projects section containing MediCheck and EchoTask |
| Experience | `#experience` | Experience and education section |
| Skills | `#skills` | Evidence-based skills section |
| Contact | `#contact` | Contact section |

`#projects` identifies one semantic Projects section containing two project articles or project subsections: MediCheck, optionally identified by `#medicheck`, and EchoTask, optionally identified by `#echotask`. They do not receive separate top-level navigation links. The site name or restrained wordmark links to `#top`, which requires an actual page-top target in the later implementation.

If a current-section indicator is added later, it must supplement rather than replace the link label and must not depend on color alone. Navigation follows DOM order, works by keyboard, and has clearly visible focus treatment. A first-focusable “Skip to main content” link targets the main content. Mobile navigation must expose the same destinations in the same order with adequately sized controls. A simple always-visible or native disclosure treatment is preferred; all section anchors and essential content must remain usable when JavaScript is unavailable. Smooth scrolling, if later used, is optional and must respect reduced-motion preferences.

## 4. Section-by-section wireframe specification

| Section | Purpose and hierarchy | Actions and emphasis | Desktop / mobile concept | Density, anchor, and accessibility |
| --- | --- | --- | --- | --- |
| Header | Orient the visitor with YuShan's name and primary destinations. | Name returns to top; navigation is the emphasis. A contact action is optional and subordinate. | Desktop: compact horizontal row. Mobile: compact name plus accessible navigation control or wrapped links. | Keep every label concise. Anchor: `#top`. Header landmark, logical focus order, visible focus, and keyboard-operable mobile behavior. |
| Hero | Establish identity, role, and broad positioning immediately. Hierarchy: greeting/name, `Software Developer`, approved supporting copy, actions. | Primary: `View projects`. Secondary: `Contact me`. LinkedIn may appear as a lower-emphasis link. | Desktop: focused text-led composition with restrained supporting visual space. Mobile: one column with actions stacked or wrapped in priority order. | Keep all hero copy concise. Anchor: page top. One `h1`, descriptive links, no résumé action. |
| About | Bridge the positioning statement to evidence. Hierarchy: heading, concise introduction, optional supporting paragraph. | No primary action is required; an inline route to experience may be added only if useful. | Desktop: readable text block with controlled measure. Mobile: the same text in uninterrupted document order. | Initial paragraph stays concise; supporting background may expand. Anchor: `#about`. Do not expose employer identity or confidential details. |
| MediCheck | Provide the dominant, detailed project case study inside the Projects section. Hierarchy: Projects introduction, status metadata, project title and summary, primary visual, problem/approach, relational-data evidence, supporting visuals, technology and action. | Primary: `View MediCheck on GitHub`. An internal case-study jump is optional only if supported by visible content. | Desktop: generous image-and-copy composition followed by a limited evidence sequence. Mobile: exact sequence defined in Section 16. | Status and summary stay concise; supported problem, approach, and data explanation may expand. Parent anchor: `#projects`; optional project anchor: `#medicheck`. Meaningful captions and alt text; prototype status in text. |
| EchoTask | Show a credible secondary project article or subsection without implying equal maturity. Hierarchy: title, status, summary, temporary visual, current implementation evidence, pause note, technology and action. | Primary: `View EchoTask on GitHub`; no live demo. Visually quieter than MediCheck. | Desktop: smaller text-and-preview block. Mobile: exact sequence defined in Section 16. | Status stays concise; workflow and architecture may expand modestly. Parent anchor: `#projects`; optional project anchor: `#echotask`. Temporary label must be text, not image-only. |
| Experience and education | Provide professional and academic context without competing with projects. Hierarchy: heading, experience block, education block. | No primary action. | Desktop: two paired blocks, experience first. Mobile: stacked in the same order. | Headings and dates stay concise; public-safe role context may expand slightly. Anchor: `#experience`. Use semantic headings and readable date text. |
| Skills | Connect demonstrated capability to evidence. Hierarchy: heading, short introduction, four evidence groups. | No primary action; evidence references may point to relevant visible sections when useful. | Desktop: balanced grid of groups. Mobile: single-column groups in evidence order. | Labels stay concise; supporting evidence may expand. Anchor: `#skills`. Avoid ratings and icon-only meaning. |
| Portfolio rebuild | Make the portfolio itself transparent supporting evidence. Hierarchy: compact heading, short statement, concise implementation themes. | A repository link is optional only if a confirmed public link is approved later; no action is required for Version 1. | Desktop: narrow, visually light band or block. Mobile: simple text block. | Keep shorter than either project. Optional anchor: `#portfolio-rebuild`. Ongoing status must be stated in text. |
| Contact | Provide the final clear conversion point. Hierarchy: the approved Contact heading and invitation from `PORTFOLIO_CONTENT.md`, email action, LinkedIn support. | Primary: `Send an email`. Secondary: LinkedIn. | Desktop: focused closing panel. Mobile: single column with full-width or comfortably sized actions. | Keep the approved invitation concise. Anchor: `#contact`. Explicit email label, visible focus, clear external-link behavior. |
| Footer | Close with authorship and optional build note. | Optional restrained LinkedIn and confirmed project repository links. | Desktop and mobile: compact, wrapping safely as needed. | Keep concise. Footer landmark; no private information or résumé link. |

## 5. Header and navigation

Use a compact header with `YuShan` as text or a restrained wordmark. It supports orientation and should not compete with the hero. On desktop, place the name link first and the five navigation links in a horizontal group. A separate Contact button is not necessary because Contact already appears in the concise primary navigation; if visual exploration later includes one, it must not overpower or duplicate the navigation's meaning.

On mobile, preserve the name first and expose a compact navigation treatment. If a disclosure button is used, give it an accessible name, communicate expanded state, keep it keyboard operable, and ensure links remain reachable without JavaScript through progressive enhancement. Recommend a sticky header only if later layout testing shows that it improves orientation without reducing usable viewport space; non-sticky is an acceptable default.

Focus order is skip link, name link, navigation links in displayed order, then main content. Interactive targets must be comfortably sized for touch and separated enough to prevent accidental activation. Focus indicators remain visible against every header state. Any header transition or scroll response must be restrained, avoid being essential, and be disabled or simplified under reduced-motion preferences.

## 6. Hero hierarchy and actions

The hero uses this hierarchy:

1. Eyebrow/name: `Hello, I'm YuShan.`
2. Sole page `h1`: `Software Developer`
3. Approved lead: `I build practical software and approach technical problems with experience spanning IT operations, data reporting, workflow analysis, and automation.`
4. Primary action: `View projects` → `#projects`
5. Secondary action: `Contact me` → `#contact`
6. Optional lower-emphasis LinkedIn link using the approved profile URL

The action wording intentionally adapts the approved “View my work” direction to the requested, more specific Projects anchor without changing the positioning. There is no résumé action because a public-safe résumé is unavailable. GitHub should not compete with the two section actions; project-specific repository links appear with their evidence.

The eyebrow, title, lead, and two core actions must remain concise and immediately visible on desktop and mobile. Do not add a large technology-logo wall, inflated expertise claim, or frontend-only/full-stack-expert framing.

## 7. About section

About is a concise narrative bridge, not a second hero or full biography. Its initial visible paragraph should communicate the Bachelor’s degree in Applied Computer Science, current IT Operations Analyst experience, and interest in the relationship among software, data, systems, and operational workflows.

A second short paragraph may expand on breaking down technical problems, organizing requirements, practical implementation, continued full-stack learning, and the broad range of software and systems opportunities described in the approved content. That supporting detail should remain visible in the normal reading flow for Version 1; it need not be hidden behind an interaction.

The section must preserve broad technical positioning and must not identify the employer, internal systems, confidential work, or unapproved responsibilities and outcomes.

## 8. Projects section hierarchy

Projects is one semantic section identified by `#projects`. It opens with the approved Projects introduction from `PORTFOLIO_CONTENT.md` and contains two project articles or project subsections in this order: MediCheck, optionally identified by `#medicheck`, followed by EchoTask, optionally identified by `#echotask`.

MediCheck is the dominant featured case study and the primary project with the strongest available evidence. It receives the larger visual, more page space, deeper explanation, and strongest action treatment while remaining clearly described as an educational software prototype. EchoTask follows as a smaller, text-led work-in-progress presentation with an explicitly temporary preview. Its status and pause note appear near its title rather than being buried. The difference in space, visual scale, detail, and action emphasis must distinguish the strength and depth of the currently available evidence without implying that MediCheck is production-ready or that every planned feature is complete.

The projects should share enough structural patterns to scan as a set, but they must not appear equally mature or receive equal visual weight.

## 9. MediCheck visual placement

Present MediCheck accurately as an **educational desktop software prototype**, **solo project**, **2024**, built with **Python and MySQL**. Its evidence centers on clinic workflow management, relational database design, and SQL-based retrieval across historical patient, symptom, diagnosis, and medication records.

Use one strong primary screenshot or composed application view near the project introduction. Follow it with a limited sequence of supporting screenshots only where they clarify a workflow or database-related explanation. Each image needs a short visible caption stating what the image demonstrates. Selection is based on factual evidence, interface readability, and relevance—not quantity.

On desktop, the opening copy and primary visual may share a balanced composition, provided neither becomes cramped. Supporting images align with the explanatory text they substantiate. On mobile, copy establishes context before the primary image, and each later screenshot immediately follows the explanation and caption it supports. Use a consistent aspect-ratio family or presentation frame, preserve intrinsic proportions, serve responsive image sizes, and never shrink full interfaces into unreadable thumbnails. Crops may focus attention only when they preserve honest context.

Alternative text should identify the relevant interface state and what is visible when that information is not already conveyed by adjacent prose. Captions explain significance; alt text describes the image. Purely decorative framing receives empty alternative text. Do not select unreviewed filenames or assume every legacy image will be reused. Final screenshot selection from the preserved legacy portfolio remains a later review item.

Primary action: `View MediCheck on GitHub`. A secondary internal case-study navigation action is justified only if the final visible case-study structure has a useful destination. Do not add a live demo. Never imply clinical validation, clinical use, machine learning, treatment effectiveness, production use, or healthcare transformation.

## 10. EchoTask temporary visual treatment

Present EchoTask accurately as a **solo project**, **active full-stack MVP**, and **work in progress** using **React, Flask, SQLAlchemy, and SQLite**. EchoTask remains active, but active implementation is temporarily paused while the portfolio rebuild is the priority. Describe the verified relational models for buildings, work areas, users, attendance, snow logs, and supply requests; selected Flask routes; and React supply-selection prototype. Do not imply abandonment or current production readiness.

Use a polished but restrained development-preview panel. The recommended Version 1 visual is a low-detail structural diagram showing the verified system areas and their broad relationship to the React prototype, Flask routes, and relational data layer. It must carry the exact visible label:

> Interface preview in development.

The panel is intentionally schematic rather than screenshot-like. Avoid fabricated controls, dashboards, metrics, users, workflows, data, or visual detail that could suggest a finished product. Essential facts and the temporary status remain selectable page text outside the image; decorative diagram elements receive appropriate empty alternatives, while an informative diagram receives concise alt text plus an adjacent text explanation.

Give EchoTask less space and a smaller visual than MediCheck while maintaining aligned typography and polished spacing. Primary action: `View EchoTask on GitHub`. Do not add a live-demo action or imply production readiness, completed authentication, deployment, full integration, comprehensive testing, or adoption.

## 11. Experience and education structure

Use two restrained paired blocks rather than a timeline. A timeline would imply a longer chronology than the approved public content supports; paired blocks provide direct context without competing with the projects.

The first block contains:

- `IT Operations Analyst`
- `June 2025–present`
- The approved public-safe themes: IT operations, data reporting, workflow analysis, automation, and technical problem-solving

The second block contains:

- `Bachelor’s degree in Applied Computer Science`
- `University of Winnipeg`
- `Completed 2023`
- A concise note about the foundation in software development, computing concepts, and structured problem-solving

On desktop, place the blocks side by side only when both retain comfortable text width, with experience first in visual and DOM order. On mobile, stack experience before education. Do not name the employer or add confidential work details, unconfirmed responsibilities, or outcomes.

## 12. Skills supported by evidence

Use four compact evidence-based groups:

| Group | Concise evidence connections |
| --- | --- |
| Software development | Python and MySQL through MediCheck; JavaScript, React, and Flask through EchoTask; Astro and TypeScript through the portfolio rebuild. |
| Data and relational systems | MediCheck relational design and SQL retrieval; EchoTask models using SQLAlchemy and SQLite. |
| Workflow analysis and automation | Public-safe current-role themes; translating operational workflow ideas into EchoTask's data structures and application responsibilities. |
| Technical operations and problem-solving | IT Operations Analyst experience, Applied Computer Science education, independent projects, and iterative portfolio work. |

Each group begins with a short capability label and follows with one or two evidence statements. Technology names should appear only where the source content supports them. Keep the default scan concise; supporting evidence may expand in ordinary visible prose or through clear links to page sections. Do not use proficiency levels, years, badges, percentages, star ratings, progress bars, or unsupported tools.

## 13. Portfolio rebuild statement

Place a short, visually lighter statement after Skills and before Contact. Its purpose is to make the portfolio itself transparent evidence of ongoing frontend engineering and maintainable organization without competing with MediCheck.

The statement may name the approved implementation concerns: Astro and TypeScript, component-based architecture, responsive CSS, semantic HTML, accessible interactions, reduced-motion support, optimized images, and GitHub Pages static deployment. Describe the work as an ongoing portfolio rebuild. Do not frame it as client work or claim business outcomes. Keep it to a short paragraph plus a concise evidence list, or an equivalently compact block.

## 14. Contact and footer

Contact is the final clear conversion point. Use the approved Contact heading and complete invitation from `docs/PORTFOLIO_CONTENT.md`; do not restate or independently finalize the role-list wording in this wireframe. Keep that approved copy concise in presentation and give it clear visual priority above the contact actions.

The primary action is `Send an email`, linked to `mailto:pokemonbotno001@gmail.com`. Show the address as adjacent visible contact information or use an accessible label that clearly identifies email as the action. LinkedIn is the secondary external destination. Relevant confirmed GitHub project links belong primarily with their projects and may be repeated in the footer only when the footer remains restrained.

All links need visible keyboard focus. External links use descriptive labels; if they open a new tab, communicate that consistently in accessible text and avoid excessive repeated announcements. Opening in the same tab is the simpler default. The footer contains `Designed and built by YuShan.` and may add `Built with Astro and TypeScript.` It may also contain restrained navigation or approved social/project links.

Do not include a home address, phone number, immigration information, sensitive personal email, employer identity, confidential work information, or unavailable résumé link.

## 15. Desktop reading flow

The desktop experience moves from a compact header into a focused hero, then gradually increases evidence depth. About is a short transition. MediCheck creates the page's largest content interval and strongest image-to-copy relationship. EchoTask repeats enough project structure to remain understandable but uses less space, a smaller schematic visual, and lighter action emphasis. Paired experience and education blocks restore a compact rhythm; Skills provides a scannable evidence grid; the rebuild statement acts as a brief supporting note; Contact creates a distinct closing point.

Body copy uses controlled line length rather than stretching across the viewport. Project visuals may sit beside introductory copy when both remain readable, while detailed explanations and supporting screenshots use consistent alignment. Layout alternation is not required; consistency of evidence placement is preferred over decorative zig-zagging. Calls to action appear at the hero, at the end of each project, and at Contact, with distinct labels and without repeating the same generic button throughout.

A quick scan should reveal role, project names and statuses, current experience, degree, evidence groups, and contact action. Deeper reading follows the same top-to-bottom order without requiring overlays or hidden core content.

## 16. Mobile reading flow

Mobile uses one logical linear sequence with no horizontal page scrolling. The header presents the name and accessible navigation without obscuring content. Hero actions appear in this exact order: `View projects`, then `Contact me`, followed by any lower-emphasis LinkedIn link. Controls may stack when wrapping would weaken their hierarchy.

MediCheck uses this exact mobile content sequence:

1. Projects section introduction
2. MediCheck title
3. `Educational desktop software prototype · Solo project · 2024` status metadata
4. Concise project summary and technology
5. Primary screenshot with its caption
6. Problem and approach explanation
7. Relational-data and SQL retrieval explanation
8. Each selected supporting screenshot immediately after the text it evidences, with a caption
9. `View MediCheck on GitHub`

EchoTask uses this exact mobile content sequence:

1. EchoTask title
2. `Full-stack MVP · Solo project · Work in progress` status metadata
3. Concise project summary and technology
4. `Interface preview in development.` label
5. Temporary structural diagram or development-preview panel
6. Current relational models, selected Flask routes, and React prototype evidence
7. Statement that development is paused while the portfolio rebuild is the priority
8. `View EchoTask on GitHub`

Text establishes context before each project's first visual. Images scale within their container, preserve aspect ratio, and may use focused responsive crops only when meaning remains intact. Do not force desktop side-by-side layouts into narrow widths. Maintain readable line lengths, clear section spacing, comfortable touch targets, and action placement directly after the content each action relates to. DOM order must match visual order, and no essential explanation may exist only in a desktop arrangement or image.

## 17. Content density rules

### Must remain concise

- Navigation labels
- Hero eyebrow, title, and lead
- Hero and project action labels
- Section introductions
- Project maturity and status labels
- Project technology summaries
- Experience and education headings and dates
- Contact invitation
- Portfolio rebuild statement
- Footer

### May expand

- MediCheck problem and approach
- MediCheck relational-data and SQL retrieval explanation
- Carefully selected MediCheck outcomes or lessons when supported by evidence
- EchoTask workflow and architecture explanation
- Skills evidence
- Public-safe experience description after review
- Image captions when they add evidence not already clear from nearby text

Expansion should use well-structured visible prose, subheadings, lists, and captions within the normal document flow. Progressive disclosure may supplement long supporting detail later, but essential context, project status, evidence, and actions must remain directly accessible. Accordions are not required and must not become the only route to core content.

## 18. Accessibility requirements for page structure

- Use one logical `h1`: `Software Developer`.
- Use sequential heading levels that reflect sections and project subsections; do not skip levels for appearance.
- Use semantic header, navigation, main, section, and footer landmarks where appropriate, with distinguishable labels if landmarks repeat.
- Provide a first-focusable skip link to the main content.
- Use descriptive link text such as `View MediCheck on GitHub`, not ambiguous repeated labels.
- Make all navigation and controls keyboard operable, with visible focus indicators that are not clipped.
- Keep DOM order aligned with visual and spoken reading order at every viewport.
- Do not depend on hover for instructions, status, actions, or content access.
- Do not embed important text only in screenshots, diagrams, or decorative artwork.
- Give informative screenshots meaningful, context-specific alternative text; use visible captions to explain their relevance.
- Give decorative images and framing empty alternative text or implement them so assistive technology ignores them.
- Provide sufficiently large and separated touch targets without relying on exact dimensions at this stage.
- Respect reduced-motion preferences and make motion nonessential to comprehension or navigation.
- Support browser zoom and text resizing without clipped, overlapping, or missing content.
- Prevent horizontal page scrolling at supported viewport sizes.
- Make mobile navigation operable, labeled, state-aware, and resilient when JavaScript is unavailable.
- Communicate prototype, work-in-progress, and paused statuses in visible text, not color or styling alone.
- Keep project status and technology metadata understandable as normal text; do not turn them into an excessive or repetitive series of tags or badges.
- Make external destinations clear from descriptive labels or concise consistent cues without repetitive announcements.
- Preserve anchors, primary actions, navigation, and all essential content when JavaScript is unavailable.

## 19. Out-of-scope decisions

This wireframe does not decide:

- Final typography scale
- Final font families
- Final colors
- Exact spacing values
- Component-level CSS
- Animation timing
- Signature interaction design
- Final screenshot filenames
- Final EchoTask interface artwork
- Astro implementation details

These decisions belong to later focused Phase 2 documentation or implementation tasks.

## 20. Recommended next Phase 2 task

After this wireframe is reviewed, define the portfolio's typography and spacing systems in one small documentation-first specification, before choosing colors or detailed component styling.
