---
layout: default
title: "Horizon Summary: 2026-11-19 (ZH)"
date: 2026-11-19
lang: zh
---

> 从 44 条内容中筛选出 15 条重要资讯。

---

**科技新闻**
1. [Nginx 披露未认证 HTTP/2 远程代码执行漏洞](#item-tech-news-1) ⭐️ 9.0/10
2. [OpenAI 宣布将 AI 模型用于芯片设计](#item-tech-news-2) ⭐️ 8.0/10
3. [谷歌发布 Gemini 4 Neon：编程智能体登顶，主打快速端到端执行](#item-tech-news-3) ⭐️ 8.0/10
4. [微软 Ignite 2026 发布七款新 AI 模型](#item-tech-news-4) ⭐️ 8.0/10
5. [Google DeepMind 发布 Genie 4，面向部分订阅用户开放](#item-tech-news-5) ⭐️ 8.0/10
6. [调查联盟用 OpenAleph 分析德意志银行约 1500 万份文件](#item-tech-news-6) ⭐️ 7.0/10
7. [Quad9 因法国盗版 DNS 屏蔽令退出法国市场](#item-tech-news-7) ⭐️ 7.0/10
8. [RadixArk 发布开源权重模型 DaisyRose-27B，训练成本与评测偏向引发讨论](#item-tech-news-8) ⭐️ 7.0/10
9. [Energy-Based Reasoners 项目宣称推理效率提升 385 倍](#item-tech-news-9) ⭐️ 7.0/10
10. [交互式网站可拆解旅行者 1 号直至单颗内存芯片](#item-tech-news-10) ⭐️ 7.0/10
11. [curl 维护者：AI 生成的 Rust 重写难以跟上真实项目修复](#item-tech-news-11) ⭐️ 7.0/10

**财经新闻**
1. [美联储会议纪要：多数官员预计还需加息，并担忧 AI 推升通胀与金融风险](#item-finance-news-1) ⭐️ 8.0/10
2. [APEC 深圳峰会：特朗普、习近平与普京会晤三大看点](#item-finance-news-2) ⭐️ 7.0/10
3. [腾讯三季度营收增长 8%低于预期，AI 资本开支升至 814 亿元](#item-finance-news-3) ⭐️ 7.0/10
4. [中韩自贸协定服务投资后续谈判实质性结束](#item-finance-news-4) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [Nginx 披露未认证 HTTP/2 远程代码执行漏洞](https://www.wiz.io/blog/nginx-http2-rce-vulnerabilities) ⭐️ 9.0/10

安全研究方 Xint 披露了名为 NGINX2Root 的漏洞链，包含 5 个 Nginx 漏洞和 1 个 Linux 内核缺陷，串联后可从 Nginx 的未认证访客权限一路提升到主机 root。其中 CVE-2026-123007 是 HTTP/2 流控内存破坏漏洞，未认证攻击者即可在 Nginx worker 进程中执行命令。Nginx 1.30.7 和 1.31.9 已于 11 月 18 日发布，修复了共 10 个 CVE；Rapid7 已放出 PoC，目前暂无在野利用报告。无法升级的系统可通过关闭对外 HTTP/2 来缓解风险。

hackernews · speedping · 11月18日 15:19 · [社区讨论](https://news.ycombinator.com/item?id=50547374)

**「背景」** NGINX 的 HTTP/2 支持建立在流量控制窗口、流多路复用和二进制帧解析等机制之上，攻击面比 HTTP/1.x 更复杂。此次 CVE-2026-123007 正是 HTTP/2 流量控制处理中的整数下溢/堆缓冲区溢出：攻击者可通过特制请求使流控窗口超出允许范围，导致 worker 进程内存破坏，在特定条件下实现未认证远程代码执行或拒绝服务。该漏洞与另外几个 NGINX 漏洞及一个 Linux 内核缺陷串联，构成被披露的 NGINX2Root 攻击链，可从 NGINX 访客权限提升到主机 root。NGINX 1.30.7 与 1.31.9 已于 11 月 18 日修复相关 CVE，Rapid7 已公开 PoC，暂无在野利用报告；无法升级的部署可通过关闭对外 HTTP/2 来缓解。

**「影响与应对」** 运行受影响版本且对外启用 HTTP/2 的 Nginx 服务面临未认证远程代码执行风险，攻击链还可能进一步获得主机 root 权限。无法立即升级到 1.30.7 或 1.31.9 的管理员应关闭对外 HTTP/2：从 listen 指令中移除 http2 参数，并在 1.25 及以上版本设置 http2 off;。Qualys 与 Red Hat 已发布检测和缓解指引，Rapid7 已公开 PoC，但暂无在野利用报告。

**「社区讨论」** 有评论者 black3r 指出，开源仓库中的修复提交比公告早约一周，且提交信息中包含 &quot;Reported by Xint.io&quot;，理论上熟悉 Xint 的攻击者可能通过监控仓库提前发现可利用的修复。testtestmetest 则引用外部说法称利用需要大量 HTTP/2 流量和特定 CPU 指令支持，认为实际风险被夸大；这些属于社区观点，尚需独立验证。另有评论指出 HTTP/2 并非 Nginx 默认开启，约 12% 的网站服务器启用了它。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.rapid7.com/blog/post/ve-cve-2026-123007-critical-nginx-http-2-integer-underflow-leads-to-rce-fixed/">CVE-2026-123007: Critical NGINX HTTP/2 Integer Underflow ...</a></li>
<li><a href="https://access.redhat.com/security/cve/cve-2026-123007">CVE-2026-123007 - Red Hat Customer Portal</a></li>
<li><a href="https://www.sophos.com/en-us/security-advisories/sophos-sa-20261118-nginx2root">Advisory: NGINX Vulnerabilities - nginx2root (CVE-2026-123007 ...</a></li>
<li><a href="https://access.redhat.com/security/cve/cve-2026-123007">CVE-2026-123007 - Red Hat Customer Portal</a></li>
<li><a href="https://blog.qualys.com/product-tech/patch-management/2026/11/18/nginx2root-five-nginx-flaws-led-by-cve-2026-123007-how-to-find-mitigate-and-patch-now">NGINX2Root: Five nginx Flaws, Led by CVE-2026-123007. How to ...</a></li>

</ul>
</details>

**标签**: `#security`, `#nginx`, `#remote-code-execution`, `#http2`, `#vulnerability`

---

<a id="item-tech-news-2"></a>
### [OpenAI 宣布将 AI 模型用于芯片设计](https://openai.com/index/advancing-chip-design-with-our-models/) ⭐️ 8.0/10

OpenAI 于 2026 年 11 月 18 日宣布，正在把自家 AI 模型用于芯片设计，并提到一个名为 Jalapeño 的芯片项目。该公告属于公司层面的进展披露，尚未给出可验证的芯片规格、性能数据、量产时间表或设计是否开源等关键细节。对芯片、AI 和硬件工程领域来说，这表明 OpenAI 正从模型研发扩展到芯片设计能力建设，但实际技术影响仍需等待后续具体成果。

hackernews · vighneshiyer · 11月18日 17:45 · [社区讨论](https://news.ycombinator.com/item?id=50549493)

**「背景」** OpenAI 的芯片设计工作此前已有公开进展：2026 年 6 月，《纽约时报》报道 OpenAI 与 Broadcom 合作推出定制 AI 芯片 Jalapeño，自研芯片可降低对 Nvidia 和 AMD 的依赖，并在与这些公司谈判时增加筹码。2026 年 8 月，Tom&\#x27;s Hardware 报道 OpenAI 在 Hot Chips 上披露 Jalapeño 推理 ASIC，称其大量借助 AI、设计周期非常短。此次公告是在这一背景下，进一步说明 OpenAI 模型正被用于改进为 AI 供电的芯片，包括从规格设计 RISC-V 核心、优化 RISC-V 核心、改进 Jalapeño 的计算模块，以及与 AMD 的合作。

**「对芯片设计流程与生态的影响」** 对芯片设计团队而言，OpenAI 模型已从辅助分析走向参与实际设计环节：Jalapeño 硅片中的电路经过其模型优化，RISC-V 核心设计也得到改进，并与 Broadcom 的软硬件协同开发、Synopsys 的 GPT-Synopsys EDA 工具链形成配合。这意味着团队可能需要评估在 RTL/电路优化、仿真与验证流程中引入此类 AI 工具，同时关注供应商锁定与设计资产归属问题——社区已质疑这些 RISC-V 设计是否会公开共享，采用前应确认授权与开放程度。

**「社区讨论」** Hacker News 上，用户 zardo 质疑 OpenAI 是否会公开这些 RISC-V 设计，jacquesm 则认为 AI 公司正在凭借模型能力进入多个行业，并可能与自身客户形成竞争。也有从业者分享了不同看法：skyberrys 表示自己把芯片设计当作软件工程问题，用智能体生成电路、自动化 EDA 流程并看护长时间仿真，但主要工作并不直接围绕 RTL 展开。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://openai.com/index/advancing-chip-design-with-our-models/">Advancing chip design with OpenAI models | OpenAI</a></li>
<li><a href="https://www.tomshardware.com/tech-industry/artificial-intelligence/openai-jalapeno-design-interview-transcript-hardware-vp-richard-ho-explains-how-ai-assisted-design-may-shape-the-future-of-inference-asics">OpenAI Jalapeño design interview transcript... | Tom&#x27;s Hardware</a></li>
<li><a href="https://www.nytimes.com/2026/06/24/technology/openai-broadcom-chip-jalapeno.html">OpenAI and Broadcom Unveil Custom A.I. Chip Design</a></li>
<li><a href="https://openai.com/index/advancing-chip-design-with-our-models/">Advancing chip design with OpenAI models</a></li>
<li><a href="https://www.broadcom.com/company/news/product-releases/64506">OpenAI and Broadcom Unveil LLM-Optimized Intelligence Processor</a></li>
<li><a href="https://news.synopsys.com/2026-09-30-OpenAI-and-Synopsys-Announce-GPT-Synopsys-Frontier-Intelligence-to-Revolutionize-Chip-Design">OpenAI and Synopsys Announce GPT-Synopsys: Frontier ...</a></li>

</ul>
</details>

**标签**: `#AI`, `#chip design`, `#hardware`, `#OpenAI`, `#RISC-V`

---

<a id="item-tech-news-3"></a>
### [谷歌发布 Gemini 4 Neon：编程智能体登顶，主打快速端到端执行](https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-neon/) ⭐️ 8.0/10

谷歌发布 Gemini 4 Neon 模型，定位为复杂软件工程、知识工作与科研工作流的快速端到端执行，已向开发者、企业及 Google AI Pro/Ultra 订阅用户开放。定价为每百万输入 token 3 美元（缓存输入 0.15 美元）、输出 15 美元，支持 100 万 token 上下文。基准方面，Gemini 4 Neon 在 Artificial Analysis 编程智能体指数以 58.6 分登顶第一，智能指数 xhigh 档以 61 分位列总榜第三，Terminal-Bench 4.1 得分 65.2%，且默认 high 档单任务成本较 Carbon 降低 32%。

hackernews · yigitdemirag · 11月18日 21:34 · [社区讨论](https://news.ycombinator.com/item?id=50552424)

**「背景」** Gemini 4 Neon 是 Google Gemini 系列中的新模型，定位为面向复杂软件工程、知识工作与科研工作流的前沿模型，并已向开发者、企业及 Google AI Pro/Ultra 订阅用户开放。要理解这次发布，需要把它放在 Gemini 现有产品线中比较：Google 仍将 Carbon 定位为“长时程”模型，而 Neon 虽然在 Artificial Analysis 智能指数等综合榜单上更高，却在 CritPt 这类研究级推理评测中低于 Carbon，说明两者是按任务场景分工，而不是简单的新旧替代关系。

**「影响」** 对于开发者和企业用户，Gemini 4 Neon 提供了一个在编程智能体任务上表现突出的新选择：Google 官方称其在 Artificial Analysis Coding Agent Index 以 58.6 分排名第一，Terminal-Bench 4.1 得分 65.2%，FrontierCode 2.0 默认 high 档得分 46.2%。它已通过 Gemini API、Google AI Studio 及企业平台提供，并附带迁移指南，适合需要快速端到端执行复杂软件工程、知识工作和科研工作流的团队评估或接入。同时，社区反馈显示 Google 的模型命名体系（如 Neon、Carbon 等）让用户难以判断各模型的定位和适用场景，选型时需要结合具体评测和实际任务验证，而不能只看名称或单一榜单。

**「社区讨论」** Hacker News 讨论集中在其产品定位与命名体系：stillpointlab 表示对 AI 模型命名频繁更迭感到疲劳，认为用户难以将 Neon、Carbon、Opus 等名称映射到具体使用场景。declanjackson 指出 Neon 虽整体智能评分高于 Carbon，但 Carbon 仍被定位为“长时程”模型，在 CritPt 等科研级推理评测中得分更低，反映前沿能力正变得“参差不齐”。seizethecheese 观察到 Neon 在 OpenRouter 上推理速度达 127 tokens/秒，远高于 Carbon 的 46 tokens/秒，并对其作为旗舰模型却速度更快表示疑惑。impulser\_ 则认为最新 Gemini 模型在整体通用智能体验上仍不及 Anthropic 的 Opus 5.5。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://artificialanalysis.ai/models/gemini-4-neon">Gemini 4 Neon Models - Intelligence, Performance &amp; Price Comparison</a></li>
<li><a href="https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-neon/">Introducing Gemini 4 Neon</a></li>
<li><a href="https://deepmind.google/blog/introducing-gemini-4-neon/">Introducing Gemini 4 Neon - deepmind.google</a></li>
<li><a href="https://docs.cloud.google.com/gemini-enterprise-agent-platform/models/guides/gemini-4-neon">Developer&#x27;s guide to Gemini 4 Neon | Gemini Enterprise Agent ...</a></li>
<li><a href="https://aistudio.google.com/docs/models/gemini-4-neon">Gemini 4 Neon - Gemini API | Google AI Studio</a></li>

</ul>
</details>

**标签**: `#AI`, `#Google`, `#Gemini`, `#LLMs`, `#model releases`

---

<a id="item-tech-news-4"></a>
### [微软 Ignite 2026 发布七款新 AI 模型](https://microsoft.ai/news/microsoft-ignite-2026/) ⭐️ 8.0/10

微软在 Ignite 2026 上宣布推出七款新 AI 模型，定位为在可扩展的价格与性能之间取得平衡。其中 MAI Code 2 是面向编程的模型，早期社区反馈称其在常见开发任务中表现良好，并被认为与 Anthropic Opus、OpenAI Sol 等领先模型处于同一水平。不过，这些比较主要来自发布会宣传和个别用户测试体验，尚未有独立基准测试证实其性能排名。

hackernews · gmays · 11月18日 16:08 · [社区讨论](https://news.ycombinator.com/item?id=50548021)

**「背景」** 微软在 Ignite 2026 上发布了一组七款新模型，其中 MAI Code 2 被定位为面向智能体编程的旗舰模型，MAI Cyber 2 Flash 则被定位为安全方向模型。微软称 MAI Code 2 可达到 GPT-6.1 Sol 约 98% 的编程质量，而价格约为其 40%；MAI Cyber 2 Flash 在 CyberGym-E2E 基准上以低于 2% 的单任务成本超过 GPT-6 Astra。

**「对开发者和企业的影响」** 对使用 AI 辅助编程的开发者和企业而言，MAI Code 2 与 MAI Code 2 Flash 的发布增加了一个以更低成本覆盖日常企业编码任务的选项；微软称其性能达到领先水平，但这一说法来自厂商宣传，尚需独立基准验证。已有开发者反馈称其在日常工作中表现良好，并认为可对标 Opus 或 Sol，不过这只是个人使用体验，不能等同于公开基准结论。若微软希望在企业市场获得实际份额，是否提供开源或开放权重版本、以及与现有开发工具链的兼容性，将是值得关注的关键因素。

**「社区讨论」** 有开发者表示实际测试 MAI Code 2 后认为它“相当不错”，认可微软从零开始做出有竞争力的编程模型；也有人认为微软若不开源部分模型，可能重蹈 Windows Phone 市场份额失败的覆辙。另有评论对 Ignite 主题演讲持批评态度，认为其缺乏创新、对一线 AI 工程实践吸引力不足。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://microsoft.ai/news/microsoft-ignite-2026/">Seven new world-class models at scalable price-performance ...</a></li>
<li><a href="https://windowsforum.com/news/microsoft-ignite-2026-mai-code-2-models-agent-365-governance-and-enterprise-ai-stack.453003/">Microsoft Ignite 2026: MAI Code 2 Models, Agent 365 ...</a></li>
<li><a href="https://www.zeebiz.com/technology/news-microsoft-mai-code-2-ai-models-openai-anthropic-405704">Microsoft unveils MAI Code 2 AI models with focus on coding ...</a></li>
<li><a href="https://benchlm.ai/compare/claude-opus-5-5-vs-gpt-6-2-sol">Claude Opus 5.5 vs GPT-6. 2 Sol : Benchmarks &amp; Cost</a></li>
<li><a href="https://microsoft.ai/news/introducing-mai-code-2-and-mai-code-2-flash/">MAI Code 2 and Code 2 Flash: Everyday coding at... | Microsoft AI</a></li>

</ul>
</details>

**标签**: `#Microsoft`, `#AI models`, `#coding assistants`, `#Ignite 2026`, `#LLMs`

---

<a id="item-tech-news-5"></a>
### [Google DeepMind 发布 Genie 4，面向部分订阅用户开放](https://blog.google/innovation-and-ai/models-and-research/google-deepmind/genie-4-now-available-project-genie/) ⭐️ 8.0/10

Google DeepMind 宣布 Genie 4 正式可用，这是一个 AI 世界模型，据称可生成可交互的模拟环境。根据官方博客，该模型目前面向部分“符合条件的 Google AI Ultra 订阅者”开放，而非全面公开。此次发布引发了关于访问资格、能力边界、伦理风险以及未来是否可用于游戏引擎等方向的讨论；目前公开材料中尚未提供详细技术基准或独立性能验证。

hackernews · leumon · 11月18日 18:49 · [社区讨论](https://news.ycombinator.com/item?id=50550415)

**「背景」** Genie 是 Google DeepMind 的 AI 世界模型系列，用于生成可交互的模拟环境。此前的 Genie 3 已向部分 Google AI Ultra 订阅者提供；根据 TechCrunch 报道，Genie 4 曾于 2026 年 10 月 27 日以研究预览形式发布，新增实时音频、更真实的世界生成和实时操控，并更紧密地集成 Gemini 来规划步骤和检查画面。

**「实际影响」** 对符合条件的 Google AI Ultra 订阅者来说，Genie 4 已从研究演示变成可实际使用的产品，可用于实时生成可交互、可语音引导修改的模拟世界。但访问条件仍不透明：有用户反映工作区账号无法开通 Ultra，个人 Gmail 页面又显示 Ultra 对应 Genie 3，且不清楚这是地区限制还是页面未更新，因此潜在用户需要先确认自己账号和所在地区能否获得访问权限。

**「社区讨论」** Hacker News 上的讨论集中在几个方面。有用户指出访问规则不够清晰：页面称 Genie 4 面向“符合条件的 Google AI Ultra 订阅者”，但其 Workspace 账号无法开通该订阅，而个人 Gmail 账号的 Ultra 页面仍显示包含 Genie 3，因此不确定是地区限制、账号类型限制还是页面未更新。也有用户认为讨论过度聚焦定价、盈利和能力，忽视了对这类技术的潜在负面后果的担忧；另有用户猜测这类世界模型未来可能演变为新型游戏引擎，但认为商业化和内容版权问题仍不确定。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://blog.google/innovation-and-ai/models-and-research/google-deepmind/genie-4-now-available-project-genie/">Project Genie update featuring Genie 4</a></li>
<li><a href="https://techcrunch.com/2026/10/27/googles-genie-4-world-model-adds-audio-more-realistic-worlds-and-real-time-steering/">Google ’s Genie 4 world model adds audio, more... | TechCrunch</a></li>
<li><a href="https://techcrunch.com/2026/10/27/googles-genie-4-world-model-adds-audio-more-realistic-worlds-and-real-time-steering/">Google’s Genie 4 world model adds audio, more... | TechCrunch</a></li>

</ul>
</details>

**标签**: `#AI`, `#Google DeepMind`, `#world models`, `#generative AI`, `#game engines`

---

<a id="item-tech-news-6"></a>
### [调查联盟用 OpenAleph 分析德意志银行约 1500 万份文件](https://www.inside-db.com/) ⭐️ 7.0/10

一个调查报道联盟发布了对德意志银行内部文件的大规模检视，项目页面为 inside-db.com。据参与记者在 Hacker News 上的说明，约 1500 万份文件（主要是 Outlook 邮箱导出）通过 OpenAleph 提供给联盟伙伴；该平台由 DARC 维护，基于 Elasticsearch，并使用为调查新闻场景设计的 FollowTheMoney 数据模式。报道方表示，记者将在未来几个月继续以新闻方式评估材料，但不会在网上公布原始数据。

hackernews · gyre007 · 11月18日 15:38 · [社区讨论](https://news.ycombinator.com/item?id=50547620)

**「背景」** “Inside Deutsche Bank”是由约 230 名记者和 50 家新闻机构参与的联合调查，基于超过 1500 万份与德意志银行活动相关的泄露文件，覆盖其 2010 年代初以来的业务活动。报道方称这是迄今针对一家银行规模最大的新闻调查，文件显示该行曾忽视洗钱和制裁违规的预警信号。为处理这批以 Outlook 邮箱导出为主的材料，项目使用 DARC 维护的 OpenAleph 平台，该平台基于 Elasticsearch 和面向调查新闻设计的 FollowTheMoney 数据模式。

**「影响」** 对从事数据工程、调查工具或新闻技术栈的团队来说，这个案例展示了 Elasticsearch 加上领域专用模式（FollowTheMoney）在超大规模非结构化文档检索与协作分析中的实际用法；OpenAleph 是可关注的开源工具。对读者而言，项目方明确不公开原始数据，意味着结论需依赖联盟后续发布的报道来核验。

**「社区讨论」** Hacker News 上，参与项目的记者 ltrg 介绍了 OpenAleph、Elasticsearch 和 FollowTheMoney 的技术栈；mlmonkey 则批评“不公布原始数据”可能让读者难以核查选择性叙述。另有评论认为首页缺少高层次摘要，读者需要点进多篇长文才能了解要点。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.lemonde.fr/en/les-decodeurs/article/2026/11/17/inside-deutsche-bank-an-investigation-by-230-journalists-and-50-news-orgs-into-15-million-files_6782703_8.html">&#x27;Inside Deutsche Bank&#x27;: An investigation by 230 journalists ...</a></li>
<li><a href="https://www.himalmag.com/inside-deutsche-bank-leak-investigation/">Inside Deutsche Bank: Leak of 15 million files from Deutsche ...</a></li>
<li><a href="https://www.linkedin.com/pulse/inside-deutsche-bank-making-15-million-files-searchable-nrflf">Inside Deutsche Bank: Making 15 million files ... - LinkedIn</a></li>

</ul>
</details>

**标签**: `#investigative journalism`, `#data engineering`, `#elasticsearch`, `#open source`, `#finance`

---

<a id="item-tech-news-7"></a>
### [Quad9 因法国盗版 DNS 屏蔽令退出法国市场](https://techstackups.com/articles/quad9-leaves-france-dns-blocking/) ⭐️ 7.0/10

公共 DNS 解析服务 Quad9 宣布退出法国，原因是法国法院要求 DNS 解析器在盗版执法中实施域名屏蔽。Quad9 与 Cloudflare 都就此事发布了说明，Cloudflare 的文章标题为“Quad9 withdrawal from France”。这一事件在 Hacker News 上引发大量讨论（621 分、234 条评论），焦点是 DNS 解析器是否适合作为版权执法的执行点，以及责任应归于法院还是立法者。

hackernews · ritzaco · 11月18日 13:18 · [社区讨论](https://news.ycombinator.com/item?id=50545958)

**「背景」** DNS 解析器负责把域名转换成 IP 地址，因此法院可以要求运营商或公共解析服务在解析阶段拦截特定网站，这也是法国针对盗版网站下达 DNS 屏蔽令的技术基础。Quad9 是一家提供公共 DNS 解析服务的非营利组织，其 9.9.9.9 服务常被用户用来替代 ISP 默认解析器。此前在 2024 年 12 月，法国的盗版屏蔽令已扩展到全球范围，Quad9 当时表示会抗争；到 2026 年 10 月下旬，相关报道指出 Quad9 计划在 2026 年 11 月 24 日前退出法国，以避免执行 DNS 审查，同时继续在法院抗争。

**「实际影响」** 自 2026 年 11 月 24 日起，法国用户将无法继续使用 Quad9 的公共 DNS 解析服务，需要改用其他解析器或运营商默认 DNS。对依赖 Quad9 过滤恶意域名的用户来说，这一安全功能也会随之消失；Cloudflare 则警告，法院强制公共解析器执行 DNS 级封锁的做法，可能促使其他服务商重新评估其在法国的可用性。

**「社区讨论」** 评论者 skrebbel 提出关键区分：这究竟是法国法院因专业能力不足做出的荒谬裁决，还是法官对一部本就有问题的法律的正确适用；他认为应据此决定批评对象是法院还是立法者。trentnix 则认为，任何不以“起诉盗版者”为核心的打击盗版手段，都可能成为政府压制其不喜欢的言论的后门；bemtevi 从用户体验角度主张，打击盗版的更好方式是让付费版本比盗版更方便，例如提供 2 至 5 美元、无 DRM 的电影下载。

<details><summary>参考链接</summary>
<ul>
<li>&quot;Quad9 is retracting from Franc…&quot; - Das Federversum - Marcel Waldvogel</li>
<li>French Piracy Blocking Order Goes Global, DNS Service Quad9 Vows to Fight - Reddit</li>
<li><a href="https://blog.cloudflare.com/quad9-withdrawal-from-france/">Quad9’s withdrawal from France: A canary in the coal mine</a></li>
<li><a href="https://techstackups.com/articles/quad9-leaves-france-dns-blocking/">Quad9 Is Leaving France: Why DNS Resolvers Are the Wrong ...</a></li>

</ul>
</details>

**标签**: `#DNS`, `#internet-policy`, `#censorship`, `#piracy`, `#infrastructure`

---

<a id="item-tech-news-8"></a>
### [RadixArk 发布开源权重模型 DaisyRose-27B，训练成本与评测偏向引发讨论](https://www.radixark.com/blog/daisyrose-27b) ⭐️ 7.0/10

RadixArk 的 DaisyRose-27B 是一个新近受到讨论的开源权重 27B 模型，模型已发布在 Hugging Face 的 RadixArk/DaisyRose-27B。社区讨论集中在其基准测试导向的训练、硬件成本和可能的性能取舍上。相关训练 reportedly 使用 144 块 H200 GPU 运行 18 天，但部分能力声明仍依赖厂商或发布者自己的报告，尚需独立验证。

hackernews · de\_sty · 11月18日 19:39 · [社区讨论](https://news.ycombinator.com/item?id=50551046)

**「背景」** DaisyRose-27B 是基于 Qwen3.8-27B 的开放权重模型，由 RadixArk 使用其开源强化学习框架 Miles 进行后训练。据发布方介绍，训练在 144 块 H200 GPU 上进行 18 天，采用全异步模式，使智能体执行与模型学习可以并行推进。相关报道称，该模型将 Terminal-Bench 4.1 的 pass@1 成绩从 5.6% 提升到 12.0%，并在其他六项基准上也有提升。

**「实际影响」** 对使用开源权重的开发者和模型评测者来说，DaisyRose-27B 提供了一个基于 Qwen 3.8-27B、经强化学习后训练的新选择，但需要先确认部署形态：目前讨论中提到没有 GGUF 权重可下载，本地或量化部署可能要等待社区转换。对训练侧团队，其公开的“18 天、144 块 H200”训练规模也给出了一个参考点：在 27B 级模型上做 RL 后训练仍需要相当大的 GPU 投入。评测者还应关注社区提出的权衡问题——如果模型主要针对特定基准优化，最好同时查看未参与训练的其他基准前后对比，以判断通用能力是否受损。

**「社区讨论」** jacquesm 认为，专门拉高某些基准时很难保持能力平衡，希望发布者同时公布未参与训练的其他基准的前后对比。xlayn 则关注实际可用性：目前没有 GGUF 可下载，他打算等量化版本出现后再测试，同时认为 144 块 H200 训练 18 天的硬件投入很高。woah 从评测数据依赖角度提出，这让人怀疑 AI 很快自我改进的说法；pkoiralap 提到同领域的 Sabi-noema 竞品；mips\_avatar 询问 RL 训练拓扑细节。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.radixark.com/blog/daisyrose-27b">DaisyRose-27B: Pushing the Frontier of Post-Training Efficiency</a></li>
<li><a href="https://www.aigpu.cloud/en/blog/radixark-daisyrose-27b-rl-post-training">RadixArk&#x27;s DaisyRose-27B Doubles Agent Benchmark Scores with ...</a></li>
<li><a href="https://news.lavx.hu/article/radixark-releases-daisyrose-27b-built-on-qwen3-8-27b">RadixArk Releases DaisyRose-27B, Built on Qwen3.8-27B</a></li>
<li><a href="https://www.radixark.com/blog/daisyrose-27b">DaisyRose - 27 B : Pushing the Frontier of Post-Training... | RadixArk Blog</a></li>
<li><a href="https://openrouter.ai/qwen/qwen3.8-27b">Qwen 3.8 27 B - API Pricing &amp; Benchmarks | OpenRouter</a></li>
<li><a href="https://huggingface.co/Qwen">Org profile for Qwen on Hugging Face, the AI community building the...</a></li>

</ul>
</details>

**标签**: `#open-source-models`, `#large-language-models`, `#reinforcement-learning`, `#benchmarks`, `#model-training`

---

<a id="item-tech-news-9"></a>
### [Energy-Based Reasoners 项目宣称推理效率提升 385 倍](https://energy-based-reasoners.github.io/) ⭐️ 7.0/10

一个名为 Energy-Based Reasoners 的项目页面宣称，其基于能量模型的推理方法可将推理效率提升 385 倍。该说法目前主要来自项目方自己的宣传材料，公开来源中尚未提供足以验证这一数字的实验细节、基准条件或第三方复现结果。Hacker News 上的讨论显示，部分读者对能量模型在传统 LLM 较弱的逻辑、计数和数学类任务上的潜力感兴趣，但也有评论指出这类模型训练难度高、适用范围较窄，且相关数独求解示例在小规模场景下表现较好、扩展性仍待证明。

hackernews · frenchmajesty · 11月18日 09:29 · [社区讨论](https://news.ycombinator.com/item?id=50543989)

**「背景」** Energy-Based Reasoners（EBR）是一类在潜在推理状态上学习能量函数的模型，把循环式推理更新表述为对该能量函数的梯度下降；能量用于给潜在状态打分，其梯度则引导状态精炼并作为停止信号。项目页面称，在 Sudoku-Extreme 上 EBR 用 5 个样本达到 99.9% 准确率，推理计算量比次优的 Looped flows（5 样本 99.3%）少 345 倍。相关方向也受到产业关注：初创公司 Logical Intelligence 发布了面向推理的商业化能量基模型 Kona 1.0，并宣布图灵奖得主 Yann LeCun 担任技术研究委员会创始主席。

**「影响」** 对关注推理成本和专用推理模型的研究者与工程团队来说，如果 385 倍效率提升能在明确任务和同等精度条件下被复现，可能显著降低某些结构化推理任务的计算开销。但在获得论文级实验细节或独立验证之前，更稳妥的做法是将其视为项目方声明，而不是已确立的通用推理加速结论。

**「社区讨论」** 评论者 Topfi 建议参考由 Yann LeCun 等人参与的 Logical Intelligence，以了解能量模型的背景，并认为其在 LLM 不擅长的初级数学和计数任务上有潜力。评论者 mocmoc 则根据一年左右的实践经验表示，能量模型虽然可作 validators，但训练极难、较为 niche，且 Logical Intelligence 的数独求解器是否能扩展到大规模问题仍存疑。xgk 还指出，论文对“能量”的定义不够清晰，只说模型学习一个给候选预测分配标量能量的函数。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://arxiv.org/abs/2611.08977">[2611.08977] Energy-Based Reasoners: Your Recurrent Reasoner ...</a></li>
<li><a href="https://energy-based-reasoners.github.io/">Energy-Based Reasoners: Your Recurrent Reasoner Should Be an ...</a></li>
<li><a href="https://daily.dev/posts/energy-based-reasoners-385x-more-efficient-inference-dnzpii9nt">Energy-Based Reasoners: 385x more efficient inference</a></li>
<li><a href="https://paperlens.io/idea/kona-1/">Kona 1: Energy - Based Reasoning | PaperLens</a></li>

</ul>
</details>

**标签**: `#energy-based models`, `#inference efficiency`, `#AI reasoning`, `#machine learning`, `#LLMs`

---

<a id="item-tech-news-10"></a>
### [交互式网站可拆解旅行者 1 号直至单颗内存芯片](https://rshekhar.com/voyager/) ⭐️ 7.0/10

开发者 raj-shekhar 发布了一个交互式网站，用户可在线探索旅行者 1 号（Voyager 1）的硬件结构，从核电池内的 24 颗钚球、数据计算机，一直深入到单颗内存芯片，甚至命令计算机内存中的单个比特。网站还提供两艘旅行者号探测器的实时位置追踪、地球接收天线状态、金唱片封面播放说明，以及旅行者 1 号通过无线电修复故障的故事。作者同时发布了一部 4 分钟的相关影片。发布当天恰逢旅行者 1 号距离地球达到 1 光日。

hackernews · raj-shekhar · 11月18日 16:18 · [社区讨论](https://news.ycombinator.com/item?id=50548161)

**「背景」** Voyager 1 是 NASA 于 1977 年发射的探测器，曾飞掠木星、土星及其卫星土卫六，目前是距地球最远的人造物体。据维基百科与半岛电视台报道，它预计在 2026 年 11 月 18 日达到距地球一光天的距离，此时距发射已近 50 年；这一里程碑正是该交互式网站发布的契机。

**「影响」** 对航天爱好者、教育者和工程学习者来说，这个网站把通常只存在于文档和照片中的探测器硬件变成可交互浏览的结构，降低了理解 1970 年代航天计算机、放射性同位素热电发电机和深空通信系统的门槛。作者还公开了核电池、内存芯片、单个比特、金唱片封面和无线电修复故事的直达链接，方便课堂演示或自学时快速定位内容。

**「社区讨论」** 作者 raj-shekhar 在评论区补充了多个深层页面的直达链接。有用户分享了自制的金唱片图像解码工具；也有用户称赞其呈现方式，但指出内容仍有缺漏。glimshe 则质疑该网站是否主要由 AI 生成，并询问是否经过权威来源核对；IAmNotACellist 更关注技术细节，希望了解旅行者 1 号内存芯片故障在门电路、走线、热循环或封装互连层面的确切物理机制。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Voyager_1">Voyager 1 - Wikipedia</a></li>
<li><a href="https://www.aljazeera.com/news/2026/11/18/nasas-voyager-1-hits-record-one-light-day-distance-50-years-after-launch">NASA’s Voyager 1 hits record one light - day distance, 50... | Al Jazeera</a></li>

</ul>
</details>

**标签**: `#spacecraft`, `#hardware`, `#interactive visualization`, `#Voyager`, `#engineering history`

---

<a id="item-tech-news-11"></a>
### [curl 维护者：AI 生成的 Rust 重写难以跟上真实项目修复](https://simonwillison.net/2026/Nov/18/daniel-stenberg/) ⭐️ 7.0/10

curl 维护者 Daniel Stenberg 在博客中比较了 AI 代理对 curl 的 Rust 重写与真实 curl 项目的进展。他说，这些代理在约三周内把 185,000 行 C 代码转换成 340,000 行 Rust 代码；同一时期，真正的 curl 项目合并了超过 300 个提交，包含约 200 个 bug 修复和若干漏洞修复。他进一步指出，再过一个月项目还会再完成约 200 个修复，并质疑这些重写版本能否持续跟上。

rss · Simon Willison · 11月18日 15:58

**「背景」** curl 是一个长期以 C 语言开发、被广泛部署的网络传输库，其维护者 Daniel Stenberg 长期负责上游安全修复。近期出现了由 AI 编程代理生成的 curl Rust 重写版本，Stenberg 在 2026 年 11 月 17 日的博客中对此作出回应：这些代理在约三周内把 185,000 行 C 代码转换成 340,000 行 Rust 代码，但同一时期真正的 curl 项目合并了超过 300 个提交，其中包含约 200 个 bug 修复和若干漏洞修复。他据此质疑这些重写版本能否持续跟上上游的维护节奏。

**「影响」** 对考虑采用 AI 生成 Rust 重写版的团队来说，Stenberg 的数据说明这类快照式移植可能缺少上游持续发布的安全补丁和 bug 修复；如果用于生产环境，需要另行评估其与真实 curl 的同步机制和维护责任。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://daniel.haxx.se/blog/2026/11/17/actual-curl-rewrites-in-rust/">Actual curl rewrites in rust - daniel.haxx.se</a></li>
<li><a href="https://explainx.ai/blog/daniel-stenberg-curl-rust-agent-rewrites-vs-maintenance-november-2026">Daniel Stenberg: Agentic Rust curl Rewrites Cannot Keep Up ...</a></li>
<li><a href="https://letsdatascience.com/news/curl-maintainer-daniel-stenberg-answers-ai-built-rust-rewrit-53834580">Curl maintainer Daniel Stenberg answers AI-built Rust ...</a></li>

</ul>
</details>

**标签**: `#curl`, `#rust`, `#ai-assisted-development`, `#open-source`, `#security`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [美联储会议纪要：多数官员预计还需加息，并担忧 AI 推升通胀与金融风险](https://www.cnbc.com/2026/11/18/fed-minutes-october-2026.html) ⭐️ 8.0/10

美联储 10 月会议纪要显示，几乎所有官员都认为在其基准通胀和就业展望下，进一步上调联邦基金利率目标区间“可能是合适的”，以使通胀及时回到 2%目标；会议以 10 比 2 维持利率在 3.75%-4%不变。官员们还把 AI 相关需求视为“重要的通胀风险来源”，并担忧 AI 相关债务快速增长、融资结构复杂且不透明，若 AI 投资回报不及预期可能放大损失。

rss · CNBC Finance · 11月18日 19:41

**「背景」** 美联储在 10 月会议上以 10 票对 2 票将基准利率维持在 3.75%至 4%区间，Lisa Cook 和 Beth Hammack 投反对票并支持加息 25 个基点。官员们当时选择按兵不动，是为了获取更多信息，以确保通胀及时回到 2%目标。

**「影响」** 若美联储在 12 月继续加息，借贷成本可能进一步上升，影响房贷、企业融资和消费信贷；市场目前普遍定价 12 月加息 25 个基点，但也计入小幅概率出现 50 个基点的更大幅度加息。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.cnbc.com/2026/11/18/fed-minutes-october-2026.html">Fed minutes October 2026 : Officials expect more rate hikes , worry...</a></li>

</ul>
</details>

**标签**: `#Federal Reserve`, `#interest rates`, `#inflation`, `#artificial intelligence`, `#monetary policy`

---

<a id="item-finance-news-2"></a>
### [APEC 深圳峰会：特朗普、习近平与普京会晤三大看点](https://www.cnbc.com/2026/11/18/apec-trump-xi-putin-shenzhen.html) ⭐️ 7.0/10

美国、中国、俄罗斯等亚太经济体领导人本周在深圳出席 APEC 峰会，特朗普与习近平预计将举行双边会谈，重点落实去年达成的贸易休战协议，包括双方 9 月宣布的对 300 亿美元商品互降关税。习近平还将于周四与特朗普和普京举行首次三方领导人会晤，但各方对取得突破的预期较低。

rss · CNBC Finance · 11月18日 06:04

**「背景」** 亚太经合组织（APEC）第三十三次领导人非正式会议于 11 月 18 日至 19 日在深圳举行，普京已抵达深圳，特朗普也前往参会。去年在韩国举行的特朗普与习近平会晤促成为期一年的贸易休战，涉及降低关税和部分稀土出口，该休战已延长至 2027 年 1 月。

**「潜在影响」** 亚洲各国政府将密切关注此次会晤，以判断在中美技术竞争加剧的背景下自身还有多少回旋空间；同时，美国收紧中国获取美国人工智能技术的渠道，可能引发中方反制措施。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://sputnikglobe.com/20261117/putin-lands-in-shenzhen-for-apec-summit--and-historic-trilateral-meeting-with-trump--xi-1125082115.html">Putin Lands In Shenzhen for APEC Summit — and Historic Trilateral ...</a></li>
<li><a href="https://www.aa.com.tr/en/asia-pacific/explainer-trade-technology-and-possible-putin-talks-what-awaits-trump-in-asia/4124280">Anadolu Ajansı: EXPLAINER – Trade , technology and possible Putin...</a></li>

</ul>
</details>

**标签**: `#APEC summit`, `#US-China trade`, `#geopolitics`, `#AI technology restrictions`, `#global energy prices`

---

<a id="item-finance-news-3"></a>
### [腾讯三季度营收增长 8%低于预期，AI 资本开支升至 814 亿元](https://api3.cls.cn/share/article/2537922?os=android&amp;amp;sv=8.8.5&amp;amp;app=cailianpress&amp;amp;selected=) ⭐️ 7.0/10

腾讯公布 2026 年第三季度财报：营收 2073 亿元、同比增长 8%，低于市场预期；归母净利润 636 亿元、同比增长 0.8%。当季资本开支达 814.33 亿元，远超市场预估的 554 亿元，单季自由现金流为负 691 亿元；公司还称 WorkBuddy 每日 Token 消耗量超过 100 万亿，为国内大语言模型 AI 产品中最高。

telegram · zaihuapd · 11月18日 09:20

**「背景」** 资本开支指公司为服务器、数据中心和算力等长期资产投入的资金，是观察 AI 基础设施投入强度的常用指标；自由现金流则是经营现金流减去资本开支后可自由支配的资金。腾讯此前已在 2026 年一季度披露企业服务收入同比增长 20%，并称 WorkBuddy 日活第一，本次三季报进一步显示其 AI 相关投入和调用量继续扩大。

**「影响」** 对关注腾讯及中国科技股的投资者而言，AI 相关资本开支大幅上升和自由现金流转负，意味着短期利润与现金流承压，需关注公司能否将 AI 投入转化为持续收入。

<details><summary>参考链接</summary>
<ul>
<li>腾讯Q1财报：企业服务收入同比增长20%，混元调用量登顶，WorkBuddy日活第一 - 新浪财经</li>

</ul>
</details>

**标签**: `#Tencent`, `#quarterly earnings`, `#AI capex`, `#free cash flow`, `#Chinese tech`

---

<a id="item-finance-news-4"></a>
### [中韩自贸协定服务投资后续谈判实质性结束](https://x.com/Jaemyung_Lee/status/2122988472994791476) ⭐️ 7.0/10

中韩于 11 月 18 日宣布自贸协定服务与投资后续谈判实质性结束。中国承诺在电影、游戏等领域给予韩国最惠国待遇，并扩大旅游、法律、建筑、金融等领域开放。

telegram · zaihuapd · 11月18日 10:02

**「背景」** 中韩自贸协定于 2015 年生效，服务与投资后续谈判自 2018 年 3 月启动，此前多轮谈判进展缓慢。

**「影响」** 韩国影视、游戏、旅游、法律、建筑和金融服务企业有望获得更稳定的中国市场准入条件；双方视听合拍范围也从电影扩展到电视剧、动画、综艺和纪录片。

**标签**: `#China-South Korea FTA`, `#trade policy`, `#services and investment`, `#market opening`, `#audiovisual co-production`

---