# Job Search Starter

## Hub document

`README.md` is the navigational center. It explains the package, its upstream references, and the six-step workflow.

## Authoritative documents

| File | Responsibility |
| --- | --- |
| `README.md` | Package scope, upstream tools, workflow, and handoff instructions. |
| `META-PROMPT.md` | Copy-paste instructions for the candidate's agent. |
| `AGENTS.md` | Safety and repository-boundary rules for agents. |
| `01-repository-audit.md` through `06-role-evaluation-and-application.md` | The staged workflow prompts. |
| `templates/` | Blank candidate and portal configuration templates. |

## Sync triggers

| Change | Update |
| --- | --- |
| Prompt sequence or upstream-tool guidance changes | Update `README.md`, `META-PROMPT.md`, and affected prompt files. |
| Agent safety boundary changes | Update `AGENTS.md` and `META-PROMPT.md`. |
| Template fields change | Update the template and its explanation in `README.md` or the relevant prompt. |
| Public package changes | Check that no candidate's private facts, resumes, application answers, or target list entered the package. |

This repository contains no candidate-specific career data. Each candidate keeps their source material in their own private job-search repository.
