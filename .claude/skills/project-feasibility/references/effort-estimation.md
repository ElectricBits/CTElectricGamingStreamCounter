# Effort Estimation

Estimates must be **ranges with assumptions**, broken down **per system** and rolled up into **milestones**. Never a single number.

## Step 1 - State the assumptions
- Who builds it (solo / team size) and their experience with this stack.
- Hours per week available.
- Whether AI coding assistance is used.
- Whether art/audio/content is bought, generated, commissioned or made by the user.
- Quality target (prototype / polished indie / commercial).

## Step 2 - Size each system
For each system from the decomposition, give an optimistic-to-pessimistic range in hours (or days for big items) using these rough bands for an experienced solo developer, then adjust:

| System class | Typical range (experienced dev) |
|---|---|
| Standard, well-documented (CRUD screen, menu, settings page, basic API integration) | 2-16 h |
| Moderate (auth + accounts, save system, basic AI behaviour, inventory, simple multiplayer lobby) | 16-60 h |
| Demanding (character controller with good feel, networking with prediction, custom shader pipeline, sync engine, ML pipeline) | 60-300 h |
| Uncertain (no proven path) | Do not estimate the build; estimate the **prototype** only and mark the system "TBD after prototype". |

Adjustments:
- **Unfamiliar stack:** x1.5-2.
- **Beginner:** x2-3 on demanding systems.
- **Feel/polish-heavy work** (game feel, animation, UX polish): add 50-100% for tuning iterations.
- **Integration with poorly documented or unstable APIs:** add 30-100%.
- **Cross-platform:** add 20-50% per extra platform for testing and fixes.

## Step 3 - AI-assistance effect (be honest)
AI coding agents reduce effort unevenly:

| Work type | Typical effect |
|---|---|
| Boilerplate, scaffolding, CRUD, tests, docs, well-known algorithms | Large speed-up (often 2-4x) |
| Integration with well-documented APIs | Moderate speed-up |
| Debugging logic errors in code the agent can run | Moderate |
| Performance tuning, profiling on real hardware | Small |
| Game feel, animation, visual/audio judgement | Small to none - needs human iteration |
| Hardware/driver/platform-specific issues | Small; agent may not have access to the device |
| Architecture coherence over a long project | Can be negative without strong human direction (drift, duplicated systems) |

Apply speed-ups per system, not to the total. These multipliers are [Estimate]s - say so.

## Step 4 - Add the overheads people forget
- Integration & bug fixing between systems: +15-30%
- Testing/QA on real hardware: +10-20%
- Build, packaging, deployment, store submission: fixed chunk (often 8-40 h first time)
- Content production (art, audio, levels, writing): estimate separately - often the largest item in games
- Learning time for new tech

## Step 5 - Milestones
Group into milestones that each produce something testable, e.g.:
1. **M0 - Prototypes** that settle critical unknowns (time-boxed).
2. **M1 - Vertical slice / core loop**: smallest end-to-end playable/usable version.
3. **M2 - Feature-complete**: all planned systems working.
4. **M3 - Content & polish**.
5. **M4 - Release**: packaging, store, launch tasks.

Give each a range and convert the total to calendar time at the user's hours/week.

## Step 6 - Sanity checks
- Compare against similar projects found in research (how long did they take, how big was the team?).
- Highest-uncertainty system: what happens to the total if it takes the pessimistic value x2?
- If the total exceeds the user's available time by a lot, say so and propose scope cuts - don't shrink the estimate.
