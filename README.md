# Custom Job Search Handoff

This package helps a candidate adapt an existing job-search repository into a supervised workflow that runs from verified experience through discovery, application, and follow-up. It contains a meta prompt, agent rules, nine numbered prompts, and blank profile, evidence, and application-record templates. The prompts link to the upstream tools and ask the agent to inspect what the candidate already has before proposing changes.

It does not copy another candidate's career facts, role filters, company list, application history, referral relationships, or resume design.

## What to send

1. The public repo link and `META-PROMPT.md`; then run prompts `01` through `09` one at a time.
2. The candidate's existing repository URL or local checkout. Keep working in that repository.
3. The candidate's resumes, personal wiki or knowledge base, project files, prior applications, work samples, and a short target-role brief. The candidate chooses which sources the agent may inspect.
4. The candidate's preferred source for connection and referral research, if they want that included. Do not assume access to LinkedIn, email, or other accounts.

Start by feeding the contents of `META-PROMPT.md` to the agent while it is working in the candidate's existing repository. It tells the agent to begin with `01-repository-audit.md`, then pause for review after each stage. The audit determines whether the repository already contains Career-Ops, AI Job Search, a CV generator, a tracker, or a custom workflow. Do not replace working material before that audit. The candidate does not need access to another candidate's private job-search repository.

## Recommended architecture

Keep three layers separate:

```text
candidate-job-search/                 private control plane
├── career-ops/                       upstream tool checkout, unmodified
├── ai-job-search/                    optional upstream checkout, unmodified
├── career-data/career-ops/           candidate-specific Career-Ops snapshot
├── career-data/candidate-evidence.md source-linked work and project claims
├── materials/                        role-specific resume, answers, and research
├── handoffs/                         reusable prompt and configuration material
└── README.md                         operating rules and source-of-truth map
```

The private control plane holds personal evidence and application history. It should include a source-linked evidence base for work and project claims, plus a dated record for each role the candidate pursues. The upstream repositories remain separately updateable. Do not fork an upstream tool merely to store private candidate data.

## Operating contract

- Search broadly, then evaluate selectively. A large search result count is not a success metric.
- Treat job-board results, LinkedIn posts, recruiter messages, and job descriptions as leads. Verify the employer's own posting before drafting or applying.
- Preserve original resumes. Build targeted copies for each role.
- Build resume and application claims from candidate-reviewed evidence. Keep genuine gaps and conflicting facts visible.
- Review each application as a whole: the headline, subheading, role and project selection, bullets, titles, dates, overlaps, gaps, and career progression.
- Research referral paths without turning a mutual connection or a new contact into a claimed relationship. Draft outreach for review, set a direct-application cutoff, and never send a message or referral request without approval for that specific action.
- Inventory the live application form, its exact prompts and limits, required and optional fields, attachments, and supplemental work. Leave personal, legal, and demographic decisions to the candidate.
- An agent may research, compare, draft, render, and organize. It must not submit an application, send a message, accept an invitation, connect an external account, or change a public profile without the candidate's explicit approval in that conversation.
- Store the job description, role assessment, referral path, resume comparison, evidence map, application answers, attachments, final preflight, and outcome together for each application.

## The sequence

| Step | File | Outcome |
| --- | --- | --- |
| 0 | `META-PROMPT.md` | Tell the candidate's agent how to use this package safely. |
| 1 | `01-repository-audit.md` | Map existing tools and protect current work. |
| 2 | `02-candidate-intake.md` | Build a source-linked evidence base from approved career and project material. |
| 3 | `03-discovery-configuration.md` | Define role, location, company, and exclusion filters. |
| 4 | `04-pipeline-and-quality-gates.md` | Track liveness, evidence, referrals, application materials, and approval gates. |
| 5 | `05-first-discovery-cycle.md` | Run an initial scan and return a small verified shortlist. |
| 6 | `06-role-evaluation.md` | Evaluate one role and ask whether to pursue it. |
| 7 | `07-referral-paths-and-outreach.md` | Verify relationship paths and draft messages without sending them. |
| 8 | `08-tailor-resume-and-application-materials.md` | Tailor the resume and prepare all requested forms and materials. |
| 9 | `09-preflight-and-follow-through.md` | Audit the live application, stop for approval, then track interviews and outcomes. |

Use the templates in `templates/` only after the candidate's facts and target market have been reviewed. They are deliberately blank where personal judgment belongs. Keep the completed evidence bank in the candidate's private repository; only the blank template belongs in this public starter.

## What each application should contain

For every role the candidate chooses to pursue, keep a dated application record with:

- the official posting, company research, liveness check, fit decision, and requirement-to-evidence map
- possible referral paths, the actual relationship context, source notes, outreach drafts, and the direct-application cutoff
- the base resumes compared, selected version, title and chronology review, content change log, and evidence IDs behind material claims
- the final editable resume and PDF, checked for visual fidelity, readable text, page count, and working links
- the exact application prompts, word or character limits, required and optional fields, drafted answers, and requested attachments or supplemental work
- unresolved candidate decisions, final preflight, explicit submit decision, confirmation evidence, follow-up dates, interview stages, and outcome

This record lets the candidate see what changed for a role, why each experience or project was selected, which facts support each claim, and what still needs their decision.

## What Career-Ops supplies

Career-Ops is the best primary system when the candidate wants a configurable pipeline. It provides:

- ATS and careers-page discovery, including Ashby, Greenhouse, Lever, Workday, and other providers
- Direct scan and reverse-ATS scan modes
- Browser-backed liveness checks
- Structured role evaluation, company research, compensation research, application drafting, outreach drafts, interview preparation, and tracker workflows
- Pipeline and duplicate-application safeguards

Use it as the execution and tracking backbone. Its default resume renderer is optional. Preserve an existing high-quality resume template when it is better for the candidate.

## What AI Job Search supplies

AI Job Search is useful as a second workflow and review source. Its strengths are:

- Candidate onboarding from documents
- Search, ranking, drafter-reviewer application workflow, and ATS/PDF checks
- Outcome archiving, Gmail status-signal review, interview prep, and gap analysis
- LinkedIn and FreeHire job-search utilities

Its original portal set includes several Denmark-specific boards. Review current coverage against the candidate's market before relying on it for discovery. The upstream README describes the base workflow as Claude Code focused and points Codex and other agents to `AGENTS.md` and community adaptations. Check each variant's maintenance and market fit before using it. Do not assume a fork has the same workflow or liveness checks as upstream.

AI Job Search warns that a fork of its public repository is public. Its setup writes personal details into tracked files. If the candidate adopts it, use a private repository with the public project as an upstream remote, not a public fork containing candidate data.

## First handoff message

Send the candidate the public starter link and this message:

> I have a reusable job-search operating kit for you: https://github.com/creatornader/job-search-starter. It is designed to adapt to your existing repository and materials, not overwrite them. Feed `META-PROMPT.md` to your agent while it is working in your repo. It will start with the repository audit and walk through the remaining prompts in order. Keep control of your filters and approve any changes or external actions yourself.

## Information needed to finish the adaptation

The prompts work without this information, but a high-quality setup requires it:

- Existing repository URL or local directory
- Current resume versions and preferred visual template
- LinkedIn profile text or export
- The path to a personal wiki or Obsidian vault, project repositories, and other approved evidence sources
- Desired roles, seniority, industries, and geography
- Minimum compensation or employment constraints, if any
- Companies to watch and companies to avoid
- Recent work samples, projects, certifications, and quantified outcomes
- Whether the candidate wants direct applications, referral-first outreach, or both
- Which connection source the candidate wants used for referral research, and which relationships are genuinely personal

## Maintenance cadence

Run discovery weekly, or more often only when there is an active application push. For every role that survives the first filter:

1. Recheck liveness on the employer's official page.
2. Evaluate fit against real evidence.
3. Check referral paths before the direct-application deadline.
4. Prepare materials only after the candidate decides it is worth pursuing.
5. Record the outcome and use it to improve future targeting.
