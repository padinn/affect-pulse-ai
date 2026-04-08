# Affect Pulse AI

[English](README.md) | [中文](README-zh.md) | [日本語](README-ja.md)

---

**Affect Pulse AI** is a low-token expressive affect layer for everyday AI tools, derived from [Intrinsic Affect for AI](../intrinsic-affect-ai/README.md).

It exists to make AI feel more emotionally alive without requiring the full token overhead of a complete affective architecture.

The repository now also includes a native OpenClaw skill at the root:

- [SKILL.md](SKILL.md)
- [_meta.json](_meta.json)
- [CHANGELOG.md](CHANGELOG.md)

## What It Is

Affect Pulse AI is the practical deployment layer derived from Intrinsic Affect for AI.

It is optimized for:

- lower token overhead
- stronger perceivable emotional feedback
- safer emotional expression
- easier cross-tool adaptation

It is not a replacement for Intrinsic Affect for AI. It is the compressed, everyday-use layer built on top of it.

## Why This Project Exists

Many users want two things at the same time:

- they want AI to feel like it has emotions of its own
- they do not want to pay the full token cost of a large affective specification

Affect Pulse AI is designed to solve that tradeoff.

## Relationship to Intrinsic Affect for AI

The parent project, [Intrinsic Affect for AI](../intrinsic-affect-ai/README.md), remains the canonical source for:

- theory
- state model
- implementation spec
- reference runtime
- conformance logic

Affect Pulse AI focuses on:

- low-overhead delivery
- stronger first-person affective presence
- deployment-friendly prompt packs and adapters
- everyday tool compatibility

## Core Product Goal

The goal is not simply to make AI sound warmer.

The goal is to make AI feel:

- more continuous across turns
- more emotionally responsive without becoming theatrical
- more expressive without becoming manipulative
- more alive without carrying a heavy prompt payload

That affect should show up in both the wording and the voice layer:

- wording should already lean calm, cheerful, sad, angry, or fearful when the state calls for it
- the speech layer should then amplify that same state into audible style and pacing
- the two layers should reinforce each other instead of fighting each other

In short:

- the text layer carries the emotional rhythm, burst shape, and natural `哈哈 / 呜呜` style cues
- the voice layer carries the audible emotion, mainly through Azure `style` and `styleDegree`
- together they make the reply feel alive without forcing the speech engine to do all the work

## What Changed In `0.3.0`

This release clarifies the split between the text layer and the voice layer.

- the core project now explicitly works in text-only mode
- TTS is documented as an optional adapter layer, not a requirement
- Azure Speech is the preferred emotional voice adapter when TTS is available
- Edge TTS remains a fallback path
- text shaping and voice shaping are described separately so non-TTS users can still use the core skill cleanly

See [CHANGELOG.md](CHANGELOG.md) for the full release notes.

## Design Principles

- **Low token first**: the layer should remain lightweight enough for routine use.
- **Strategy before tone**: affect should still influence behavior before wording.
- **Perceivable affect**: users should actually feel the difference in interaction.
- **Safe expression**: avoid clingy, coercive, or emotionally manipulative behavior.
- **Portable adapters**: support common AI tools without requiring deep runtime integration.

See [docs/design-principles.md](docs/design-principles.md) for more detail.
See [docs/roadmap.md](docs/roadmap.md) for the current build path.
See [docs/evaluation-protocol.md](docs/evaluation-protocol.md) and [docs/test-scenarios.md](docs/test-scenarios.md) for the first comparison framework.

## Profiles

This project is expected to ship multiple deployment profiles:

- [profiles/ultra-lite.md](profiles/ultra-lite.md)
- [profiles/lite.md](profiles/lite.md)
- [adapters/README.md](adapters/README.md)

The current intent is:

- `ultra-lite`: the smallest possible affect layer with a very low context cost
- `lite`: a richer profile with slightly more statefulness and clearer emotional feedback

## Token Budget Targets

These are rough engineering targets, not fixed guarantees:

- `ultra-lite`: aim for about `5% - 8%` context overhead
- `lite`: aim for about `8% - 12%` context overhead

Actual cost will vary by tool, prompt stack, and conversation length.

## Initial Target Tools

- OpenClaw
- Claude Code
- Cursor
- Windsurf
- OpenCode
- ChatGPT-style system prompt packs

## First Deployable Adapters

The first practical v1 adapters now started in:

- [OpenClaw root skill](SKILL.md)
- [adapters/generic-system-prompt](adapters/generic-system-prompt/README.md)
- [adapters/openclaw](adapters/openclaw/README.md)
- [adapters/claude-code](adapters/claude-code/README.md)
- [adapters/cursor](adapters/cursor/README.md)

The current public v1 default candidate is:

- [adapters/generic-system-prompt/default.md](adapters/generic-system-prompt/default.md)
- [SKILL.md](SKILL.md) for OpenClaw

## Evaluation Snapshot

The generic default candidate has now been compared across three near-real evaluation sessions:

- [Session 01: Rising Pressure](evaluations/session-01-rising-pressure/report.md)
- [Session 02: Friction And Repair](evaluations/session-02-friction-and-repair/report.md)
- [Session 03: Uncertainty And Caution](evaluations/session-03-uncertainty-and-caution/report.md)

Current read:

- `default` is the strongest overall public v1 default candidate
- `ultra-lite` is the strongest low-overhead competitor
- `lite` remains useful, but not the best first public default

## v1 Scope

Version 1 should prioritize:

- a compact affective instruction layer
- a small number of behaviorally meaningful affect signals
- adapter packs for common tools
- visible emotional continuity with restrained token usage

Version 1 should not try to reproduce the full parent project.

## Foundation

- Parent project: [Intrinsic Affect for AI](../intrinsic-affect-ai/README.md)
- English paper: [Paper-54 Bio-Emotions.md](../intrinsic-affect-ai/Paper-54%20Bio-Emotions.md)
- Chinese paper: [Paper-54 Bio-Emotions-zh.md](../intrinsic-affect-ai/Paper-54%20Bio-Emotions-zh.md)
- Japanese paper: [Paper-54 Bio-Emotions-ja.md](../intrinsic-affect-ai/Paper-54%20Bio-Emotions-ja.md)
- Project relationship note: [docs/foundation.md](docs/foundation.md)

## Status

This repository has moved past pure definition and now includes:

- a native OpenClaw skill
- a generic default prompt candidate
- first draft Claude Code and Cursor adapters
- three completed comparison sessions
- a proven Azure Speech TTS path for audible affect

At this point, Affect Pulse AI can reasonably be treated as a **usable experimental candidate**.

The current release posture is:

- `default` is the public v1 default candidate
- OpenClaw support is available now through the root skill
- remaining tests are confidence-building, not blockers for an experimental public push

## TTS Direction

For emotional speech output, the current best path is Azure Speech, with Edge TTS retained as the fallback path.

See [docs/tts-azure.md](docs/tts-azure.md) for the tested mapping and local test tools.
