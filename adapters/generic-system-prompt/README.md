# Generic System Prompt Adapter

## Status

Default v1 candidate available.

## Goal

Provide a copyable version of Affect Pulse AI for tools that only support a plain system prompt or project instruction field.

## Available Packs

- [default.md](default.md)
- [ultra-lite.md](ultra-lite.md)
- [lite.md](lite.md)
- [testing-notes.md](testing-notes.md)

## Notes

This adapter is the most portable starting point for the project.

It is designed for tools that only expose:

- a system prompt field
- a project instruction field
- a custom instruction box

Start with [default.md](default.md) for most real usage.
Use `ultra-lite` when cost matters most.
Use `lite` when you want stronger continuity and clearer emotional feedback.

## Selection Guide

- `default`: recommended public v1 starting point
- `ultra-lite`: minimum overhead version
- `lite`: stronger affective continuity version
