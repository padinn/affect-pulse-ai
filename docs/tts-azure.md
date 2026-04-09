# Azure Speech TTS

Azure Speech is currently the strongest TTS path we have found for carrying Affect Pulse AI emotions into audible output.

This document is only about the voice adapter layer.
The core Affect Pulse AI skill still works in text-only mode, so you can use the project even if you do not connect any TTS at all.

## Why It Matters

We compared several TTS paths during experimentation:

- Edge TTS was not expressive enough for the emotional target
- Azure Speech produced clearly audible differences across styles

MiniMax was tested earlier, but it is no longer part of the preferred deployment path.

That makes Azure Speech the best current fit for emotional output from Affect Pulse AI.

## Recommended Mapping

The first stable mapping is:

- `happy` -> `cheerful`
- `calm` -> `calm`
- `fearful` -> `fearful`
- `angry` -> `angry`
- `sad` -> `sad`

This is intentionally small. The goal is audible difference first, completeness later.

## Voice And Style Notes

The first working voice used for testing was:

- `zh-CN-XiaoyiNeural`

The best test signal came from the `style` field in SSML, not from plain text heuristics alone.

For the current OpenClaw setup, the intended pattern is:

- let the text layer already lean toward the target emotional state
- then let Azure Speech amplify that state through `style` and `styleDegree`
- keep the default voice stable, so emotion changes are easier to hear than voice identity changes

In practice, pacing and rhythm now mostly come from the text layer:

- short, sharp lines feel faster
- longer, fuller clauses feel slower
- short burst replies create a more emotional rhythm
- laughter, crying, and sentence shape now do most of the expressive work

Azure is the audible amplifier, not the main rhythm writer.

Important implementation note:

- do not reintroduce an extra `prosody` wrapper around `cheerful` or `sad` by default
- we tested that this combination can trigger Azure-side synthesis failures in this setup
- the current stable path is `style` + `styleDegree` plus text shaping, without the extra wrapper
- if you experiment with `prosody` later, treat it as an opt-in edge case, not the baseline

For cheerful states, light laughter markers like `哈哈` or `嘻嘻` can be used when they feel natural; the voice layer will usually sound more upbeat and smile-like rather than literally laughing.

If the situation is emotionally low or needs repair, a short `recovery burst` of 2 or 3 follow-up lines can help the text and voice layers land more naturally, as long as the burst stays short and functional.

For Telegram voice notes, keep at least one line as a full clause when you want audible output. Very tiny fragments are more likely to be skipped than a sentence with some body.

If the happy state is mostly laughter, a full sentence like "哈哈，这次真的顺了" usually gives the most natural result for voice. The same goes for sad replies: a spoken sentence with some哭意 is usually better than a pile of cry-only fragments when the reply is intended to be voiced.

If the reply is meant to be voiced, avoid splitting it across blank-line paragraphs; keep the cheerful spoken part as one continuous paragraph so the voice path stays intact.

Very sad bursts should stay soft and a little slower; very happy bursts can be brighter and more playful, but still short enough that the voice sounds like a human reaction instead of a performance.

## Local Test Scripts

The repository includes small helpers for testing:

- `tools/azure_speech_rest_test.py`
- `tools/azure_speech_batch_test.py`
- `tools/azure_ssml_builder.py`

For a very short working reference, see:

- [docs/emotion-card.md](emotion-card.md)

## Sample Pack

The generated sample pack is stored under:

- `samples/azure`

## Practical Recommendation

If Affect Pulse AI is used for speech output, Azure Speech should be treated as the preferred TTS path for emotionally expressive voices.

Edge TTS can remain the fallback path, but it should not be the default emotional path.
