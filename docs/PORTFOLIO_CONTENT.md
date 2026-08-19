# Portfolio Master Content — Version 1

## 1. Content purpose and editing rules

This document is the Version 1 master copy for YuShan's portfolio. It provides the approved content direction for page design and implementation while remaining editable as the layout develops.

- Keep the writing clear, concise, and factual.
- Prefer specific evidence over broad claims.
- Preserve an honest distinction between completed work, prototypes, and work in progress.
- Do not add metrics, outcomes, technologies, responsibilities, users, clients, or achievements without confirmation.
- Keep project descriptions understandable to both technical and non-technical readers.
- Treat headings, paragraph length, and calls to action as adjustable during layout review, but preserve the meaning and restrictions recorded here.
- Do not feature individual academic assignments as portfolio projects.

## 2. Target audience

The portfolio is intended for hiring managers, recruiters, technical leads, and potential collaborators considering YuShan for software development, full-stack development, application support, systems analysis, technical analyst, and related technical roles.

The content should work for readers who want a quick overview as well as those looking for evidence of practical development, structured analysis, and technical problem-solving. Supporting career copy may refer naturally to junior-level opportunities, but the portfolio should not narrow YuShan to a single title or frontend-only path.

## 3. Professional positioning

YuShan is a software developer with experience across IT operations, data reporting, workflow analysis, automation, and technical problem-solving. A background in applied computer science supports a practical approach to understanding systems, organizing information, investigating problems, and building software.

The positioning should remain broad enough to support software development, full-stack development, application support, systems analysis, technical analyst roles, and related technical work. YuShan should not be presented only as a frontend developer.

**Short positioning line:**

> Software developer bringing structured analysis and practical problem-solving to software, systems, and operational workflows.

## 4. Hero

**Eyebrow:**

> Hello, I'm YuShan.

**Headline:**

> Software Developer

**Supporting copy:**

> I build practical software and approach technical problems with experience spanning IT operations, data reporting, workflow analysis, and automation.

**Primary action:**

> View my work

**Secondary action:**

> Contact me

**Résumé action:**

> View résumé

The résumé action must remain inactive or clearly marked as unavailable until a public-safe universal résumé and final link are ready.

## 5. About

I am a software developer with a Bachelor’s degree in Applied Computer Science, currently working as an IT Operations Analyst. My work and projects have developed my interest in the connection between software, data, systems, and the day-to-day workflows they support.

I enjoy breaking down technical problems, organizing requirements, and turning ideas into practical implementations. My experience includes IT operations, data reporting, workflow analysis, automation, and application development. I am continuing to strengthen my full-stack development skills through focused projects and the rebuild of this portfolio.

I am interested in junior-level and related opportunities where I can contribute careful analysis, dependable technical work, and a willingness to keep learning across software and systems.

## 6. Experience

### IT Operations Analyst

**June 2025–Present**

Current technical role involving IT operations, data reporting, workflow analysis, automation, and technical problem-solving.

The employer's name, internal systems, confidential processes, private data, and unconfirmed responsibilities or outcomes must not be published. This description should remain intentionally high level unless additional public-safe details are reviewed and approved.

## 7. Education

### Bachelor’s degree in Applied Computer Science

**University of Winnipeg · Completed 2023**

The degree established a foundation in software development, computing concepts, and structured problem-solving. Individual academic assignments should not be featured as portfolio projects.

## 8. Projects section introduction

These projects show how I approach software development through practical problem definition, structured data, interface design, and iterative implementation. Each project is presented according to its current scope and maturity, without overstating completion or real-world use.

## 9. MediCheck

### MediCheck

**Educational desktop software prototype · Solo project · Built 2024 · Redesigned 2026**

MediCheck is a Python, Tkinter/ttk, and MySQL educational clinic-workflow prototype that I originally built in 2024 and substantially redesigned in 2026. The current application follows one continuous workflow from patient check-in and queue management through consultation, transactional visit completion, and historical record retrieval.

**Workflow redesign:** I redesigned the original popup-heavy, debug-style interface as a persistent multi-workspace application shell with clear navigation and integrated patient workflows. The main flow moves from Check In / Register through Patient Queue, Take Patient, Symptoms, Diagnosis, Prescription, Review, Complete Visit, and Patient History. Consultation is one four-stage experience—Symptoms, Diagnosis, Prescription, and Review—that keeps patient context and confirmed selections visible. This preserved useful backend behavior while improving the existing application rather than replacing it with an unnecessary rewrite.

**Relational data and SQL:** MediCheck models patients, visits, symptoms, diagnoses, prescriptions, and medicines as related data. Historical records reconstruct visits across those relational tables and support symptom, diagnosis, and medicine suggestions through SQL queries, associations, aggregation, frequency analysis, and ranking. The system distinguishes generated suggestions from confirmed selections; it does not use a trained machine-learning model or medically validated AI.

**Reliability and state:** Completing a visit now persists the complete logical case in one explicit database transaction. A persistence failure rolls the transaction back while preserving consultation state for retry; state is cleared only after successful completion, and duplicate completion is guarded against. The redesign also included consistent patient-ID normalization, validation, empty and error states, state-lifecycle fixes, focused automated testing, and manual end-to-end QA with a real local MySQL environment.

**Technology:** Python, Tkinter/ttk, MySQL

**Status:** Educational software prototype

**Repository action:**

> View MediCheck on GitHub

**Approved visual evidence:** Use the redesigned 2026 Dashboard as the primary visual and the Symptoms / consultation workspace as the supporting visual. The Patient Records / history screenshot remains a reserve image only. Diagnosis and Prescription screenshots are not selected because they duplicate the consultation evidence and would unnecessarily lengthen the presentation. No third image, carousel, animation, video, JavaScript interaction, or dependency is approved.

> Clinic workflow overview — The redesigned application shell brings queue status, patient actions, and current clinic activity into one consistent workspace.

> Guided consultation workflow — A four-stage consultation keeps patient context and confirmed selections visible while historical relational data surfaces related suggestions.

MediCheck must not be described as clinically validated, medically deployed, machine learning, medical AI, a real deployed clinical system, production-ready, production software, regulatory-compliant software, or effective treatment technology. Its educational and prototype status must remain clear wherever it appears.

## 10. EchoTask

### EchoTask

**Completed full-stack MVP · Solo project**

EchoTask is a full-stack operations-coordination MVP designed around the daily workflows of a caretaking or facilities team. It brings attendance, worker availability, area coverage, temporary assignments, events, Snow Logs, supply requests, and account management into one role-aware system.

I designed and implemented the project end to end: the relational model, Flask backend and authenticated JSON API, business rules, React frontend, and role-aware Worker, Coordinator, and Supervisor workflows.

The design keeps permanent worker-area assignments separate from temporary daily coverage, separates private absence reasons from general operational availability, and models important business relationships as structured relational data instead of free-form text. Backend authorization enforces role permissions beyond the interface, while an explicit UTC/local-time contract keeps timestamps predictable across the application.

The implementation includes cookie-based Flask sessions, validation and edge-state handling, privacy-aware information visibility, SQLite schema evolution, and reproducible demo data. Automated backend testing reached a documented checkpoint of 52 passing tests, alongside browser and frontend/backend integration verification and iterative refinement.

**Technology:** React, Flask, SQLAlchemy, SQLite

**Status:** Completed MVP

**Repository action:**

> View EchoTask on GitHub

**Approved visual evidence:** Use two complementary screenshots rather than a general feature gallery. The Dashboard shows the coordinator's operational overview of building coverage, worker availability, regular area ownership, temporary coverage, and selected-building detail. Attendance / Worker Availability shows that official attendance remains separate from operational availability. No third screenshot is currently needed.

> Daily coverage overview — Coordinators can review worker availability, regular area ownership, and temporary coverage across buildings from a shared operational dashboard.

> Attendance and availability — EchoTask keeps official attendance separate from operational availability, allowing a worker to remain checked in while temporarily assigned elsewhere.

These screenshots support EchoTask's status as a completed solo full-stack MVP. They must not imply production deployment or real organizational adoption.

EchoTask must not be presented as a production system used by a real organization, commercially deployed software, enterprise-scale software, production-ready, or as having real organizational adoption.

## 11. Skills with supporting evidence

Skills should be presented in evidence-based groups rather than as an exhaustive technology list.

### Software development

- **Python:** Used for MediCheck's desktop application logic, workflow redesign, validation, and state lifecycle.
- **JavaScript and React:** Used in the EchoTask full-stack MVP.
- **Flask:** Used for EchoTask's backend development.
- **SQLAlchemy and SQLite:** Used for data modeling and persistence work in EchoTask.
- **MySQL:** Used for MediCheck's relational visit records, SQL-driven historical suggestions, and transactional persistence.

### Systems and analysis

- **IT operations:** Supported by the current IT Operations Analyst role.
- **Workflow analysis:** My current role provides experience in analyzing workflows and developing small automation tools.
- **Data reporting:** Supported by current professional experience.
- **Automation:** Supported by current professional experience.
- **Technical problem-solving:** Demonstrated across the current role, independent software projects, and applied computer science education.

### Working approach

- **Structured problem-solving:** Supported by applied computer science education and project work spanning interfaces, application logic, and data.
- **Iterative development:** Demonstrated by maintaining clear prototype and work-in-progress boundaries while improving projects in stages.
- **Full-stack learning:** Demonstrated through EchoTask's React, Flask, SQLAlchemy, and SQLite stack.

Do not add proficiency ratings, years of experience, or additional tools without verified supporting evidence.

## 12. Portfolio rebuild statement

This portfolio is being rebuilt as a focused software project using Astro and TypeScript. The work includes content planning, component-based implementation, responsive design, accessibility considerations, and static deployment through GitHub Pages.

The rebuild is intended to make the portfolio itself a transparent example of thoughtful frontend engineering and maintainable organization. It should be presented as ongoing work until the relevant design, implementation, and quality checks are complete.

## 13. Contact

### Let's connect

I am open to conversations about software development, full-stack development, application support, systems analysis, technical analyst roles, junior-level opportunities, and related technical work.

**Email:** [pokemonbotno001@gmail.com](mailto:pokemonbotno001@gmail.com)

**LinkedIn:** [linkedin.com/in/yushan-hung-266273212](https://www.linkedin.com/in/yushan-hung-266273212/)

**Primary contact action:**

> Send an email

## 14. Footer

> Designed and built by YuShan.

Optional supporting line:

> Built with Astro and TypeScript.

The footer may include the confirmed LinkedIn and GitHub project links where appropriate. It should not display private contact information.

## 15. Confirmed public links

- **Email:** [pokemonbotno001@gmail.com](mailto:pokemonbotno001@gmail.com)
- **LinkedIn:** [https://www.linkedin.com/in/yushan-hung-266273212/](https://www.linkedin.com/in/yushan-hung-266273212/)
- **MediCheck repository:** [https://github.com/haneyoshi/MediCheck](https://github.com/haneyoshi/MediCheck)
- **EchoTask repository:** [https://github.com/haneyoshi/WebAppMVP](https://github.com/haneyoshi/WebAppMVP)

## 16. Temporary placeholders

- **Résumé URL:** Pending a public-safe universal résumé. Do not publish a temporary private document or invent a URL.
- **MediCheck visuals:** The redesigned 2026 Dashboard and Symptoms / consultation screenshots are the approved two-image evidence set. Patient Records / history remains reserve-only; no third image is currently needed.
- **EchoTask visuals:** Dashboard and Attendance / Worker Availability are the approved complementary evidence; no third screenshot is currently needed.

Placeholders must be visibly temporary in working materials and must not create broken or misleading public actions.

## 17. Privacy and claim restrictions

- Do not publish a home address, phone number, immigration information, sensitive personal email, or other private information.
- Do not publish the current employer's name, confidential operational details, internal systems, private data, or unapproved work examples.
- Do not invent or imply metrics, achievements, technologies, users, clients, responsibilities, or business outcomes.
- Do not present prototypes or works in progress as production-deployed, adopted, or production-ready. Describe completion, testing, or validation only when supported by authoritative project evidence.
- Do not claim MediCheck is clinically validated, medically deployed, machine learning, medical AI, a real deployed clinical system, production-ready, production software, regulatory-compliant software, or effective treatment technology.
- Do not claim EchoTask is production-deployed, commercially deployed, enterprise-scale, production-ready, used by a real organization, or adopted by one.
- Do not feature individual academic assignments.
- Review all future additions for public safety, factual support, and consistency with the project's actual status.

## 18. Remaining review items

- Public-safe résumé completion and final link
- MediCheck implementation refresh after the documentation changes are reviewed
- Final wording refinements after page layout review
