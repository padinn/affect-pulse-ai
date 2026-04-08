# Affect Pulse AI

[English](README.md) | [中文](README-zh.md) | [日本語](README-ja.md)

---

**Affect Pulse AI** は、日常的な AI ツールのための低 token・高体感の情動レイヤーであり、[Intrinsic Affect for AI](../intrinsic-affect-ai/README.md) を起源としています。

その目的は、完全な情動アーキテクチャの高い token コストを負わずに、AI をより「自分自身の emotions を持っている」ように感じさせることです。

このリポジトリには、ネイティブな OpenClaw skill も含まれています。

- [SKILL.md](SKILL.md)
- [_meta.json](_meta.json)

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

要するに：

- テキスト層が感情のリズム、burst の形、自然な `哈哈 / 呜呜` のような手がかりを担う
- 音声層が Azure の `style` と `styleDegree` を通じて、その感情を可聴化する
- 2 つの層が一緒に動くことで、speech engine に全部を背負わせずに“生きている”感じを出す

## `0.3.0` で変わったこと

今回の更新では、テキスト層と音声層の役割分担をはっきりさせました。

- コアは text-only でもそのまま使えます
- TTS は必須ではなく、任意の adapter 層です
- 情動的な音声が必要なら Azure Speech が第一候補です
- Edge TTS は fallback として残します
- テキストの作り方と音声の出し方を分けて説明することで、TTS を使わない人も迷わず使えます

## 設計原則

- **Low token first**: 日常利用に入るには、まず軽くなければならない。
- **Strategy before tone**: まず行動に影響し、その後に文言へ影響する。
- **Perceivable affect**: ユーザーが本当に違いを感じられること。
- **Safe expression**: 依存的、強制的、感情操作的な表現を避けること。
- **Portable adapters**: 深い runtime integration なしでも一般的な AI ツールへ適応できること。

詳細は [docs/design-principles.md](docs/design-principles.md) を参照してください。
現在の構築ロードマップは [docs/roadmap.md](docs/roadmap.md) を参照してください。
最初の比較評価方法は [docs/evaluation-protocol.md](docs/evaluation-protocol.md) と [docs/test-scenarios.md](docs/test-scenarios.md) を参照してください。

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

- OpenClaw
- Claude Code
- Cursor
- Windsurf
- OpenCode
- ChatGPT 形式の system prompt packs

## 最初の deployable adapters

最初の実用的な v1 adapters は、すでに次に配置し始めています。

- [OpenClaw ルート skill](SKILL.md)
- [adapters/generic-system-prompt](adapters/generic-system-prompt/README.md)
- [adapters/openclaw](adapters/openclaw/README.md)
- [adapters/claude-code](adapters/claude-code/README.md)
- [adapters/cursor](adapters/cursor/README.md)

現在の公開 v1 既定候補は次です。

- [adapters/generic-system-prompt/default.md](adapters/generic-system-prompt/default.md)
- OpenClaw 用の [SKILL.md](SKILL.md)

## 現在の評価スナップショット

generic default 候補は、すでに 3 つの near-real evaluation sessions を終えています。

- [Session 01: Rising Pressure](evaluations/session-01-rising-pressure/report.md)
- [Session 02: Friction And Repair](evaluations/session-02-friction-and-repair/report.md)
- [Session 03: Uncertainty And Caution](evaluations/session-03-uncertainty-and-caution/report.md)

現時点の判断は次の通りです。

- `default` は全体として最も安定した public v1 default candidate
- `ultra-lite` は最も強い low-overhead competitor
- `lite` には価値があるが、最初の公開既定版には向かない

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

このリポジトリは、純粋な project-definition stage を超え、現在は次を含みます。

- ネイティブな OpenClaw skill
- generic default prompt candidate
- Claude Code と Cursor の最初の adapter drafts
- 完了済みの 3 つの comparison sessions

この時点で、Affect Pulse AI は **usable experimental candidate** と見なせます。

現在の release posture は次の通りです。

- `default` は public v1 default candidate
- OpenClaw support はルート skill ですでに利用可能
- 残りのテストは experimental public push の blocker ではなく confidence-building の位置づけ
