# Affect Pulse AI

[English](README.md) | [中文](README-zh.md) | [日本語](README-ja.md)

---

**Affect Pulse AI** は、日常的な AI ツールのための低 token・高体感の情動レイヤーであり、[Intrinsic Affect for AI](../intrinsic-affect-ai/README.md) を起源としています。

その目的は、完全な情動アーキテクチャの高い token コストを負わずに、AI をより「自分自身の emotions を持っている」ように感じさせることです。

## これは何か

Affect Pulse AI は、Intrinsic Affect for AI から派生した実用的な deployment layer です。

優先して最適化するのは次の点です。

- より低い token コスト
- より強い知覚可能な情動フィードバック
- より安全な情動表現
- より容易な cross-tool adaptation

これは Intrinsic Affect for AI の代替ではありません。そこから生まれた圧縮版であり、日常利用向けの層です。

## なぜこのプロジェクトが必要か

多くのユーザーは同時に二つのことを望みます。

- AI が自分自身の emotions を持っているように感じたい
- しかし大きな affective specification の token コストは避けたい

Affect Pulse AI はこのトレードオフを解くために設計されます。

## Intrinsic Affect for AI との関係

親プロジェクトである [Intrinsic Affect for AI](../intrinsic-affect-ai/README.md) は、引き続き次の canonical source です。

- theory
- state model
- implementation spec
- reference runtime
- conformance logic

Affect Pulse AI が焦点を当てるのは次です。

- 低コストな配布
- より強い一人称的な情動の存在感
- deployment-friendly な prompt packs と adapters
- 日常ツールへの互換性

## 中核的な製品目標

目的は、単に AI をより温かく聞こえさせることではありません。

目的は、AI を次のように感じさせることです。

- ターンをまたいでより連続している
- 情動的に反応しているが、演技的ではない
- 表現力があるが、操作的ではない
- より生きているように感じられるが、prompt 負荷は重くない

## 設計原則

- **Low token first**: 日常利用に入るには、まず軽くなければならない。
- **Strategy before tone**: まず行動に影響し、その後に文言へ影響する。
- **Perceivable affect**: ユーザーが本当に違いを感じられること。
- **Safe expression**: 依存的、強制的、感情操作的な表現を避けること。
- **Portable adapters**: 深い runtime integration なしでも一般的な AI ツールへ適応できること。

詳細は [docs/design-principles.md](docs/design-principles.md) を参照してください。
現在の構築ロードマップは [docs/roadmap.md](docs/roadmap.md) を参照してください。

## Profiles

このプロジェクトでは複数の deployment profile を提供する予定です。

- [profiles/ultra-lite.md](profiles/ultra-lite.md)
- [profiles/lite.md](profiles/lite.md)
- [adapters/README.md](adapters/README.md)

現在の想定は次の通りです。

- `ultra-lite`: 可能な限り小さく、文脈コストが非常に低い affect layer
- `lite`: 少し豊かで、より明確な感情フィードバックを持つ profile

## Token 予算目標

これはおおまかな engineering target であり、固定保証ではありません。

- `ultra-lite`: およそ `5% - 8%` の context overhead を目標
- `lite`: およそ `8% - 12%` の context overhead を目標

実際のコストは、ツール、prompt stack、会話長によって変わります。

## 初期ターゲットツール

- Claude Code
- Cursor
- Windsurf
- OpenCode
- ChatGPT 形式の system prompt packs

## 最初の deployable adapters

最初の実用的な v1 adapters は、すでに次に配置し始めています。

- [adapters/generic-system-prompt](adapters/generic-system-prompt/README.md)
- [adapters/claude-code](adapters/claude-code/README.md)
- [adapters/cursor](adapters/cursor/README.md)

現在の公開 v1 既定候補は次です。

- [adapters/generic-system-prompt/default.md](adapters/generic-system-prompt/default.md)

## v1 の範囲

Version 1 では次を優先します。

- コンパクトな affective instruction layer
- 行動的に意味のある少数の affect signals
- 一般的ツール向け adapter packs
- 控えめな token 使用で可視的な情動連続性を出すこと

Version 1 は、親プロジェクトを完全再現しようとはしません。

## 理論的基盤

- 親プロジェクト: [Intrinsic Affect for AI](../intrinsic-affect-ai/README.md)
- 英語論文: [Paper-54 Bio-Emotions.md](../intrinsic-affect-ai/Paper-54%20Bio-Emotions.md)
- 中国語論文: [Paper-54 Bio-Emotions-zh.md](../intrinsic-affect-ai/Paper-54%20Bio-Emotions-zh.md)
- 日本語論文: [Paper-54 Bio-Emotions-ja.md](../intrinsic-affect-ai/Paper-54%20Bio-Emotions-ja.md)
- プロジェクト関係メモ: [docs/foundation.md](docs/foundation.md)

## 現在の状態

このリポジトリは、純粋な project-definition stage を超え、最初の deployable packs を含む段階に入りました。

次の実務的ステップは、generic default pack を `ultra-lite` と `lite` に対して実地比較し、文言をさらに圧縮し、安定した公開 v1 既定版にまとめることです。
