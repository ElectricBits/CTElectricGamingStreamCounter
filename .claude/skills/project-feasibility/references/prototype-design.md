# Prototype Design

**Principle:** before committing to full development, build the **smallest experiment that can prove or disprove the riskiest assumption**. A prototype is a question, not a mini-version of the product.

## When a prototype is required
Any system rated "uncertain" in decomposition, or any unknown that could change the verdict, scores by 2+, or the architecture choice.

## Designing one
For each prototype specify:
1. **Question** - one specific, answerable question. ("Can a rope-swing in Godot 4 feel responsive at 60 fps without jitter?" - not "build the swinging game".)
2. **Smallest build** - the minimum code/content needed. Grey boxes, placeholder art, hard-coded values, no menus, no save system.
3. **Pass/fail criterion - decided before building.** Measurable where possible (fps, ms latency, memory, error rate, % of test inputs handled), otherwise a defined judgement test (e.g. "3 people play for 5 minutes and rate swinging feel 4/5+", "side-by-side with reference clip, no visible foot-sliding").
4. **Test conditions** - on what hardware, with what data, at what scale.
5. **Time-box** - hours/days. If it can't be shown within the time-box, that is itself a result.
6. **Decision mapping** - pass -> next step; fail -> fallback approach or verdict change.

Order prototypes by risk: the one most likely to kill the project goes first.

## Patterns by risk type

| Risk type | Prototype pattern | Example |
|---|---|---|
| Physics / feel | Single mechanic in an empty test level; tune with exposed parameters | Swing + release + land on one rope between two platforms |
| Animation quality | One character, 3-5 key transitions, compared against a reference clip | Idle -> run -> jump -> land with blending and IK feet |
| Performance | Stress scene at target scale on the *minimum* target hardware; profile | 500 enemies on screen on a mid-range phone; measure frame time |
| API compatibility | Minimal script calling the real API with real credentials (in a sandbox), covering auth, the key endpoint, rate limits, error cases | Subscribe to a platform's follow events and log them for 1 hour |
| Networking | Two clients + server with artificial latency/packet loss | 150 ms latency, 2% loss: do players desync? |
| AI/ML quality | Small evaluation set (20-100 real examples) run through candidate models with a scoring rubric | Does the model classify chat messages correctly >= 90%? |
| Platform restriction | Build-and-deploy "hello world" to the real target (store build, browser, device, OBS browser source) using the risky capability | Does the overlay's WebGL effect run in OBS's browser source at acceptable CPU cost? |
| Content pipeline | Produce one finished asset end-to-end through the intended pipeline; time it | One character from generation/modelling to in-engine, rigged and animated |
| Integration between systems | Thin end-to-end slice touching each risky boundary once | Input -> server -> DB -> overlay update round-trip, measured |

## Anti-patterns
- Prototype that grows into the product ("we'll just keep building on it"). Keep prototype code throwaway unless deliberately promoted.
- No pass/fail criterion -> every result looks like success.
- Testing on the dev's high-end PC when the target is low-end.
- Testing the easy part (UI) instead of the risky part.
- Prototyping several unknowns at once so a failure can't be attributed.

## Reporting results back
When the user returns with results, update the assessment: treat measured results as [Verified] evidence, re-score affected sections, and re-issue the verdict with a "What changed" note.
