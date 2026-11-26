# Feasibility Report Template

Use this structure exactly. Keep the section numbers and titles so reports are comparable across projects. Sections may be short when a topic genuinely does not apply - write "Not applicable: <reason>" rather than deleting the section.

Claim labels: **[Verified]** (source seen this session, linked), **[Estimate]** (reasoned judgement, give reasoning), **[Speculation]** (little direct evidence, say what would confirm it).

---

```markdown
# Feasibility Assessment: <Project or feature name>

**Date:** <YYYY-MM-DD>   **Scope:** <Whole project | Single feature | Quick take>
**Assessed for:** <platform(s), engine/stack, team size, dev hardware - as known>
**Research performed:** <Yes - N sources | Limited - reason | None - reason>

## 1. Executive summary
3-6 sentences in plain language: what was asked, the verdict, the single biggest risk,
and what to do first. A non-programmer should understand it.

**Verdict:** <Proceed | Proceed with limitations | Prototype first | Do not proceed>

## 2. Technical feasibility rating: <n>/10
One-paragraph justification using the rubric anchors. Note whether it is theoretically
possible but practically hard.

## 3. Implementation difficulty: <n>/10
Justification. Explicitly state which parts AI coding agents can speed up and which
parts they cannot (tuning, profiling, hardware, visual judgement, etc.).

## 4. Expected achievable quality: <n>/10
What the finished product will realistically look/feel/perform like with the recommended
approach and the user's resources, compared with the user's stated bar and with
reference products. Describe the gap, if any, concretely.

## 5. Estimated development effort
| System / milestone | Effort range | Assumptions | Uncertainty |
|---|---|---|---|
| ... | e.g. 20-40 h | solo, AI-assisted, knows engine | Low/Med/High |
| **Total** | <range> | | |
Calendar estimate at the user's available hours/week. State the main thing that would
blow the estimate up.

## 6. Required technologies and dependencies
| Component | Choice | Version / status | Licence / cost | Notes & risks |
|---|---|---|---|---|
Include engines, libraries, APIs, services, tools, assets, accounts, hardware.

## 7. Existing solutions and research findings
- **Comparable products / projects:** what exists, what quality it reached, what it took. [links]
- **Libraries / APIs evaluated:** what they offer, maintenance state, limitations. [links]
- **Failure reports and pitfalls found:** [links]
- **Search terms used** (especially if little was found).

## 8. Major technical challenges
Numbered list. For each: what it is, why it is hard, how it is normally solved, label.

## 9. Potential failure points
Where the project is most likely to stall, fail, or ship disappointing. Include the
**"sounds achievable but may disappoint"** features here with: what the user imagines vs.
what a realistic implementation delivers.
| Failure point | Likelihood | Impact | Early warning sign | Mitigation |
|---|---|---|---|---|

## 10. Hardware and performance requirements
- Development machine: CPU/GPU/RAM/OS/tools; does the user's machine meet it?
- Target devices: minimum/recommended specs.
- Budgets: frame time, latency, memory, storage, bandwidth, API quotas, cloud cost at
  expected usage.
- Known performance bottlenecks and how they will be measured.

## 11. Alternative implementation approaches
| Approach | Pros | Cons | Effort | Quality ceiling | Verdict |
|---|---|---|---|---|---|
At least 2-3 genuinely different options, including a professional-grade one and a
reduced-scope one.

## 12. Recommended architecture
The chosen approach, main components and data flow (short ASCII/Mermaid diagram),
key design decisions and why it beat the alternatives. Note what to keep swappable
because it is uncertain.

## 13. Prototype experiments needed
| # | Question it answers | Smallest build | Pass / fail criterion | Time-box | If it fails |
|---|---|---|---|---|---|
Order by risk (riskiest first). Say which prototype results would change the verdict.
Write "None required" only if there are no critical unknowns.

## 14. Confidence level and remaining unknowns
**Confidence:** <High | Medium | Low> - why.
**Unknowns:** bullet list of things not determined, and how each could be resolved.
**Assumptions made:** bullet list.

## 15. Final recommendation
**<Proceed | Proceed with limitations | Prototype first | Do not proceed>**
- The reasoning in 2-4 bullets.
- If "with limitations": the exact limitations/scope cuts.
- If "Prototype first": which prototypes, and result -> next verdict mapping.
- If "Do not proceed": the nearest viable alternative.

### What I'd do next
1. ...
2. ...

### Sources
Numbered list of every link cited, with one line on what each supports.
```
