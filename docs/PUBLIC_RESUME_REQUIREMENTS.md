# Private Résumé Source Inventory and Fact-Verification Reference

## 1. Purpose

This document is a private source inventory and fact-verification reference for maintaining a private master résumé and preparing job-specific résumés. It identifies reliable source material, privacy restrictions, supported facts, unresolved facts, evidence rules, and review criteria. It is not a public résumé specification and does not authorize any résumé artifact, page, download, or link in the portfolio.

The portfolio remains a single-page public professional profile. It should contain important public professional information without reproducing the full résumé, and it will have no résumé PDF, no résumé download link, and no dedicated résumé webpage. The private master résumé and all job-specific résumés remain outside the public portfolio workflow.

## 2. Source-material inventory

| Repository path or reference | Type | Apparent purpose and status | Potentially reusable information | Concerns and review requirement |
| --- | --- | --- | --- | --- |
| `YuShan Hung.pdf` | Binary PDF | Preserved legacy résumé; currency is uncertain | May contain prior experience, education, skills, and contact details | Contents could not be inspected with the available repository tools. Treat as unreadable for this inventory; manually review for privacy, accuracy, age, and conflicts before reusing anything. |
| `index.html` | Legacy HTML | Preserved legacy portfolio with an external Google Drive résumé link; outdated | Name, older education references, GitHub profile, LinkedIn, and historical project/skill leads | Describes YuShan as a recent graduate seeking an internship, shortens the current approved degree wording elsewhere, and lists electrical-engineering education without enough credential detail. Its project claims and broad skill list are not current evidence. The external résumé contents were not inspected. Manual review is required. |
| `docs/PORTFOLIO_CONTENT.md` | Markdown | Authoritative editable public-copy source; current | Approved positioning, current role and dates, education, project facts and status, evidence-supported technologies, public email, LinkedIn, and project links | Employer and confidential work details must remain excluded. Public portfolio wording is useful corroboration, but private résumé contact and tailoring decisions require separate review. |
| `docs/PORTFOLIO_REBUILD_PLAN.md` | Markdown | Governing portfolio roadmap, decisions, and restrictions; current | Broad role audience, public experience and education boundaries, supported skill evidence, portfolio technology, and privacy/claim restrictions | Contains implementation history as well as approved facts; extract only relevant current decisions. Manual review is required. |
| `docs/PORTFOLIO_BACKLOG.md` | Markdown | Portfolio maintenance register; current | Records evidence-led public portfolio work | It does not govern private résumé production and must not contain a résumé-publication implementation task. |
| `src/pages/index.astro` | Astro/HTML source | Current public portfolio implementation and project descriptions | Public presentation of IT Operations Analyst experience, education, MediCheck, EchoTask, evidence-supported technologies, contact details, LinkedIn, and project links | Useful as corroboration, but `docs/PORTFOLIO_CONTENT.md` remains the public-copy authority. Do not infer additional duties or maturity from presentation wording. |
| `mediCheckIntro.html` | Legacy HTML | Older MediCheck project page; outdated | Historical lead to the MediCheck repository and possible implementation topics | Contains promotional medical and outcome claims that conflict with the approved educational-prototype limits. Do not reuse those claims without independent verification. Manual review is required. |
| `README.md` and `astro.config.mjs` | Markdown and JavaScript configuration | Current repository/deployment references | Corroborate the Astro portfolio and public GitHub Pages site `https://haneyoshi.github.io/` | They do not establish personal qualifications. Manual review is required before a link is used in a job-specific résumé. |

No second repository résumé file was found. The Google Drive destination referenced by the legacy page is an external reference, not an inspected repository artifact; its availability, contents, ownership, privacy, and currency remain uncertain.

## 3. Confirmed facts

The following facts are supported by the current portfolio planning and content documents:

- Name: YuShan.
- Broad positioning: software developer with experience in IT operations, data reporting, workflow analysis, automation, and technical problem-solving.
- Current role: IT Operations Analyst, June 2025–present. Do not publish the employer name.
- Education: Bachelor’s degree in Applied Computer Science, University of Winnipeg, completed in 2023.
- Bachelor’s degree in Electrical Engineering from WuFeng University. The exact official credential wording and completion date still require documentary verification before use.
- MediCheck: solo 2024 Python and MySQL educational desktop software prototype.
- EchoTask: solo full-stack MVP and work in progress using React, Flask, SQLAlchemy, and SQLite.
- Portfolio rebuild: built with Astro and TypeScript.
- Documented public contact/link candidates: `pokemonbotno001@gmail.com`, `https://www.linkedin.com/in/yushan-hung-266273212/`, `https://github.com/haneyoshi/MediCheck`, `https://github.com/haneyoshi/WebAppMVP`, and `https://haneyoshi.github.io/`. Each must be reviewed for relevance and accuracy before use in a job-specific résumé; the documented public portfolio email does not authorize publication of any separate private résumé email.

Do not invent responsibilities, metrics, achievements, clients, users, technologies, dates, certifications, awards, or business outcomes.

## 4. Privacy and public-claim restrictions

The portfolio must not publish a phone number, private résumé email, current employer identity, confidential systems, processes, work information, private data, or unsupported claims. Home address, immigration or work-authorization information, references, and reference contact details also remain private. Do not publish unsupported proficiency, years-of-experience, metrics, achievements, or claims that overstate MediCheck or EchoTask maturity.

A private résumé may contain approved contact or employer information when appropriate for its specific recipient, but that does not make the information eligible for the public portfolio. Review every job-specific résumé and intended recipient separately.

MediCheck must remain clearly identified as an educational prototype. It must not be presented as validated, deployed, production, machine-learning, diagnostic, or treatment technology, and it must not imply real clinical use or medical outcomes.

EchoTask must remain clearly identified as a work-in-progress MVP. Stronger claims—including authentication, role-based access, automated testing, and 52 passing tests—require direct repository verification before they may appear publicly. Do not imply completed integration, production deployment, comprehensive testing, or organizational adoption without verified evidence.

## 5. Private résumé purpose and audience

Maintain one private master résumé as a controlled source of verified facts. Use it to prepare tailored, job-specific résumés for software-development, junior or early-career full-stack, application-support, systems or technical analyst, and related technical opportunities.

The master résumé is not a universal public document. Portfolio wording and tailored-résumé project wording may differ to suit their contexts, but both must remain factual, preserve project maturity and ownership, and be supported by inspected evidence or explicit confirmation.

## 6. Candidate private résumé sections

A private master or job-specific résumé may use the following sections when relevant and supported:

1. Name and professional headline.
2. Recipient-appropriate contact details and reviewed links.
3. Professional summary.
4. Technical skills supported by inspected evidence.
5. Experience.
6. Selected projects.
7. Education.

Certifications, awards, training, or other optional sections may be added only when verified source material exists. Sections and emphasis should be tailored to the specific opportunity rather than copied wholesale into the portfolio.

## 7. Evidence and claim rules

Every portfolio or résumé statement must be supported by at least one inspected source or explicit user confirmation. Classify working material as:

- **Confirmed fact:** directly supported by a current inspected source.
- **Safe summary:** a conservative paraphrase that preserves the source's scope and certainty.
- **Confirmation required:** incomplete, conflicting, outdated, binary/unreadable, external-only, or otherwise unverified information.
- **Do not publish:** restricted private information or an unsupported/confidential claim.

Use current planning/content documents over legacy presentation where they conflict, but record rather than conceal unresolved conflicts. Project labels must state maturity honestly, and ownership must remain accurate: MediCheck and EchoTask are solo projects. Do not turn tools used in a project into unsupported general proficiency or infer employment responsibilities from a title alone.

## 8. Unresolved information

Confirm the following before relying on it in the private master résumé or a job-specific résumé:

- exact approved professional headline or opportunity-specific variants;
- complete current-role responsibilities, supportable outcomes, and which details may be disclosed to a specific recipient;
- whether older employment should be included, with exact titles and dates;
- whether the Electrical Engineering degree from WuFeng University should appear in a particular tailored résumé, plus its exact official credential wording and completion date;
- any additional verified technical skills and their evidence;
- certifications, awards, or training, if any;
- approved résumé email, phone number, LinkedIn, GitHub/profile, project, portfolio, and other recipient-appropriate links;
- whether any usable facts exist only in the binary PDF or external legacy résumé, and how conflicts should be resolved; and
- desired length and preferred source/output format for the private master and each job-specific résumé.

These unresolved items do not create a public portfolio résumé task.

## 9. Private maintenance and tailoring sequence

1. Resolve outstanding facts relevant to the target opportunity.
2. Update the private master résumé with source-backed facts.
3. Prepare job-specific wording and select relevant sections.
4. Review privacy, claims, project maturity, and recipient suitability.
5. Review formatting, accessibility, links, and document properties.
6. Deliver the job-specific résumé outside the public portfolio workflow.
7. Record material fact corrections in the appropriate private source inventory; update public portfolio documentation only when a separately approved, public-safe factual correction is needed.

## 10. Readiness checklist

A private master or job-specific résumé is ready for use only when:

- [ ] Required unresolved facts have explicit answers or are deliberately omitted.
- [ ] Every intended claim has an inspected source or explicit user confirmation.
- [ ] Current-role wording excludes confidential details and is appropriate for the intended recipient.
- [ ] Education conflicts and any older employment are resolved.
- [ ] Project ownership, technology, and maturity labels are verified.
- [ ] Contact details and every link are accurate and appropriate for the intended recipient.
- [ ] Optional credentials have documentary support or are excluded.
- [ ] Intended length and source/output format are agreed.
- [ ] Privacy and accuracy review is complete.
- [ ] No résumé artifact or link is being added to the public portfolio.
