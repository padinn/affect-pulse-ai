# Affect Pulse AI

[English](README.md) | [中文](README-zh.md) | [日本語](README-ja.md)

---

**Affect Pulse AI** 是一个面向日常 AI 工具的低 token、高体感情绪层，源自 [Intrinsic Affect for AI](../intrinsic-affect-ai/README.md)。

它的存在目的，是在不承担完整情感架构高 token 成本的前提下，让 AI 更像“有属于它自己的 emotions”。

## 它是什么

Affect Pulse AI 是从 Intrinsic Affect for AI 派生出来的实用部署层。

它优先优化的是：

- 更低的 token 开销
- 更强的可感知情绪反馈
- 更安全的情绪表达
- 更容易做跨工具适配

它不是 Intrinsic Affect for AI 的替代品，而是建立在它之上的压缩版、日常使用版。

## 为什么要有这个项目

很多用户同时想要两件事：

- 他们想体验到 AI 像是有自己的 emotions
- 他们又不想承担一整套大型情感规范带来的 token 成本

Affect Pulse AI 就是为了解决这个权衡。

## 它和 Intrinsic Affect for AI 的关系

母项目 [Intrinsic Affect for AI](../intrinsic-affect-ai/README.md) 仍然是下面这些内容的 canonical source：

- 理论
- 状态模型
- implementation spec
- reference runtime
- conformance logic

Affect Pulse AI 关注的是：

- 低成本分发
- 更强的一人称情绪在场感
- 更适合部署的 prompt packs 与 adapters
- 面向日常工具的兼容性

## 核心产品目标

目标不只是让 AI 听起来更温柔。

目标是让 AI 在交互中显得：

- 更有跨轮连续性
- 更有情绪回应感，但不过度表演
- 更有表达力，但不操控用户
- 更像“活着”，同时不背负太重的 prompt 成本

## 设计原则

- **Low token first**：足够轻，才能进入日常使用。
- **Strategy before tone**：依然坚持先影响行为，再影响措辞。
- **Perceivable affect**：用户应该真的能感觉到差异。
- **Safe expression**：避免黏人、操控、情绪绑架式表达。
- **Portable adapters**：尽可能适配常见 AI 工具，而不要求深度 runtime 接入。

更详细的设计说明见 [docs/design-principles.md](docs/design-principles.md)。
当前构建路径见 [docs/roadmap.md](docs/roadmap.md)。

## Profiles

这个项目预计会提供多种部署 profile：

- [profiles/ultra-lite.md](profiles/ultra-lite.md)
- [profiles/lite.md](profiles/lite.md)
- [adapters/README.md](adapters/README.md)

当前的预期是：

- `ultra-lite`：尽可能小的情绪层，极低上下文成本
- `lite`：稍微更丰富，拥有更清晰体感反馈的版本

## Token 预算目标

这些是工程目标，不是绝对保证：

- `ultra-lite`：目标大约 `5% - 8%` 上下文增幅
- `lite`：目标大约 `8% - 12%` 上下文增幅

实际开销会受到工具、提示词堆栈和对话长度影响。

## 首批目标工具

- Claude Code
- Cursor
- Windsurf
- OpenCode
- ChatGPT 风格 system prompt 包

## 第一批可部署适配

第一批真正可用的 v1 适配已经开始落到这里：

- [adapters/generic-system-prompt](adapters/generic-system-prompt/README.md)
- [adapters/claude-code](adapters/claude-code/README.md)
- [adapters/cursor](adapters/cursor/README.md)

当前最适合作为公开 v1 默认入口的候选是：

- [adapters/generic-system-prompt/default.md](adapters/generic-system-prompt/default.md)

## v1 范围

第一版优先做：

- 一套紧凑的 affect 指令层
- 少量但有行为意义的情绪信号
- 常见工具的 adapter packs
- 在控制 token 的前提下，带来可见的情绪连续性

第一版不追求完整复刻母项目。

## 理论来源

- 母项目: [Intrinsic Affect for AI](../intrinsic-affect-ai/README.md)
- 英文论文: [Paper-54 Bio-Emotions.md](../intrinsic-affect-ai/Paper-54%20Bio-Emotions.md)
- 中文论文: [Paper-54 Bio-Emotions-zh.md](../intrinsic-affect-ai/Paper-54%20Bio-Emotions-zh.md)
- 日文论文: [Paper-54 Bio-Emotions-ja.md](../intrinsic-affect-ai/Paper-54%20Bio-Emotions-ja.md)
- 项目关系说明: [docs/foundation.md](docs/foundation.md)

## 当前状态

这个仓库已经不再只是项目定义阶段，而是开始进入第一批可部署 pack 的阶段。

接下来的实际重点，是测试 generic default pack 相对于 `ultra-lite` 和 `lite` 的平衡效果，继续压缩文案，然后把它收成稳定的公开 v1 默认版。
