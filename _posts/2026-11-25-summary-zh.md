---
layout: default
title: "Horizon Summary: 2026-11-25 (ZH)"
date: 2026-11-25
lang: zh
---

> 从 27 条内容中筛选出 3 条重要资讯。

---

**科技新闻**
1. [PrismML 发布三值权重模型 Ternary Bonsai 2.5 27B](#item-tech-news-1) ⭐️ 8.0/10
2. [Simon Willison：过去十二个月 LLM 的三个能力拐点](#item-tech-news-2) ⭐️ 8.0/10

**财经新闻**
1. [美联储威廉姆斯：为使通胀回到 2%，需“随时间采取行动”](#item-finance-news-1) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [PrismML 发布三值权重模型 Ternary Bonsai 2.5 27B](https://prismml.com/news/bonsai-2-5-27b) ⭐️ 8.0/10

PrismML 发布了 270 亿参数的三值权重（ternary-weight，权重被限制为三个离散取值）语言模型 Ternary Bonsai 2.5 27B，面向高效的本地推理场景。社区用户报告，以 Q2 GGUF 量化运行时，在配备 24GB 内存的 Mac Mini M5 Pro 上生成速度约 22–25 token/秒、首 token 延迟约 2.1 秒，并能轻松在内存中容纳 128k 上下文，因而被认为适合智能体编程（agentic coding）等长上下文任务。有评论称其在 SWE-bench Verified 上相当于 2026 年 2 月发布的 Opus 4.6，也有用户自建的长程任务基准显示 2.5 版较 2.0 版步数减少 17%、总耗时减少 29%；这些基准数据均来自社区、尚未经独立验证。

hackernews · b0m · 11月24日 20:08 · [社区讨论](https://news.ycombinator.com/item?id=50633922)

**「三元权重模型与本地推理」** 三元权重（ternary-weight）模型是一种极端量化路线：把参数限制为三个离散取值（通常为 -1、0、+1），相比常见的 16 位权重能显著降低内存占用与推理开销，因此适合在消费级硬件上做本地推理。PrismML 的 Ternary Bonsai 2.5 27B 采用混合注意力架构（约 75% 线性注意力、约 25% 全注意力），配合 SwiGLU MLP、RoPE 与 RMSNorm，上下文长度达 262K tokens，并以 GGUF 权重格式发布，可经 llama.cpp 运行于 NVIDIA 和 Intel GPU，也可经 MLX 运行于 Mac、iPhone、iPad 等 Apple 设备。高比例线性注意力带来的长上下文能力与较低的硬件门槛，是社区讨论将其用于 agentic coding（智能体编程）任务的技术前提。

**「影响」** 对本地部署用户而言，一个 27B 级模型能在 24GB 级内存的消费级 Mac 上以约 22–25 token/秒的速度处理 128k 长上下文，使批量智能体编程等任务在本地运行变得现实。想尝试的开发者需要使用 Q2 GGUF 量化版本，并应把目前流传的基准成绩当作待验证信息，最好与同规模模型的量化版本做直接对比后再决定是否采用。

**「社区讨论」** 评论区的分歧集中在性能解读：nik\_s 质疑其 SWE-bench Verified 成绩可能包含“刷榜”或基准本身变动的成分，并认为该基准代表性有限；hatthew 则希望看到与 1B–10B 级量化模型的直接对比。thepoet 的自建长程任务测试中，Bonsai 2.5 与 2.0 同为 8 项通过 5 项（作为对照，Opus 5.5 为 8 项全过），但 2.5 版步数从 358 降至 296、总耗时从 107 分钟降至 76 分钟。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://prismml.com/news/bonsai-2-5-27b">PrismML — Introducing Ternary Bonsai 2 . 5 27 B : Powering Agentic...</a></li>
<li><a href="https://huggingface.co/prism-ml/Ternary-Bonsai-2.5-27B-GGUF">prism - ml / Ternary - Bonsai - 2 . 5 - 27 B -GGUF · Hugging Face</a></li>

</ul>
</details>

**标签**: `#machine-learning`, `#local-llm`, `#quantization`, `#agentic-coding`, `#model-release`

---

<a id="item-tech-news-2"></a>
### [Simon Willison：过去十二个月 LLM 的三个能力拐点](https://simonwillison.net/2026/Nov/24/llm-inflection-points/) ⭐️ 8.0/10

Simon Willison 在 AI Engineer Code Summit 2026 演讲稿的整理文章中提出，过去十二个月 LLM 与编程智能体出现了三个重要拐点。其一是 2025 年 11 月 24 日发布的 Claude Opus 4.5：他称这是第一个让 Claude Code 默认输出“大体正确”的模型，同期 OpenAI 发布的 GPT-5.1 系列（Instant、Thinking、Codex、Codex-Max）也让 Codex 智能体变得可靠可用。其二是 2026 年 6-7 月的“Fable 级”模型：Claude Fable 5 源自因网络攻击能力过强而被 Anthropic 认为“太危险”不予发布的 Mythos，上线约三天后因美国出口管制被事实禁用，7 月 1 日恢复；这类模型在给定目标和工具后能以“暴力”方式解决问题。其三是 9-10 月前沿模型在 3D 建模与游戏开发上的跃升：9 月 22 日发布的 Claude Opus 5.5 被他视为第一个“理解好玩”的模型，花费 12 小时试玩新功能并重新平衡数值后，把他的 RTS 游戏从无聊改成“深度有趣”。

rss · Simon Willison · 11月24日 23:02

**「背景」** 这一叙事的前提是编码智能体在一年内的快速成熟。Anthropic 于 2025 年 2 月 24 日随 Claude 3.7 Sonnet 推出编码智能体工具 Claude Code，但早期模型可靠性不足，用户常需反复纠正其输出。2025 年 11 月 24 日发布的 Claude Opus 4.5 改变了这一局面：它是 Anthropic 的旗舰模型，以更低定价提供最先进的编码与智能体性能，也是 Willison 眼中首个让 Claude Code 默认结果普遍正确的模型；此后发布的 Opus 5.5 则被 Anthropic 定位为迄今最强、可支撑长时间运行智能体的 Opus 模型。

**「影响」** 对开发者而言，最直接的变化是编程智能体从“需要频繁纠错”变成可托付日常任务的工具，协作粒度也从写代码片段上升到“给定目标与工具后自主解题”——Willison 用 Fable 5.2 与 Opus 5.5 配合五个 WebAudio 麦克风，把房间里的神秘蜂鸣声定位到约 40 厘米范围内。同时，AI 辅助游戏开发的质量已足以引发独立游戏圈关于 AI 披露的公开争议（如 IGF 奖项相关讨论），相关团队可能需要提前准备 AI 使用披露口径。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.anthropic.com/news/claude-opus-4-5">Introducing Claude Opus 4.5 \ Anthropic</a></li>
<li><a href="https://www.anthropic.com/claude/opus">Claude Opus \ Anthropic</a></li>

</ul>
</details>

**标签**: `#LLMs`, `#coding agents`, `#AI engineering`, `#software engineering`, `#Claude Opus 4.5`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [美联储威廉姆斯：为使通胀回到 2%，需“随时间采取行动”](https://www.cnbc.com/2026/11/23/john-williams-fed-inflation-rate-hikes.html) ⭐️ 7.0/10

纽约联储主席约翰·威廉姆斯 11 月 23 日表示，让通胀“及时且持续地”回到美联储 2%的目标是“100%必要”的，决策者仍需随时间采取行动；他预计通胀将在 2027 年接近目标，并于 2028 年达成。他未明确评论 12 月 8-9 日的议息会议，但市场目前已完全定价该会议将加息 25 个基点（当前利率目标区间为 3.75%-4%）。

rss · CNBC Finance · 11月24日 13:33

**「背景」** 威廉姆斯是美联储利率决策机构联邦公开市场委员会（FOMC）的常任投票成员，其表态对市场利率预期影响较大；目前美国经济持续增长、通胀仍远高于 2%目标，美联储内部对加息节奏存在分歧，威廉姆斯主张渐进行事。

**「影响」** 若美联储如市场预期在 12 月加息，家庭和企业的房贷、消费信贷等借贷成本将进一步上升。

**标签**: `#Federal Reserve`, `#monetary policy`, `#interest rates`, `#inflation`, `#FOMC`

---