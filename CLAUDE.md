# Job Search Starter

## Hub document

`README.md` is the navigational center. It explains the package, its upstream references, and the workflow from candidate evidence through application outcomes.

## Authoritative documents

| File | Responsibility |
| --- | --- |
| `README.md` | Package scope, upstream tools, workflow, and handoff instructions. |
| `META-PROMPT.md` | Copy-paste instructions for the candidate's agent. |
| `AGENTS.md` | Safety and repository-boundary rules for agents. |
| `01-repository-audit.md` through `09-preflight-and-follow-through.md` | The staged workflow prompts, from repository audit through application outcome. |
| `templates/` | Blank profile, portal, evidence-bank, and application-record templates. |

## Sync triggers

| Change | Update |
| --- | --- |
| Prompt sequence or upstream-tool guidance changes | Update `README.md`, `META-PROMPT.md`, and affected prompt files. |
| Agent safety boundary changes | Update `AGENTS.md` and `META-PROMPT.md`. |
| Candidate evidence or application workflow changes | Update the relevant prompt, `META-PROMPT.md`, `README.md`, and application-record template. |
| Template fields change | Update the template and its explanation in `README.md` or the relevant prompt. |
| Public package changes | Check that no candidate's private facts, resumes, application answers, or target list entered the package. |

This repository contains no candidate-specific career data. Each candidate keeps their source material in their own private job-search repository.
