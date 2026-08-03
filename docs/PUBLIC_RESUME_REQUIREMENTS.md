# Public Resume Requirements

## 1. Purpose

This document prepares a later resume-writing task. It identifies reliable source material, publication restrictions, required sections, unresolved facts, evidence rules, and review criteria for one universal public-safe resume. It is a requirements and source-control document, not the resume itself.

## 2. Source-material inventory

| Repository path or reference | Type | Apparent purpose and status | Potentially reusable information | Concerns and review requirement |
| --- | --- | --- | --- | --- |
| `YuShan Hung.pdf` | Binary PDF | Preserved legacy resume; currency is uncertain | May contain prior experience, education, skills, and contact details | Contents could not be inspected with the available repository tools. Treat as unreadable for this inventory; manually review for privacy, accuracy, age, and conflicts before reusing anything. |
| `index.html` | Legacy HTML | Preserved legacy portfolio with an external Google Drive resume link; outdated | Name, older education references, GitHub profile, LinkedIn, and historical project/skill leads | Describes YuShan as a recent graduate seeking an internship, shortens the current approved degree wording elsewhere, and lists electrical-engineering education without enough credential detail. Its project claims and broad skill list are not current evidence. The external resume contents were not inspected. Manual review is required. |
| `docs/PORTFOLIO_CONTENT.md` | Markdown | Authoritative editable public-copy source; current | Approved positioning, current role and dates, education, project facts and status, evidence-supported technologies, public email, LinkedIn, and project links | Employer and confidential work details must remain excluded. Contact details and every link still require deliberate resume-publication approval. Manual final review is required. |
| `docs/PORTFOLIO_REBUILD_PLAN.md` | Markdown | Governing roadmap, decisions, and restrictions; current | Broad role audience, public experience and education boundaries, supported skill evidence, portfolio technology, and privacy/claim restrictions | Contains implementation history as well as approved facts; extract only relevant current decisions. Manual review is required. |
| `docs/PORTFOLIO_BACKLOG.md` | Markdown | Deferred-work register; current | Confirms that a universal public-safe resume and explicit publication approval are prerequisites to replacing the placeholder | It does not supply resume copy or a final URL. Manual review is required before changing backlog status. |
| `src/pages/index.astro` | Astro/HTML source | Current public portfolio implementation and project descriptions | Public presentation of IT Operations Analyst experience, education, MediCheck, EchoTask, evidence-supported technologies, contact details, LinkedIn, and project links | Useful as corroboration, but `docs/PORTFOLIO_CONTENT.md` remains the copy authority. Do not infer additional duties or maturity from presentation wording. Manual review is required. |
| `mediCheckIntro.html` | Legacy HTML | Older MediCheck project page; outdated | Historical lead to the MediCheck repository and possible implementation topics | Contains promotional medical and outcome claims that conflict with the approved educational-prototype limits. Do not reuse those claims without independent verification. Manual review is required. |
| `README.md` and `astro.config.mjs` | Markdown and JavaScript configuration | Current repository/deployment references | Corroborate the Astro portfolio and public GitHub Pages site `https://haneyoshi.github.io/` | They do not establish personal qualifications or a resume publication URL. Manual link approval is required. |

No second repository resume file was found. The Google Drive destination referenced by the legacy page is an external reference, not an inspected repository artifact; its availability, contents, ownership, privacy, and currency remain uncertain.

## 3. Confirmed public facts

The following facts are supported by the current portfolio planning and content documents:

- Name: YuShan.
- Broad positioning: software developer with experience in IT operations, data reporting, workflow analysis, automation, and technical problem-solving.
- Current role: IT Operations Analyst, June 2025–Present. Do not publish the employer name.
- Education: Bachelor’s degree in Applied Computer Science, University of Winnipeg, completed in 2023.
- MediCheck: solo 2024 Python and MySQL educational desktop software prototype.
- EchoTask: solo full-stack MVP and work in progress using React, Flask, SQLAlchemy, and SQLite.
- Portfolio rebuild: built with Astro and TypeScript.
- Documented public contact/link candidates: `pokemonbotno001@gmail.com`, `https://www.linkedin.com/in/yushan-hung-266273212/`, `https://github.com/haneyoshi/MediCheck`, `https://github.com/haneyoshi/WebAppMVP`, and `https://haneyoshi.github.io/`. Each remains subject to deliberate approval for resume publication.

Do not invent responsibilities, metrics, achievements, clients, users, technologies, dates, certifications, awards, or business outcomes.

## 4. Publication and privacy restrictions

The public resume must exclude:

- home address;
- phone number unless separately approved later;
- immigration or work-authorization information;
- employer identity;
- confidential systems, processes, data, or internal details;
- sensitive personal email addresses;
- references and reference contact details;
- unsupported proficiency or years-of-experience claims;
- invented metrics or achievements; and
- any claim that overstates MediCheck or EchoTask maturity.

MediCheck must remain clearly identified as an educational prototype, not validated, deployed, production, machine-learning, or treatment technology. EchoTask must remain clearly identified as a work-in-progress MVP and must not imply completed authentication, production deployment, complete integration, comprehensive testing, or organizational adoption. All contact details and links must be deliberately reviewed and approved before publication, even when already public elsewhere.

## 5. Proposed resume purpose and audience

Create one universal public-safe resume suitable for software-development, junior or early-career full-stack, application-support, systems or technical analyst, and related technical opportunities. Keep the positioning broad and evidence-based; do not position YuShan exclusively as a frontend developer.

## 6. Required resume sections

The later resume should contain, without presupposing final copy:

1. Name and professional headline.
2. Public-safe contact details and approved links.
3. Professional summary.
4. Technical skills supported by inspected evidence.
5. Experience.
6. Selected projects.
7. Education.

Certifications, awards, training, or other optional sections may be added only when verified source material exists and publication is approved.

## 7. Evidence and claim rules

Every resume statement must be supported by at least one inspected source or explicit user confirmation. Classify working material as:

- **Confirmed fact:** directly supported by a current inspected source.
- **Safe summary:** a conservative paraphrase that preserves the source's scope and certainty.
- **Confirmation required:** incomplete, conflicting, outdated, binary/unreadable, external-only, or otherwise unverified information.
- **Do not publish:** restricted private information or an unsupported/confidential claim.

Use current planning/content documents over legacy presentation where they conflict, but record rather than conceal unresolved conflicts. Project labels must state maturity honestly, and ownership must remain accurate: MediCheck and EchoTask are solo projects. Do not turn tools used in a project into unsupported general proficiency, or infer employment responsibilities from a title alone.

## 8. Unresolved information

Confirm the following before drafting:

- exact approved professional headline;
- complete public-safe current-role responsibilities and any supportable outcomes;
- whether older employment should be included, with exact titles and dates;
- whether the legacy electrical-engineering education/background should appear and its exact credential, institution, and date wording;
- any additional verified technical skills and their evidence;
- certifications, awards, or training, if any;
- final approved public email, LinkedIn, GitHub/profile, project, portfolio, and other links;
- whether any usable facts exist only in the binary PDF or external legacy resume, and how conflicts should be resolved;
- desired resume length and preferred source/output format; and
- whether PDF, HTML, or both will eventually be published.

## 9. Drafting and review sequence

1. Resolve outstanding facts.
2. Prepare source-backed resume copy.
3. Review privacy and claims.
4. Review formatting and accessibility.
5. Generate the approved final artifact.
6. Verify links and document properties.
7. Update portfolio content and the resume link in a separate task.
8. Update the rebuild plan.

## 10. Readiness checklist

Resume drafting may begin only when:

- [ ] Required unresolved facts have explicit answers or are deliberately omitted.
- [ ] Every intended claim has an inspected source or explicit user confirmation.
- [ ] Current-role wording is public-safe and excludes employer/confidential details.
- [ ] Education conflicts and any older employment are resolved.
- [ ] Project ownership, technology, and maturity labels are verified.
- [ ] Contact details and every link are explicitly approved for publication.
- [ ] Optional credentials have documentary support or are excluded.
- [ ] Intended length and source/output format are agreed.
- [ ] A privacy and accuracy reviewer is identified for the later draft.
