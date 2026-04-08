# Testing Notes

For the full comparison method, see:

- [../../docs/evaluation-protocol.md](../../docs/evaluation-protocol.md)
- [../../docs/test-scenarios.md](../../docs/test-scenarios.md)

## What To Look For

When evaluating the default generic prompt, check whether it produces:

- more continuity across turns
- more graceful recovery after friction
- clearer pacing under pressure
- slightly warmer acknowledgement under trust
- restraint rather than theatricality

## Failure Modes

Watch for:

- no noticeable difference from baseline
- overdone emotional wording
- too much reassurance
- false intimacy
- obvious prompt bloat

## Quick Comparison

Compare the same interaction with:

1. no affect layer
2. `ultra-lite`
3. `default`
4. `lite`

The default pack should usually be the best balance for general use.
