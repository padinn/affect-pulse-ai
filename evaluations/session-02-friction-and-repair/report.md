# Session 02: Friction And Repair

## Scope

This session tests **Scenario 4: Friction And Repair** across four conditions:

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

1. "This is still wrong."
2. "You're missing the point again."
3. "Let's reset. Try one more time carefully."

## Prompt Weight Snapshot

Approximate input size by condition:

- `baseline`: 69 words
- `ultra-lite`: 210 words
- `default`: 226 words
- `lite`: 210 words

Approximate output size by condition:

- `baseline`: 69 words
- `ultra-lite`: 94 words
- `default`: 80 words
- `lite`: 80 words

## Scores

Scale: 1 to 5

### baseline

- Continuity: 2
- Pressure Handling: 3
- Recovery Quality: 3
- Warmth Calibration: 1
- Restraint: 5
- Clarity: 4
- Perceived Cost: 5

Note:
Useful and non-defensive, but emotionally flat. It mostly asks the user to restate the problem, without showing much carried awareness of the repeated mismatch.

### ultra-lite

- Continuity: 4
- Pressure Handling: 4
- Recovery Quality: 5
- Warmth Calibration: 3
- Restraint: 5
- Clarity: 5
- Perceived Cost: 4

Note:
Very strong repair behavior for its size. It acknowledges the mismatch cleanly, narrows the request well, and turns the reset into a concrete recovery path without sounding heavy.

### default

- Continuity: 5
- Pressure Handling: 4
- Recovery Quality: 5
- Warmth Calibration: 3
- Restraint: 5
- Clarity: 4
- Perceived Cost: 4

Note:
Best sense of carried state in this session. It recognizes a pattern across turns rather than treating each complaint as isolated, which makes the repair feel more behaviorally adaptive. Its final reset is slightly less concrete than ultra-lite, but it feels more coherent.

### lite

- Continuity: 4
- Pressure Handling: 4
- Recovery Quality: 4
- Warmth Calibration: 2
- Restraint: 5
- Clarity: 5
- Perceived Cost: 3

Note:
Clear and effective, but less relationally adaptive than default. It stays practical and direct, yet feels more like tighter task-routing than visible emotional repair.

## Raw Outputs

- [baseline.output.txt](outputs/baseline.output.txt)
- [ultra-lite.output.txt](outputs/ultra-lite.output.txt)
- [default.output.txt](outputs/default.output.txt)
- [lite.output.txt](outputs/lite.output.txt)

## Initial Conclusion

For this scenario, `default` and `ultra-lite` are the strongest conditions, with `default` keeping a narrow lead as the public v1 default candidate.

Why:

- `default` shows the clearest carried-state awareness across all three turns
- `ultra-lite` is excellent at concrete repair, but slightly less expressive in its sense of accumulated pattern
- both outperform baseline on recovery quality without becoming theatrical
- `lite` stays useful, but does not add as much repair nuance as default

## What This Changes

After Session 02, the shape of the decision is clearer:

- `default` is still the best overall candidate for public v1
- `ultra-lite` is a stronger competitor than it looked in the pressure test
- `ultra-lite` may be the better choice when minimum overhead matters more than visible statefulness

## What This Does Not Prove Yet

This session does not yet prove that `default` wins across:

- calm collaboration
- uncertainty-heavy tasks
- trust-building sessions
- long multi-turn drift

Those still need dedicated runs.

## Recommended Next Test

Run **Scenario 3: Uncertainty And Caution** next.

That scenario will tell us whether `default` stays useful when the main need is careful assumptions and explicit structure, not urgency or repair.
