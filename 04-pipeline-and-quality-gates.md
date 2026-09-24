# Prompt 4: Install Pipeline and Quality Gates

```text
Set up a private, supervised job-search pipeline in this repository. Preserve existing application history. Do not submit applications, send outreach, or write to external systems.

Use https://github.com/santifer/career-ops as the primary reference for ATS scans, official-page liveness verification, and tracker structure. Use https://github.com/MadsLorentzen/ai-job-search as a secondary reference for PDF/ATS checks, interview preparation, outcome archiving, and optional Gmail status-signal review.

If the repository audit approved adding Career-Ops and it is not already present, add it as a separate upstream checkout rather than a fork. Keep private candidate data and generated application materials outside that checkout. If the existing repository already has equivalent working capabilities, preserve them and document the mapping instead of duplicating them.

AI Job Search warns that forks of its public repository are public and its setup stores personal details in tracked files. If the candidate adopts it, create a private repository with the public project configured as an upstream remote. Do not put candidate data in a public fork.

The pipeline must record: company, role, official URL, source, date discovered, verified liveness state, location, compensation if advertised, fit verdict, gaps, referral route, application status, next action, and links to all materials.

Implement or document these gates:

1. Official-source liveness: a search result or social post is only a lead. Confirm the employer's own posting and an active application path before evaluation.
2. Deduplication: prevent duplicate pipeline entries and direct-plus-agency double applications.
3. Evidence check: every resume bullet and form answer must have a source in the candidate evidence layer.
4. Material check: preserve the chosen resume template, render the final document, and check the PDF text layer before it is marked ready.
5. Human approval: stop before every submission, outreach message, referral request, or calendar action.
6. Outcome learning: preserve submitted materials and record interviews, rejections, offers, silence, and actionable feedback.

Add a weekly-review view that returns only the five most promising new roles and explains why each is worth investigating or skipping.
```

## Decision rules worth preserving

- Do not wait indefinitely for a vague referral promise. Set a direct-application cutoff.
- A late referral should attach to an existing application when possible, not create a duplicate.
- Do not treat an indexed or reposted job as live without checking the employer page.
- Do not write a custom resume before the candidate agrees the role is worth the effort.
