# Rating Rubrics

Scores are anchored so they mean the same thing across projects. Pick the anchor that fits best, then adjust by at most 1. Always justify in one line. Never average the three scores - they measure different things.

## Technical feasibility (1-10) - "Can this be built at all, with available technology?"
Higher = more feasible.

| Score | Anchor |
|---|---|
| 10 | Routine. Many shipped examples; mature, documented tooling. |
| 8-9 | Well-proven. Shipped examples exist; tooling mature; minor integration questions only. |
| 6-7 | Proven elsewhere but not with this exact stack/platform/scale; some compatibility unknowns. |
| 4-5 | Achieved only by specialist teams, research projects, or with custom tech; or depends on an API/platform with significant restrictions. |
| 2-3 | No known working example at the required bar; relies on unproven or unstable technology; key dependency is deprecated, closed, or legally blocked. |
| 1 | Not possible with current technology, or violates platform rules/law/physics (e.g. requires data the platform never exposes). |

## Implementation difficulty (1-10) - "How hard for *this* user/team?"
Higher = harder. Account for the user's skill, team size, and realistic AI-agent help.

| Score | Anchor |
|---|---|
| 1-2 | Tutorial-level. Follows a documented recipe; AI agents can do most of it reliably. |
| 3-4 | Standard app/game work; several systems but each well documented. |
| 5-6 | Multiple interacting systems, some tuning, profiling or non-trivial debugging; agents help with code but not with feel/perf. |
| 7-8 | Demanding: custom engine-level work, real-time networking, heavy optimisation, ML training, low-level platform/hardware integration, or extensive content production. |
| 9 | Specialist/senior-team territory; years of domain expertise normally required. |
| 10 | Frontier/research problem; no clear path even for experts. |

Mention explicitly which parts AI help reduces (boilerplate, docs-heavy integration) and which it barely touches (game feel, animation polish, perf on real hardware, hardware debugging, art/audio quality).

## Expected achievable quality (1-10) - "How good will the result realistically be?"
Relative to the user's stated quality bar and to reference products in the genre/category.

| Score | Anchor |
|---|---|
| 9-10 | Matches or rivals professional reference products. |
| 7-8 | Clearly polished; users would see it as a solid indie/commercial-grade product. |
| 5-6 | Works and is usable, but visibly rough in places (feel, visuals, edge cases, performance). |
| 3-4 | Functional prototype quality; noticeable gaps against what the user is imagining. |
| 1-2 | Barely functional or very likely to disappoint. |

State the quality *ceiling* of the recommended approach and the *likely* result given resources if they differ (e.g. "ceiling 8, likely 6 solo in 3 months").

## Confidence level

| Level | Meaning |
|---|---|
| **High** | Core claims verified with primary sources; similar projects examined; few unknowns, none critical. |
| **Medium** | Main claims supported, but some estimates rest on analogy; one or more unknowns could shift scores by 1-2. |
| **Low** | Little research possible, novel combination, or critical unknowns that could flip the verdict. A "Prototype first" verdict often pairs with Low/Medium confidence. |

## Consistency rules
- Feasibility <= 3 -> verdict cannot be "Proceed".
- Any critical unknown that could flip the verdict -> verdict should be "Prototype first" (or "Do not proceed" if even a good prototype result would not rescue it).
- Quality well below the user's stated bar -> "Proceed with limitations" (with the bar adjusted) or "Do not proceed".
- Difficulty 9-10 for a solo/beginner developer -> say so plainly in the executive summary.
