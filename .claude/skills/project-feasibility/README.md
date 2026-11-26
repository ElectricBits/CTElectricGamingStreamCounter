# project-feasibility (Claude Code skill)

An evidence-based feasibility assessor for software and game projects. It researches, scores, sizes and designs prototypes - it does **not** build the project.

## Install
Copy this folder to your global skills directory so it works in every project:

- macOS / Linux: `~/.claude/skills/project-feasibility/`
- Windows: `%USERPROFILE%\.claude\skills\project-feasibility\`

Restart Claude Code (or start a new session). Check it is listed by typing `/` and looking for `project-feasibility`, or ask "what skills do you have?".

## Use
- `/project-feasibility <describe the idea>`
- `/project-feasibility docs/design.md` (point it at a design doc)
- Or just ask: "Is it feasible to ... ?", "How hard would it be to ... ?" - Claude loads the skill automatically when the request matches.

## Files
| File | Purpose |
|---|---|
| `SKILL.md` | Main instructions: rules, workflow, verdicts, self-check |
| `references/report-template.md` | The 15-section report structure |
| `references/rating-rubrics.md` | Anchored 1-10 scales and confidence levels |
| `references/research-playbook.md` | How to research and grade evidence |
| `references/domain-checklists.md` | Hidden requirements and "sounds easy, often disappoints" lists per domain |
| `references/effort-estimation.md` | Per-system effort ranges, AI-assistance effects, milestones |
| `references/prototype-design.md` | Designing the smallest decisive prototype |

## Customising
- Add your usual stack/hardware to the top of `SKILL.md` under a "Default context" heading so you don't have to repeat it.
- Add domains to `references/domain-checklists.md` as you work on new kinds of projects.
