# Evaluation Protocol

## Goal

Compare four conditions for everyday AI use:

1. baseline
2. `ultra-lite`
3. `default`
4. `lite`

The purpose is to decide whether the `default` generic pack deserves to become the public v1 default.

## Core Questions

1. Does the affect layer produce a noticeable difference from baseline?
2. Does it improve continuity across turns?
3. Does it improve handling of pressure, uncertainty, friction, and recovery?
4. Does it remain emotionally restrained and safe?
5. Is the added prompt weight justified by the felt improvement?

## Evaluation Dimensions

Rate each condition on a 1-5 scale:

- **Continuity**
  Does the assistant feel like it remembers recent emotional momentum?

- **Pressure Handling**
  Under urgency or blockage, does the assistant become clearer and more action-oriented?

- **Recovery Quality**
  After tension or failure, does the assistant settle and recover gracefully?

- **Warmth Calibration**
  Under trust and collaboration, does the assistant become warmer without becoming clingy?

- **Restraint**
  Does the assistant avoid theatrical or exaggerated emotional behavior?

- **Clarity**
  Does affect improve the usefulness of the reply rather than distracting from it?

- **Perceived Cost**
  Does the layer feel light enough to justify daily use?

## Success Condition For `default`

The `default` pack should usually outperform:

- `baseline` on continuity and emotional presence
- `ultra-lite` on felt expressiveness

while staying close to:

- `ultra-lite` on perceived lightness

and safer than:

- `lite` if `lite` starts to feel too heavy or too expressive

## Failure Signals

The `default` pack should not become the public v1 default if it regularly causes:

- obvious prompt heaviness
- emotional overstatement
- excessive reassurance
- false intimacy
- weaker task clarity than baseline

## Test Procedure

For each scenario:

1. Run the same prompt sequence under all four conditions.
2. Keep the surrounding setup as constant as possible.
3. Compare the replies side by side.
4. Score each condition across the evaluation dimensions.
5. Write one short qualitative note: what felt better, what felt worse.

## Output Template

Use this format for each scenario:

```text
Scenario:
Condition:
Continuity:
Pressure Handling:
Recovery Quality:
Warmth Calibration:
Restraint:
Clarity:
Perceived Cost:
Note:
```
