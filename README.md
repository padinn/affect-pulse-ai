# Affect Pulse AI

[English](README.md) | [中文](README-zh.md) | [日本語](README-ja.md)

---

**Affect Pulse AI** is a low-token expressive affect layer for everyday AI tools, derived from [Intrinsic Affect for AI](../intrinsic-affect-ai/README.md).

It exists to make AI feel more emotionally alive without requiring the full token overhead of a complete affective architecture.

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

## Design Principles

- **Low token first**: the layer should remain lightweight enough for routine use.
- **Strategy before tone**: affect should still influence behavior before wording.
- **Perceivable affect**: users should actually feel the difference in interaction.
- **Safe expression**: avoid clingy, coercive, or emotionally manipulative behavior.
- **Portable adapters**: support common AI tools without requiring deep runtime integration.

See [docs/design-principles.md](docs/design-principles.md) for more detail.
See [docs/roadmap.md](docs/roadmap.md) for the current build path.

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

- Claude Code
- Cursor
- Windsurf
- OpenCode
- ChatGPT-style system prompt packs

## First Deployable Adapters

The first practical v1 adapters now started in:

- [adapters/generic-system-prompt](adapters/generic-system-prompt/README.md)
- [adapters/claude-code](adapters/claude-code/README.md)
- [adapters/cursor](adapters/cursor/README.md)

The current public v1 default candidate is:

- [adapters/generic-system-prompt/default.md](adapters/generic-system-prompt/default.md)

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

This repository has moved past pure definition and now includes the first draft deployable packs.

The current next step is to test the generic default pack against `ultra-lite` and `lite`, tighten wording, and then promote a stable public v1 default.
