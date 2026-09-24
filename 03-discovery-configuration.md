# Prompt 3: Configure Discovery for This Candidate

Use the intake output, not another candidate's settings. If the repository audit recommended Career-Ops, use its `portals.yml` and `config/profile.yml` as the configuration targets. If the audit chose a different existing system, write an equivalent configuration in that system's source-of-truth files instead.

```text
Configure the candidate's job-discovery system from their evidence layer and preferences. Do not copy another candidate's title filters, companies, or role taxonomy.

Use Career-Ops as the primary reference for ATS discovery and liveness behavior: https://github.com/santifer/career-ops. Use AI Job Search only as a secondary reference for ranking, drafting, outcomes, and interview preparation: https://github.com/MadsLorentzen/ai-job-search.

Produce a reviewed configuration with:

1. Three to five primary target role families, each with title variants and adjacent titles.
2. Secondary and exploratory role families, clearly separated from primary targets.
3. Positive title and skill signals, negative signals, and seniority rules.
4. Geography and work-arrangement rules, including how to treat generic “Remote” postings.
5. A company watchlist, an avoid list, and a plan for discovering new employers.
6. Search queries for official ATS boards, plus any industry-specific boards that fit this candidate.
7. A short evaluation rubric: role scope, evidence match, level, location, compensation, company quality, and career direction.
8. Explicit exclusions that prevent volume-based searching.

Ask the candidate to approve the role families and exclusions before activating a broad scan. Explain every proposed filter in plain English.
```

## Starting point for non-engineering project, program, and BA candidates

Do not treat this as a fixed configuration. It is a menu of terms to validate with the candidate:

- Project Manager, Program Manager, Technical Program Manager
- Business Analyst, Business Systems Analyst, Systems Analyst
- Implementation Manager, Professional Services, Customer Delivery
- Operations Manager, Business Operations, Strategy and Operations
- Transformation, Process Improvement, Change Management, PMO
- Domain-specific variants such as healthcare operations, financial operations, supply chain, public sector, ERP, CRM, data, or compliance

The candidate's actual industry, level, and evidence should determine which terms become primary. For many project-management and BA searches, domain specificity and employment type matter more than generic title similarity.
