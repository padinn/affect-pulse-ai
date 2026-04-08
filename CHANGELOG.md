# Changelog

All notable changes to Affect Pulse AI will be documented in this file.

## [0.3.0] - 2026-04-08

This release makes the core project and the voice layer boundaries explicit.

### Added

- text-only mode support for the core affect layer
- explicit TTS optionality for all users
- Azure Speech guidance as the preferred emotional voice adapter
- Edge TTS fallback guidance
- clearer separation between text rhythm and voice style
- emotional text-card guidance for laughter, crying, and short burst replies
- Azure TTS documentation and local test helpers

### Changed

- the project description now emphasizes that TTS is optional, not required
- the core affect layer now documents its text-first behavior more clearly
- the voice layer is now treated as an adapter layer instead of a core dependency
- the docs now distinguish text shaping from speech shaping

### Notes

- The core skill remains usable in text-only mode.
- If speech is enabled, Azure Speech is the preferred emotional adapter.
- Edge TTS remains a fallback adapter.
- The parent project, Intrinsic Affect for AI, remains the canonical theory and spec layer.

