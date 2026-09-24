# Prompt 4: Install Pipeline and Quality Gates

```text
Set up a private, supervised job-search pipeline in this repository. Preserve existing application history. Do not submit applications, send outreach, or write to external systems.

Use https://github.com/santifer/career-ops as the primary reference for ATS scans, official-page liveness verification, and tracker structure. Use https://github.com/MadsLorentzen/ai-job-search as a secondary reference for PDF/ATS checks, interview preparation, outcome archiving, and optional Gmail status-signal review.

If the repository audit approved adding Career-Ops and it is not already present, add it as a separate upstream checkout rather than a fork. Keep private candidate data and generated application materials outside that checkout. If the existing repository already has equivalent working capabilities, preserve them and document the mapping instead of duplicating them.

AI Job Search warns that forks of its public repository are public and its setup stores personal details in tracked files. If the candidate adopts it, create a private repository with the public project configured as an upstream remote. Do not put candidate data in a public fork.

The pipeline must record: company, role, official URL, source, date discovered, verified liveness state, location, compensation if advertised, fit verdict, evidence IDs and gaps, referral path and cutoff, selected resume variant, application-field completeness, application status, next action and date, and links to the dated application record.

Implement or document these gates:

1. Official-source liveness: a search result or social post is only a lead. Confirm the employer's own posting and an active application path before evaluation.
2. Deduplication: prevent duplicate pipeline entries and direct-plus-agency double applications.
3. Evidence check: every resume claim, application answer, and interview story must map to the candidate evidence base. Mark claims candidate-confirmed when no source document exists.
4. Resume check: compare the tailored resume with all relevant base variants. Review the whole career story, including titles, dates, overlaps, gaps, and project choices. Preserve the candidate's template and inspect both the rendered PDF and text layer.
5. Application check: inspect the live form and inventory every required and useful optional question, field, limit, attachment, and supplemental task. Leave personal, legal, and demographic decisions to the candidate.
6. Referral check: distinguish actual relationships from mutual connections and public profile signals. Set a direct-application cutoff so a referral route does not stall a live application.
7. Human approval: stop before each message, referral request, external-account connection, calendar action, or application submission. Approval for one action does not authorize another.
8. Outcome learning: preserve the exact submitted materials and confirmation, then record interviews, rejections, offers, withdrawals, follow-ups, and candidate-reviewed lessons.

Add a weekly-review view that returns only the five most promising new roles and explains why each is worth investigating or skipping.
```

## Decision rules worth preserving

- Do not wait indefinitely for a vague referral promise. Set a direct-application cutoff.
- A late referral should attach to an existing application when possible, not create a duplicate.
- Do not treat an indexed or reposted job as live without checking the employer page.
- Do not write a custom resume before the candidate agrees the role is worth the effort.
