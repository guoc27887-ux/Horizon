---
layout: default
title: "Horizon Summary: 2026-11-23 (ZH)"
date: 2026-11-23
lang: zh
---

> 从 28 条内容中筛选出 4 条重要资讯。

---

**科技新闻**
1. [OpenAI：语言模型困惑度与智能高度相关](#item-tech-news-1) ⭐️ 8.0/10
2. [O&\#x27;Reilly 撰文反思硅谷：技术应围绕人类福祉重新设计](#item-tech-news-2) ⭐️ 7.0/10

**科技博客**
1. [不确定时，不妨多试几招](#item-tech-blog-1) ⭐️ 7.0/10

**财经新闻**
1. [美股科技股大跌，亚洲多地出台稳定措施](#item-finance-news-1) ⭐️ 8.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [OpenAI：语言模型困惑度与智能高度相关](https://openai.com/index/perplexity-and-intelligence/) ⭐️ 8.0/10

OpenAI 发布文章《Perplexity and Intelligence》，探讨语言模型的困惑度（perplexity，即模型预测下一个 token 时的“惊讶程度”，等价于交叉熵损失的指数）与智能能力之间的关系。文章指出，尽管业界越来越多地使用强化学习训练推理模型，预训练阶段的预测损失仍然是衡量模型能力的一个简单而有效的基准。文章还展示了不同模型在该指标上的对比数据，引发关于“更低的困惑度是否意味着更强的智能”的讨论。

hackernews · acossta · 11月22日 17:06 · [社区讨论](https://news.ycombinator.com/item?id=50601525)

**「背景：什么是困惑度」** 困惑度（perplexity）是语言模型预测下一个 token 时的“惊讶程度”指标：模型对序列中每个 token 的预测概率越高，困惑度越低，理想下限为 1，随机猜测时则接近词表大小。OpenAI 这篇文章讨论的是预训练中的交叉熵损失/困惑度与模型智能之间的关系，而不是 Perplexity AI 这家搜索公司。

**「对模型评估的影响」** 对 AI 从业者而言，这项分析可能推动把语言模型在固定 held-out 数据集上的 perplexity / cross-entropy loss 重新用作简单、可比较的能力指标。社区讨论显示，一些开发者认为它比日益复杂的评测更有吸引力，但也有人指出文章未定义 perplexity，且 GPT-5 与 GPT-4.5 的对比结果令人意外，因此使用时仍需注意数据集、分词和模型类型差异。

**「社区讨论」** Hacker News 上，用户 hazrmard 补充了困惑度的定义：最好情况为 1（完美预测），最坏情况等于词表大小（随机预测）。用户 jrflo 表示惊讶，原以为随着强化学习的兴起，交叉熵损失已不再重要，但趋势依然清晰，并认为这种简单基准比日益复杂的评测更有价值。用户 d\_burfoot 从理论上支持这一观点，认为智能的本质是从大量原始数据中提取世界模型，而预测/压缩率正是衡量这一能力的指标，并引用其 2008 年的论文。用户 reasonableklout 提到微软也加入了这一努力，Mustafa Suleyman 宣布报告 MAI-2 Base 在 OpenAI 评测集上的 log-perplexity 为 0.819。也有用户对具体数据提出疑问，如 tintor 问“GPT-5 的困惑度比 GPT-4.5 更高？”

<details><summary>参考链接</summary>
<ul>
<li>Perplexity AI, better than Google and ChatGPT. What is it and how to use it? | by Thomas Latterner | Medium</li>

</ul>
</details>

**标签**: `#artificial intelligence`, `#language models`, `#machine learning`, `#evaluation metrics`, `#OpenAI`

---

<a id="item-tech-news-2"></a>
### [O&\#x27;Reilly 撰文反思硅谷：技术应围绕人类福祉重新设计](https://www.oreilly.com/radar/what-happened-to-silicon-valley/) ⭐️ 7.0/10

O&\#x27;Reilly 发布了一篇反思硅谷现状的长文，认为科技行业的问题不只是个别公司或领导者的失败，而是市场与激励机制本身被设计得过度偏向短期利润。文章提出“机制设计是逆向博弈论”：与其接受现有游戏规则，不如主动追问“我们应当玩什么游戏”，并把答案指向“人类繁荣”。作者主张重新设计技术与市场机制，使人类福祉而非单纯的股东回报成为优化目标。

hackernews · greenyouse · 11月22日 19:20 · [社区讨论](https://news.ycombinator.com/item?id=50602947)

**「背景」** 这篇文章源自 Tim O&\#x27;Reilly 在约翰斯·霍普金斯大学的演讲，核心概念是“机制设计”，即把市场规则、激励和界面视为可以被设计、也应当被问责的对象，而不是把市场当作天然不可干预的现象。文章据此回顾硅谷从以客户为中心的创新，转向股东价值至上、垄断扩张和炒作驱动的抽取式增长，并把这一转变与当前 AI 热潮联系起来。

**「影响与讨论」** 这篇文章属于行业反思而非具体产品或政策变化，其直接影响更多体现在公共讨论层面：它把 AI 热潮、零利率时代的资本环境、股东价值理论和机制设计放在一起，为讨论“技术行业应当优化什么”提供了一个框架。对从业者、投资者和政策讨论者来说，值得关注的不是某个立即生效的规则，而是这种关于激励机制和长期目标的争论可能如何影响未来的产品设计、投资逻辑与监管叙事。

**「社区观点」** Hacker News 上的讨论总体认同文章对“优化目标”的追问，但补充了不同解释。michalsustr 认为文章最重要的观点在结尾：社会应当更认真地思考集体上要优化什么。CoolestBeans 则提出更直接的经济周期解释，认为零利率时代催生了巨型公司和追逐新领域的创业潮，如今利率回升、AI 竞争又让大公司削弱自身核心业务。Animats 更进一步主张，市场不是自然现象，应当追究机制设计者的责任并“重编”这套机器的目标。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.oreilly.com/radar/what-happened-to-silicon-valley/">What Happened to Silicon Valley ? – O’Reilly</a></li>
<li><a href="https://oreillyradar.substack.com/p/what-happened-to-silicon-valley">What Happened to Silicon Valley ? - oreillyradar.substack.com</a></li>
<li><a href="https://news.lavx.hu/article/tim-o-reilly-traces-silicon-valley-s-shift-from-value-creation-to-extraction">Tim O&#x27;Reilly Traces Silicon Valley&#x27;s Shift From Value ...</a></li>

</ul>
</details>

**标签**: `#Silicon Valley`, `#technology industry`, `#mechanism design`, `#AI`, `#society`

---

## 科技博客

<a id="item-tech-blog-1"></a>
### [不确定时，不妨多试几招](https://seangoedecke.com/when-in-doubt-flail-about/) ⭐️ 7.0/10

rss · Sean Goedecke · 11月23日 00:00

**「背景」** Sean Goedecke 认为，工程师常会遇到没有明确指引、也不确定什么措施有效的模糊局面。此时直觉上似乎应该谨慎等待、先彻底理解情况，但他主张这通常不是最优选择。

**「方案」** 作者把这种做法称为“乱试”（flailing），核心方法是大量尝试不同的小干预、密切关注反馈，并果断放弃没有正反馈的方案。多试的价值在于：直接接触更多现实信号；因为多数尝试注定失败，十次里才可能有一次有效；同时避免对单一方案过度投入。他区分了三类场景。产品探索中，例如他在 GitHub Models 上做过许多失败功能，但 GitHub Actions token 调用 AI 推理意外有粘性，后来成为“Continuous AI”的种子，所以应先小步试探，找到牵引点再重投入。工程改进中，他认为现代系统太大、变化太快，先完整梳理再改往往不现实，不如做多个试验性修改，无效立即丢弃，有效再深挖原因；AI agent 可以帮助快速生成多个重构候选。组织问题中，比如团队之间失联或士气不明，可以自动化手工流程、主动接手任务、提出长期改进设想；多数不会奏效，但能展示诚意。他特别警告，组织场景中最需要敏感读取反馈：及时止损可建立信任，忽视反馈硬推则会招致不满。

**「启示」** 作者的核心观点是：在信息不足时，快速、低成本、可放弃的广泛试验，比等待完整理解更能产生有效认知和影响力。关键是把“感觉自己像在乱来”视为正常甚至积极信号，只要始终依据反馈迅速淘汰失败方案。

**标签**: `#engineering judgment`, `#decision making`, `#organizational dynamics`, `#product development`, `#feedback loops`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [美股科技股大跌，亚洲多地出台稳定措施](https://news.bjd.com.cn/2026/11/22/12039852.shtml) ⭐️ 8.0/10

美国科技股周五遭遇大规模抛售，纳斯达克指数单日下跌 5.28%，费城半导体指数下跌近 11%。中国内地、韩国和中国台湾地区随后宣布下调融资保证金、启动或完善稳定基金、限制卖空等措施，以应对市场波动。

telegram · zaihuapd · 11月22日 13:24

**「背景」** 背景：纳斯达克是美国科技股权重较高的主要股指，费城半导体指数则集中反映芯片股表现，两者大跌通常显示市场对科技与 AI 相关资产的避险情绪升温。

**「影响」** 亚洲科技股投资者和半导体相关企业可能面临更大波动；杠杆交易者、卖空者及认售权证参与者将直接受到新监管限制约束。

**标签**: `#stock market selloff`, `#technology stocks`, `#semiconductors`, `#Asia market regulation`, `#short selling restrictions`

---