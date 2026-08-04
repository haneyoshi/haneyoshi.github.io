# MediCheck Visual Evidence Review

## 1. Review purpose

This review determines whether the preserved MediCheck still images provide non-duplicative, public-safe implementation evidence that justifies adding one screenshot to the current portfolio case study. It reviews still images only. The preserved video is outside scope, and `mediCheckIntro.html` is used only to identify historical asset usage; its promotional medical and outcome claims are not accepted as evidence.

## 2. Current published visual

| Item | Finding |
| --- | --- |
| File | `images/Medi_main_window.png` |
| Dimensions and format | 700 × 700 pixels; PNG |
| Current implementation | Imported by `src/pages/index.astro` through Astro's `Image` component, rendered at an explicit 700 × 700 intrinsic size, and kept uncropped. |
| Visible implementation evidence | A running desktop application window titled “MediCheck System”; a Patient ID input; instructions; controls for patient check-in, removal, queue review, selecting the next patient, viewing today's visits, retrieving a patient profile, and exiting; and a visible log area. This supports the limited claim that the prototype has a desktop interface organizing several clinic-record workflow entry points. It does not demonstrate the result of using those controls. |
| Current alt text | “MediCheck desktop prototype showing a Patient ID field and controls for check-in, queue review, visit history, and patient profile retrieval.” The alt text is factual, identifies the prototype context, and summarizes the meaningful controls without making medical or outcome claims. It omits lower-value details such as the exit control and empty log area. |
| Current caption | “MediCheck’s desktop interface groups patient check-in, queue, visit-history, and profile-retrieval workflows in one prototype window.” The caption explains why the image matters and remains appropriately limited to visible interface organization. |

The image itself includes instructional text referring to documenting a diagnosis after selecting the next patient. That text is visible prototype UI copy, not proof that a diagnostic workflow is clinically valid, complete, or suitable for real use.

## 3. Preserved candidate inventory

Repository image references, image filenames, and the historical MediCheck page were checked to identify every preserved still image related to MediCheck.

| Path | Dimensions and format | What it visibly shows | Duplicate or near-duplicate relationship |
| --- | --- | --- | --- |
| `images/Medi_main_window.png` | 700 × 700 pixels; PNG | The MediCheck desktop prototype's main window, including a Patient ID field, workflow instructions, controls for check-in, queue and visit review, patient selection/removal, profile retrieval, exit, and an empty log area. | This is the same file referenced by `mediCheckIntro.html` and currently imported by `src/pages/index.astro`; those uses are not separate candidate images. No duplicate or alternate capture is preserved. |
| `images/mediBranding.webp` | 1024 × 1024 pixels; WebP | A dark, square branding graphic with a large stylized laboratory flask emblem and two smaller versions of the same emblem. It contains no application interface, workflow state, data, or implementation output. | The three emblems within the graphic repeat the same visual motif. It is not a duplicate of the main-window screenshot, but it is decorative rather than complementary implementation evidence. |

No other preserved repository image is identified by filename, source usage, or visible content as MediCheck-related. In particular, `images/enclose.png`, `images/favicon.ico`, `images/web_design.jpeg`, `images/YuShan.jpg`, `public/favicon.svg`, and `public/social-preview.png` are general legacy or portfolio assets rather than MediCheck evidence. The video inventory is intentionally excluded from this review.

## 4. Evidence-gap assessment

The current screenshot does **not** demonstrate:

- a populated patient profile, visit history, queue, or log;
- the result of a check-in or record-retrieval action;
- relationships among patient, symptom, diagnosis, and medication records;
- the MySQL schema, database connection, SQL queries, or retrieved multi-table data;
- any completed end-to-end workflow beyond the presence of interface controls; or
- clinical validation, diagnostic value, treatment effectiveness, deployment, production use, or healthcare outcomes.

The first five omissions form a real implementation-evidence gap because the current case-study story emphasizes relational modeling, SQL-based retrieval, and workflows for storing, retrieving, and reviewing connected historical records. A carefully reviewed screenshot of a populated, representative retrieval or history state could therefore be useful.

However, the gap does not by itself justify adding an image. Neither preserved still-image candidate shows the missing data relationships, retrieval result, or completed workflow. The current written case study states the technical scope without claiming that the screenshot proves every layer. The final omission is a required claim boundary, not an evidence gap that the portfolio should attempt to close.

## 5. Candidate evaluation

### `images/Medi_main_window.png`

- **Privacy:** Pass. No visible real-person data, contact information, or populated medical record is shown.
- **Factual accuracy:** Pass with the existing restrained description. It visibly supports a desktop prototype and workflow controls, but not their completed behavior or the database implementation behind them.
- **Relevance:** High. It directly represents the implemented desktop interface described in the case study.
- **Non-duplication:** Fails as an additional candidate because it is already the published image; reusing it would add no evidence.
- **Image quality:** Adequate. The 700 × 700 capture is legible, uncropped, and currently displayed at no more than its intrinsic size, although the interface is visually utilitarian and the empty state limits its evidentiary depth.
- **Representative status:** Good for the prototype's main entry window, not representative of its relational-data or retrieval results.
- **Accessibility implications:** The current factual alt text and explanatory caption make its purpose understandable. A repeated copy would create redundant screen-reader and visual content.
- **Unsupported-maturity risk:** Low under the current prototype label and caption. The on-screen reference to documenting a diagnosis requires the surrounding educational-prototype context and must not be reframed as proof of diagnostic capability.

### `images/mediBranding.webp`

- **Privacy:** Pass. No personal or record data is visible.
- **Factual accuracy:** The image can only be described as a flask-themed branding graphic. It cannot accurately support application, database, or workflow claims.
- **Relevance:** Low. Its broad medical/laboratory symbolism is thematic rather than evidence of the MediCheck implementation.
- **Non-duplication:** Visually different from the published screenshot, but non-duplication alone does not make it useful evidence. Its internal repeated emblems are also decorative repetition.
- **Image quality:** Technically clear at 1024 × 1024, but the generic graphic and repeated motif do not improve case-study understanding.
- **Representative status:** Poor. It does not represent the application interface or a verifiable implementation state.
- **Accessibility implications:** If decorative, it should receive empty alt text and would add visual weight without information. If treated as meaningful, any useful alt text would expose that it contributes only branding, not evidence.
- **Unsupported-maturity risk:** Moderate. Polished medical/laboratory branding could make the project appear more productized or medically authoritative than the educational desktop prototype warrants, especially without corresponding implementation evidence.

## 6. Side-by-side decision table

| Criterion | `images/Medi_main_window.png` | `images/mediBranding.webp` |
| --- | --- | --- |
| Public privacy | Pass; empty interface state contains no visible personal data | Pass; no personal data |
| Supports factual portfolio wording | Yes, for the existence and organization of desktop workflow controls | No implementation claim; supports only the existence of a branding motif |
| Relevant to identified gap | Partial at best; it is the current evidence and does not show results or relational data | No |
| Adds non-duplicative evidence | No; already published | No; visually different but evidentially empty |
| Image quality for its purpose | Adequate and legible | Clear but generic and decorative |
| Representative implementation state | Main interface only | No implementation state |
| Accessible contribution | Existing alt text and caption provide meaningful context | Would be decorative or require low-value descriptive text |
| Risk of implying unsupported medical maturity or deployment | Low when kept with the educational-prototype framing | Moderate because polished medical branding may imply product or medical authority |
| Decision | Keep as the single published visual | Do not add |

## 7. Final decision

**Keep the current single screenshot.**

The current visual is sufficient for the available preserved evidence: it is the only still image that visibly demonstrates any application implementation, it is privacy-safe, and its alt text and caption accurately limit its role to showing the organization of prototype workflow controls. The case-study text supplies the separately reviewed technical context about relational modeling and SQL retrieval.

An additional screenshot would be justified only if a separate, verified source capture showed a representative populated workflow or retrieval result without private data or unsupported claims. No such preserved still image exists in this repository. Adding the branding graphic would increase decoration, not evidence, and could overstate product or medical maturity.

The Priority 1 MediCheck visual-review backlog item should therefore be recorded in a later authorized backlog update as a **reviewed decline recommendation**: do not add an additional screenshot from the currently preserved candidates. This document records the recommendation only and does not edit the backlog.

## 8. Additional-screenshot implementation scope

Not applicable. No source image, public filename, alt text, caption, or later implementation file list is proposed because this review does not recommend an additional screenshot.

## 9. Remaining limitations

- The current screenshot verifies interface structure, not successful interaction behavior, data persistence, relational schema design, SQL execution, or retrieved results.
- Only two preserved MediCheck-related still images are available, and neither provides a second implementation state.
- The empty interface avoids privacy concerns but also limits the depth of visible evidence.
- The historical page establishes how the two assets were used previously; its promotional medical and outcome wording was not treated as factual support and must not be reused.
- This review does not assess or recommend video.
- This review does not independently inspect the separate MediCheck repository or execute the prototype, so it makes no claim about current reproducibility or completeness.
- Nothing in the reviewed visuals establishes clinical validation, diagnostic value, treatment effectiveness, real deployment, production use, machine learning, or healthcare outcomes.
