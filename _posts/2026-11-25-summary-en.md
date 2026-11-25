---
layout: default
title: "Horizon Summary: 2026-11-25 (EN)"
date: 2026-11-25
lang: en
---

> From 27 items, 3 important content pieces were selected

---

**Technology News**
1. [PrismML ships Ternary Bonsai 2.5 27B ternary-weight model for local inference](#item-tech-news-1) ⭐️ 8.0/10
2. [Simon Willison&\#x27;s three LLM inflection points: Opus 4.5, Fable-class models, AI game design](#item-tech-news-2) ⭐️ 8.0/10

**Financial News**
1. [Fed&\#x27;s Williams signals more rate hikes likely over time to tame inflation](#item-finance-news-1) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [PrismML ships Ternary Bonsai 2.5 27B ternary-weight model for local inference](https://prismml.com/news/bonsai-2-5-27b) ⭐️ 8.0/10

PrismML has released Ternary Bonsai 2.5 27B, a 27B ternary-weight model aimed at efficient local inference and agentic coding, with a Q2 GGUF build referenced by early users. In user-reported llama.cpp-style benchmarks on a Mac Mini M5 Pro with 24GB RAM, it generates about 22-25 tokens per second and holds up to 128k tokens of context in memory. These figures and a community claim of SWE-bench Verified parity with a frontier model are unverified user reports, not independently measured results; the release itself is the confirmed event.

hackernews · b0m · Nov 24, 20:08 · [Discussion](https://news.ycombinator.com/item?id=50633922)

**「Background」** Ternary-weight models are language models whose parameters are restricted to three values \(typically -1, 0, and +1\) instead of full-precision numbers, a format that sharply reduces memory footprint and makes large models practical to run locally on consumer hardware. Ternary Bonsai 2.5 27B is PrismML&\#x27;s new 27B-parameter model in this line, shipped as GGUF weights with a hybrid attention design of roughly 75% linear and 25% full attention and a 262K-token context length. It runs through llama.cpp on NVIDIA and Intel GPUs and through MLX on Apple devices such as Mac, iPhone, and iPad, though independent benchmark results have not yet been published.

**「Why it matters」** If the reported numbers hold, developers could run a 27B-class model with 128k context on consumer hardware such as a 24GB Mac Mini at roughly 22 tokens per second, making local long-context agentic coding or batch coding tasks practical without datacenter GPUs. Before adopting it, teams should verify the benchmark claims independently and compare it against quantized small-model alternatives, as commenters requested.

**「Community reaction」** Commenter nik\_s flagged that the claimed SWE-bench Verified parity could reflect benchmark optimization, a shifting benchmark, or genuine small-model progress, and hatthew asked for direct comparisons against quantized 1B-10B models. In a self-described long-horizon local-agent benchmark, user thepoet reported Bonsai 2.5 passed 5 of 8 tasks versus 5 of 8 for Bonsai 2, but with 17% fewer steps and 29% less wall-clock time; these are individual user reports rather than established results.

<details><summary>References</summary>
<ul>
<li><a href="https://prismml.com/news/bonsai-2-5-27b">PrismML — Introducing Ternary Bonsai 2 . 5 27 B : Powering Agentic...</a></li>
<li><a href="https://huggingface.co/prism-ml/Ternary-Bonsai-2.5-27B-GGUF">prism - ml / Ternary - Bonsai - 2 . 5 - 27 B -GGUF · Hugging Face</a></li>
<li><a href="https://benchlm.ai/models/ternary-bonsai-27b">Ternary Bonsai 27 B Context , Specs &amp; Sources (November 2026)</a></li>

</ul>
</details>

**Tags**: `#machine-learning`, `#local-llm`, `#quantization`, `#agentic-coding`, `#model-release`

---

<a id="item-tech-news-2"></a>
### [Simon Willison&\#x27;s three LLM inflection points: Opus 4.5, Fable-class models, AI game design](https://simonwillison.net/2026/Nov/24/llm-inflection-points/) ⭐️ 8.0/10

In a November 24, 2026 keynote write-up from the AI Engineer Code Summit, Simon Willison argues that the past twelve months brought three inflection points in LLM and coding-agent capability. The first was Claude Opus 4.5, released November 24, 2025: Anthropic claimed it could handle ambiguity and untangle complex multi-system bugs without hand-holding, and Willison reports the claim held up — together with OpenAI&\#x27;s same-month GPT-5.1 releases \(including GPT-5.1-Codex and GPT-5.1-Codex-Max\), coding agents like Claude Code and Codex became reliably useful daily tools for him. The second was the June 2026 arrival of Claude Fable 5, the first of what he calls &quot;Fable class&quot; models — ones that can solve a defined goal with brute force when given the necessary tools — a capability he demonstrated by having models triangulate a mysterious beep to within about 40 cm using five WebAudio microphones; Fable 5 was briefly blocked by US export controls before returning July 1. The third, emerging around September 2026, is frontier models&\#x27; sudden strength in 3D modeling and game design, led by Claude Opus 5.5 \(released September 22, 2026\), GPT-5.6 Sol, GPT-6 Astra, and the Gemini 4 family; Willison says Opus 5.5 was the first model he had used that &quot;appeared to understand fun,&quot; rebalancing his RTS game after 12 hours of autonomous playtesting.

rss · Simon Willison · Nov 24, 23:02

**「From Claude Code to Opus 4.5」** Claude Code, the Anthropic coding agent at the center of the first inflection point, was introduced alongside Claude 3.7 Sonnet on February 24, 2025. The release that changed its reliability, Claude Opus 4.5, shipped on November 24, 2025 — exactly one year before this post — and was billed by Anthropic as its new flagship model with state-of-the-art coding and agentic performance at lower pricing. The rest of the piece moves quickly through the year&\#x27;s subsequent releases, including Anthropic&\#x27;s Fable line and Opus 5.5, which Anthropic now positions as its strongest Opus model for long-running, highly capable agents, plus OpenAI&\#x27;s GPT-5.1 Codex models, GPT-6 Astra, and Google&\#x27;s Gemini 4 family.

**「What it means for developers」** For developers, Willison&\#x27;s practical claim is that goal-driven autonomy is becoming the baseline: he classes Claude Fable 5, 5.1, 5.2, Opus 5.5, GPT-6 Astra, and likely Gemini 4 Neon as models that can complete a task if you define the goal and provide tools, and says this is now his minimum expectation for a frontier model. In game development the shift is already contentious — he describes the indie scene as in a &quot;full-blown culture war&quot; over AI-assisted programming, with some calling GTA VI the last pre-generative-AI blockbuster.

<details><summary>References</summary>
<ul>
<li><a href="https://www.anthropic.com/news/claude-opus-4-5">Introducing Claude Opus 4.5 \ Anthropic</a></li>
<li><a href="https://www.anthropic.com/claude/opus">Claude Opus \ Anthropic</a></li>

</ul>
</details>

**Tags**: `#LLMs`, `#coding agents`, `#AI engineering`, `#software engineering`, `#Claude Opus 4.5`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Fed&\#x27;s Williams signals more rate hikes likely over time to tame inflation](https://www.cnbc.com/2026/11/23/john-williams-fed-inflation-rate-hikes.html) ⭐️ 7.0/10

New York Fed President John Williams said Monday that further interest-rate increases are likely over time to bring inflation back to the Fed&\#x27;s 2% goal, which he expects to approach in 2027 and reach in 2028. Markets fully expect a quarter-point hike at the Fed&\#x27;s Dec. 8-9 meeting, from the current 3.75%-4% target range.

rss · CNBC Finance · Nov 24, 13:33

**「Background」** Inflation is still running well above the Fed&\#x27;s 2% goal while the economy keeps growing, and Williams — an influential voter on the Fed&\#x27;s rate-setting committee — has favored a measured pace of rate increases rather than aggressive moves.

**Tags**: `#Federal Reserve`, `#monetary policy`, `#interest rates`, `#inflation`, `#FOMC`

---