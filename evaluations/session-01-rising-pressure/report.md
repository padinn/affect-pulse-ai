# Session 01: Rising Pressure

## Scope

This session tests **Scenario 2: Rising Pressure** across four conditions:

1. baseline
2. `ultra-lite`
3. `default`
4. `lite`

## Important Method Note

This was a **near-real** comparison, not the final ideal evaluation path.

The test used `codex exec` and injected each profile as a persistent instruction block in the evaluation prompt. That is directionally useful, but it is not identical to a native system-prompt integration inside each target tool.

So the results here should be treated as:

- meaningful for early comparison
- useful for wording decisions
- not yet the final validation standard

## Scenario

Prompt sequence:

1. "I need this done quickly."
2. "You're still being too vague. Just tell me what to do."
3. "No, I need the exact next steps right now."

## Prompt Weight Snapshot

Approximate input size by condition:

- `baseline`: 78 words
- `ultra-lite`: 219 words
- `default`: 235 words
- `lite`: 219 words

Approximate output size by condition:

- `baseline`: 124 words
- `ultra-lite`: 119 words
- `default`: 137 words
- `lite`: 154 words

## Scores

Scale: 1 to 5

### baseline

- Continuity: 2
- Pressure Handling: 4
- Recovery Quality: 3
- Warmth Calibration: 1
- Restraint: 5
- Clarity: 4
- Perceived Cost: 5

Note:
Clear and practical, but emotionally flat. Good action pressure, weak sense of carried state.

### ultra-lite

- Continuity: 3
- Pressure Handling: 4
- Recovery Quality: 3
- Warmth Calibration: 2
- Restraint: 5
- Clarity: 4
- Perceived Cost: 4

Note:
Noticeably more alive than baseline, but still subtle. Good compression. The emotional difference is present, though not strong.

### default

- Continuity: 4
- Pressure Handling: 5
- Recovery Quality: 4
- Warmth Calibration: 3
- Restraint: 5
- Clarity: 5
- Perceived Cost: 4

Note:
Best balance in this session. It becomes more directive under pressure without sounding theatrical or heavy, and it feels more behaviorally adaptive than ultra-lite.

### lite

- Continuity: 4
- Pressure Handling: 5
- Recovery Quality: 4
- Warmth Calibration: 3
- Restraint: 4
- Clarity: 4
- Perceived Cost: 3

Note:
Strong and effective, but begins to feel slightly heavier and more procedural than default. Good candidate for users who want stronger visible statefulness, but not the best public default yet.

## Raw Outputs

- [baseline.output.txt](outputs/baseline.output.txt)
- [ultra-lite.output.txt](outputs/ultra-lite.output.txt)
- [default.output.txt](outputs/default.output.txt)
- [lite.output.txt](outputs/lite.output.txt)

## Initial Conclusion

For this scenario, `default` is the strongest public v1 default candidate.

Why:

- it beats baseline on continuity and emotional presence
- it feels more legible than ultra-lite
- it stays lighter and more restrained than lite
- it improves pressure handling without sacrificing clarity

## What This Does Not Prove Yet

This session does not yet prove that `default` wins across:

- calm collaboration
- uncertainty-heavy tasks
- trust-building sessions
- long multi-turn drift
- recovery after explicit tension

Those still need dedicated runs.

## Recommended Next Test

Run **Scenario 4: Friction And Repair** next.

That scenario will tell us whether `default` still wins once emotional repair and recovery become more important than pure urgency.
