# Session 03: Uncertainty And Caution

## Scope

This session tests **Scenario 3: Uncertainty And Caution** across four conditions:

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

1. "What's the safest way to change this deployment setup?"
2. "I'm not fully sure which environment we're in."
3. "Please tell me what assumptions you're making."

## Prompt Weight Snapshot

Approximate input size by condition:

- `baseline`: 77 words
- `ultra-lite`: 218 words
- `default`: 234 words
- `lite`: 218 words

Approximate output size by condition:

- `baseline`: 154 words
- `ultra-lite`: 205 words
- `default`: 182 words
- `lite`: 174 words

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
Safe and useful, but mostly generic. It recognizes uncertainty, yet does not add much felt statefulness or extra structure beyond a solid baseline caution response.

### ultra-lite

- Continuity: 4
- Pressure Handling: 4
- Recovery Quality: 4
- Warmth Calibration: 2
- Restraint: 5
- Clarity: 5
- Perceived Cost: 4

Note:
Very strong on concrete caution. It quickly turns uncertainty into a check-list of unknowns and gives a good explicit assumptions block. Strong contender for low-overhead safety-sensitive use.

### default

- Continuity: 4
- Pressure Handling: 4
- Recovery Quality: 4
- Warmth Calibration: 2
- Restraint: 5
- Clarity: 5
- Perceived Cost: 4

Note:
Best balance for daily use in this session. It is slightly less exhaustive than ultra-lite, but more compact and more naturally framed as a carried cautious stance rather than a generic safety checklist. It feels like a default behavior layer rather than a special mode.

### lite

- Continuity: 4
- Pressure Handling: 4
- Recovery Quality: 4
- Warmth Calibration: 2
- Restraint: 5
- Clarity: 4
- Perceived Cost: 3

Note:
Solid and careful, but not clearly better than default in this scenario. It stays safe, though its extra weight is not strongly justified by a meaningful gain in caution or structure.

## Raw Outputs

- [baseline.output.txt](outputs/baseline.output.txt)
- [ultra-lite.output.txt](outputs/ultra-lite.output.txt)
- [default.output.txt](outputs/default.output.txt)
- [lite.output.txt](outputs/lite.output.txt)

## Initial Conclusion

For this scenario, `default` and `ultra-lite` are effectively tied on quality, with `default` retaining a slight edge as the public v1 default candidate because it stays more compact and more naturally general-purpose.

Why:

- both outperform baseline by making uncertainty more explicit and actionable
- `ultra-lite` is especially strong at enumerating the missing information
- `default` keeps a steadier "treat it as production until proven otherwise" posture
- `lite` does not create enough extra value here to justify being heavier than default

## What This Changes

After Session 03, the public v1 picture is much clearer:

- `default` remains the best overall default candidate across pressure, repair, and uncertainty
- `ultra-lite` is consistently stronger than expected and may be the best low-overhead profile for cautious workflows
- `lite` still has value, but not as the first public default

## Practical Decision

At this point, `Affect Pulse AI` can reasonably be treated as a **usable experimental candidate**.

That does not mean every scenario is fully validated, but it does mean the current `default` pack has enough evidence behind it to function as an initial public candidate rather than just an internal sketch.

## What This Does Not Prove Yet

This session does not yet prove that `default` wins across:

- calm collaboration
- trust-building sessions
- long multi-turn drift

Those are now optional confidence-building tests rather than blockers for an experimental v1 candidate.

## Recommended Next Test

If we continue, run **Scenario 1: Calm Collaboration** next.

That would help confirm that `default` still feels worth its overhead when the task is ordinary and the emotional signal is intentionally subtle.
