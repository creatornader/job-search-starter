# Custom Job Search Handoff

This package lets another candidate turn an existing job-search repository into a supervised, evidence-based search system. It contains a meta prompt, agent rules, six numbered prompts, and blank configuration templates. The prompts include the upstream sources needed to decide whether to retain, extend, or install the tools.

It does not copy another candidate's career facts, role filters, company list, application history, referral relationships, or resume design.

## What to send

1. `META-PROMPT.md`, followed by the six numbered prompts in order.
2. The candidate's existing repository URL or a local checkout.
3. The candidate's current resume(s), LinkedIn export or profile text, work samples, and a short target-role brief.

Start by feeding the contents of `META-PROMPT.md` to the agent with the candidate's existing repository as its working directory. It tells the agent to read the package and begin with `01-repository-audit.md`. The audit determines whether the existing repository already contains Career-Ops, AI Job Search, a CV generator, or a custom implementation. Do not replace working material before that audit. The candidate does not need access to another candidate's private job-search repository.

## Recommended architecture

Keep three layers separate:

```text
candidate-job-search/                 private control plane
├── career-ops/                       upstream tool checkout, unmodified
├── ai-job-search/                    optional upstream checkout, unmodified
├── career-data/career-ops/           candidate-specific Career-Ops snapshot
├── materials/                        role-specific resume, answers, and research
├── handoffs/                         reusable prompt and configuration material
└── README.md                         operating rules and source-of-truth map
```

The private control plane holds personal evidence and application history. The upstream repositories remain separately updateable. Do not fork an upstream tool merely to store private candidate data.

## Operating contract

- Search broadly, then evaluate selectively. A large search result count is not a success metric.
- Treat job-board results, LinkedIn posts, recruiter messages, and job descriptions as leads. Verify the employer's own posting before drafting or applying.
- Preserve original resumes. Build targeted copies for each role.
- Use only evidence the candidate has reviewed or provided. Keep genuine gaps visible.
- An agent may research, draft, render, and organize. It must not submit applications, send messages, accept invitations, or change public profiles without the candidate's explicit approval in that conversation.
- Store the job description, tailored materials, questions/answers, and outcome together for each application.

## The sequence

| Step | File | Outcome |
| --- | --- | --- |
| 0 | `META-PROMPT.md` | Tell the candidate's agent how to use this package safely. |
| 1 | `01-repository-audit.md` | Map existing tools and protect current work. |
| 2 | `02-candidate-intake.md` | Create an evidence-backed candidate profile. |
| 3 | `03-discovery-configuration.md` | Define role, location, company, and exclusion filters. |
| 4 | `04-pipeline-and-quality-gates.md` | Configure liveness, deduplication, fit review, and approval rules. |
| 5 | `05-first-discovery-cycle.md` | Run an initial scan and return a small verified shortlist. |
| 6 | `06-role-evaluation-and-application.md` | Evaluate one role, prepare materials, and stop before submission. |

Use the templates in `templates/` only after the candidate's facts and target market have been reviewed. They are deliberately blank where personal judgment belongs.

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
- Desired roles, seniority, industries, and geography
- Minimum compensation or employment constraints, if any
- Companies to watch and companies to avoid
- Recent work samples, projects, certifications, and quantified outcomes
- Whether the candidate wants direct applications, referral-first outreach, or both

## Maintenance cadence

Run discovery weekly, or more often only when there is an active application push. For every role that survives the first filter:

1. Recheck liveness on the employer's official page.
2. Evaluate fit against real evidence.
3. Check referral paths before the direct-application deadline.
4. Prepare materials only after the candidate decides it is worth pursuing.
5. Record the outcome and use it to improve future targeting.
