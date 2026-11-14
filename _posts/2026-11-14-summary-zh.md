---
layout: default
title: "Horizon Summary: 2026-11-14 (ZH)"
date: 2026-11-14
lang: zh
---

> 从 40 条内容中筛选出 16 条重要资讯。

---

**科技新闻**
1. [FAA orders nationwide ground stop for departing flights](#item-tech-news-1) ⭐️ 8.0/10
2. [TorchTitan 上训练约 1T 参数 MoE：384 块 GH200 达到每 GPU 约 1,300 tokens/s](#item-tech-news-2) ⭐️ 8.0/10
3. [Python 早期贡献者 Tim Peters 去世，享年 74 岁](#item-tech-news-3) ⭐️ 8.0/10
4. [Haskell 社区提出技术愿景，聚焦工具链与生态改进](#item-tech-news-4) ⭐️ 7.0/10
5. [AI 助力解读哥德尔手稿，或藏数百条已证定理](#item-tech-news-5) ⭐️ 7.0/10
6. [ICML 2027 推出两阶段评审与作者评审绑定新规](#item-tech-news-6) ⭐️ 7.0/10
7. [Reddit 用户用 3.1 万参数 Transformer 预测个人血糖](#item-tech-news-7) ⭐️ 7.0/10
8. [四款前沿模型在材料学七部分测试中得分 97.8–100](#item-tech-news-8) ⭐️ 7.0/10
9. [上海公布交大医学院基因编辑事件调查结果](#item-tech-news-9) ⭐️ 7.0/10
10. [微软 Outlook、Teams 全球宕机超 12 小时](#item-tech-news-10) ⭐️ 7.0/10
11. [DeepSeek 开放全家桶应用 API，V4.1-Flash 支持搜索、文件与语音能力](#item-tech-news-11) ⭐️ 7.0/10
12. [OpenAI 推出 ChatGPT Wallet，智能体可代用户完成支付](#item-tech-news-12) ⭐️ 7.0/10

**财经新闻**
1. [黄仁勋丑闻或令美中科技关系进一步紧张](#item-finance-news-1) ⭐️ 8.0/10
2. [卢特尼克因英伟达风波受质询，其家族公司与其关系密切](#item-finance-news-2) ⭐️ 7.0/10
3. [芝加哥联储主席古尔斯比：美联储在通胀问题上“肯定还有工作要做”](#item-finance-news-3) ⭐️ 7.0/10
4. [月之暗面重组股权架构，为香港 IPO 铺路](#item-finance-news-4) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [FAA orders nationwide ground stop for departing flights](https://www.nbcnews.com/news/us-news/faa-orders-nationwide-ground-stop-departing-flights-reasons-safety-rcna609247) ⭐️ 8.0/10

美国联邦航空管理局（FAA）于 2026 年 11 月 13 日发布全国范围的地面停飞令，暂停所有离港航班。据《华尔街日报》援引知情人士的报道，故障似乎影响了由 L3Harris Technologies 负责运营的一个电信网络，该网络承载着空管人员与飞行员通信所需的关键无线电频率；目前尚不清楚雷达数据是否也受到影响。纽约时报的实时报道显示，地面停飞令随后已被解除，但故障的具体原因仍未公布。

hackernews · zulln · 11月13日 21:05 · [社区讨论](https://news.ycombinator.com/item?id=50489641)

**「背景」** 美国联邦航空管理局（FAA）的全国性停飞令依赖一套覆盖各空管中心、供管制员与飞行员保持无线电联络的电信网络；这类系统一旦中断，出发和到达都会受影响。据 Al Jazeera 汇总，这是美国自 2023 年 1 月 FAA 关键计算机系统故障以来的首次全国停飞，更早一次则要追溯到 2001 年 9 月 11 日袭击之后。

**「出行影响」** 全国停飞令在约四小时后解除，但已造成数千架次出发航班延误或取消；LAX 自上午约 10:30 起几乎没有航班起飞，JFK 出发状态大面积显示延误，部分机场航班查询页面也因访问过载而无法打开。旅客应通过航空公司渠道确认后续航班状态，并预留可能的连锁延误时间。

**「社区讨论」** Hacker News 用户指出公开信息非常有限，主要来自交通部长 Duffy 在 X 上的发文；用户 Animats 观察到 LAX 自上午 10:30（太平洋时间）起没有航班起飞，JFK 的离港航班几乎全部显示延误。有用户引用 Gizmodo 报道猜测故障与 FAA 前一日宣布全国推广的 SMART AI 空管调度系统有关，但这只是未经证实的猜测；另有用户对故障与同日微软全球性部分宕机的时间巧合表示怀疑，同样没有证据支持。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.aljazeera.com/news/liveblog/2026/11/13/groundling-live">LIVE: FAA issues US ground stop , some international... | Al Jazeera</a></li>
<li><a href="https://www.cnbc.com/2026/11/13/faa-ground-stop.html">FAA lifts ground stop after four hours, but flight ... - CNBC</a></li>

</ul>
</details>

**标签**: `#FAA`, `#air-traffic-control`, `#infrastructure`, `#outage`, `#aviation`

---

<a id="item-tech-news-2"></a>
### [TorchTitan 上训练约 1T 参数 MoE：384 块 GH200 达到每 GPU 约 1,300 tokens/s](https://www.reddit.com/r/MachineLearning/comments/1xvce5h/scaling_to_1t_moe_on_torchtitan_p/) ⭐️ 8.0/10

作者团队与 TorchTitan 和 PyTorch 维护者合作，报告了在 JUPITER 超算的 384 块 GH200 GPU 上训练约 1 万亿参数 MoE 模型的结果，达到每 GPU 约 1,300 tokens/s，相比起点提升 14 倍。技术方案采用 384 路 FSDP 加节点内 4 路专家并行（EP），并明确放弃流水线并行，理由是流水线需要大量微批次、步长变长，故障排查慢。关键优化包括全量激活检查点、激活卸载到 Grace CPU、用 Muon 替代 Adam、FlexShard 按完整专家分片使 Newton-Schulz 本地执行、梯度以 bf16 传输但 fp32 累加、FP8 专家 all-gather，以及修复 PyTorch 缓存分配器多流内存隔离导致的伪 OOM。作者还贡献了一个 TorchTitan 修复，使参数位于主机内存时 Newton-Schulz 也能在 GPU 上运行，将优化器步进从约 42 秒降到约 2 秒，吞吐提升 35%。

reddit · r/MachineLearning · /u/f14-bertolotti · 11月13日 16:28

**「背景」** TorchTitan 是 PyTorch 官方的大规模训练平台，默认采用 FSDP2 作为一维并行方案，相比 FSDP1 通常能降低约 7% 的单卡显存占用并带来约 1.5% 的平均性能提升。这类框架要训练 1T 级 MoE 模型，核心难点在于单卡放不下全部参数，必须组合 FSDP、专家并行（EP）等切分方式，并尽量减少跨节点通信。本次工作正是在 384 张 GH200 GPU 上，通过 384 路 FSDP 加节点内 4 路 EP 的组合来解决这个问题。

**「实际影响」** 对从事大规模模型训练的团队而言，这项工作表明：在 JUPITER 这类共享的公开超算上，普通用户级权限、无 root 权限的作业也能训练约 1 万亿参数的 MoE 模型，关键约束是节点间 InfiniBand 带宽（约 25 GB/s/GPU）而非 GPU 数量。可借鉴的具体做法包括：用 384 路 FSDP 加节点内 4 路 EP 替代流水线并行以缩短迭代周期；用全量激活重算、激活卸载到 Grace CPU、Muon 优化器换取更长序列和更大计算强度；用 FlexShard 按完整专家分片让 Newton-Schulz 正交化在本地完成；用按注意力成本预打包和组限路由缓解慢节点；用 bf16 传输加 fp32 本地累加的 all-to-all 替代 fp32 reduce-scatter 以减半梯度字节数；以及把 FSDP 侧流临时分配移回计算流，消除虚假 OOM。作者也提醒，组限路由虽使专家负载完全均衡并带来 +7% 吞吐，但早期运行显示可能损害训练效果，仍需验证。

**「社区讨论」** 该 Reddit 帖子当前没有可用的社区评论，因此无法总结读者反馈或争议。帖子本身提到一个未决问题：组限制路由能让专家负载完全均衡并带来约 7% 吞吐提升，但早期实验显示它可能损害训练效果，作者表示仍在评估。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://arxiv.org/pdf/2410.06511">TorchTitan : One-stop PyTorch native solution for production ready...</a></li>
<li><a href="https://www.eurohpc-ju.europa.eu/jupiter-officially-propels-europe-exascale-era-2025-11-17_en">JUPITER Officially Propels Europe into the Exascale Era</a></li>

</ul>
</details>

**标签**: `#large language models`, `#mixture of experts`, `#distributed training`, `#PyTorch`, `#GPU performance`

---

<a id="item-tech-news-3"></a>
### [Python 早期贡献者 Tim Peters 去世，享年 74 岁](https://x.com/Itsfoss/status/2120957452937998716) ⭐️ 8.0/10

Python 创造者 Guido van Rossum 宣布，Python 早期贡献者 Tim Peters 去世，享年 74 岁。Peters 是 Python 的第二位真实用户，也是 Timsort 排序算法的作者和《Python 之禅》（PEP 20）的撰写者。他曾在 Python 软件基金会董事会任职 13 年。该消息目前来自社区公告，具体去世时间与原因未在现有来源中说明。

telegram · zaihuapd · 11月13日 09:55

**「背景」** Tim Peters 是 Python 早期社区的核心人物之一：他于 1999 年在 Python 邮件列表发布后来被称为《Python 之禅》的设计原则，并留下第 20 条“留给 Guido 填写”。他也是 Python 内置 Timsort 排序算法的作者，并曾长期参与 Python 软件基金会治理。Guido van Rossum 在 Python 核心开发论坛的悼念帖中称，Peters 已于今年 7 月 15 日去世，其对 Python 的影响难以估量。

**「对 Python 生态与开发者的实际影响」** 对开发者而言，Tim Peters 的技术遗产仍会持续运行在 Python 生态中：Timsort 是 Python 内置排序算法，因此日常使用 list.sort\(\)、sorted\(\) 以及依赖稳定排序的代码都会继续受其设计影响；《Python 之禅》（PEP 20）也仍是 Python 社区常引用的设计准则。对 Python 软件基金会和核心维护者来说，失去一位曾任职董事会 13 年、参与语言早期设计的贡献者，意味着社区失去了一位重要的历史记忆与技术顾问；对普通用户没有需要立即处理的兼容性或升级动作。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Zen_of_Python">Zen of Python - Wikipedia</a></li>
<li><a href="https://discuss.python.org/t/in-memoriam-tim-peters-1952-2026/110028">In Memoriam: Tim Peters 1952–2026 - Core Development...</a></li>
<li><a href="https://dev.to/romdevin/python-pioneer-and-timsort-creator-tim-peters-passes-away-at-74-36hk">Python Pioneer and Timsort Creator Tim Peters Passes Away at 74</a></li>
<li><a href="https://x.com/clcoding/status/2121103764103000486">Python Coding on X: &quot;The Python community has lost one of its ...</a></li>

</ul>
</details>

**标签**: `#Python`, `#Tim Peters`, `#open source`, `#programming history`, `#Timsort`

---

<a id="item-tech-news-4"></a>
### [Haskell 社区提出技术愿景，聚焦工具链与生态改进](https://discourse.haskell.org/t/a-technical-vision-for-the-haskell-ecosystem/15078) ⭐️ 7.0/10

Haskell 社区成员 hasufell 在 Haskell Discourse 上发布了一份技术愿景提案，讨论改进 Haskell 生态系统的方向。该提案引发了关于开发工具、调试体验、语言采用率以及长期生态目标的讨论。目前该提案仍处于社区讨论阶段，尚未形成正式的实施计划或已发布的能力。

hackernews · cosmic\_quanta · 11月13日 14:43 · [社区讨论](https://news.ycombinator.com/item?id=50484235)

**「背景」** Haskell 是一种以强类型和纯函数式编程著称的语言，其生态长期面临工具链、调试体验和应用场景覆盖等方面的讨论。此次背景涉及 Haskell Foundation 新成立的技术领导委员会：该委员会表示已开始运作，并提出了包括将 GHC 编译器自动检查周期从约六小时缩短到两小时在内的技术愿景；相关目标目前是战略方向，而非已完成的优化结果。

**「影响」** 如果该愿景被社区采纳，Haskell 开发者可能获得更一致的工具链、更好的调试体验和更清晰的生态方向；但提案本身仍处于讨论阶段，具体改进和落地时间尚未确定。对使用 Haskell 的团队而言，值得关注后续关于工具链兼容性、API 稳定性和调试支持的讨论。

**「社区讨论」** 讨论中，用户 ecshafer 提出 Haskell 的简洁性和类型安全特性可能适合 AI 代理编程，因为 AI 可以借助严格的工具链迭代验证正确性。用户 pmkary 则引用 Simon Peyton Jones 的“Haskell is Useless”演讲，指出 Haskell 缺乏像 JavaScript 或 Rust 那样的跨平台通用性，难以覆盖桌面、移动和 Web 应用开发。用户 georgewsinger 分享了在 Haskell VR 合成器中实现实时运行时调试的经验，认为交互式调试在 Haskell 生态中被低估。用户 time4tea 则将 JVM 生态作为参照，指出其在长期 API 稳定性和软硬件映射方面已实现部分类似目标。用户 carterschonwald 肯定了 hasufell 的思路，并分享了用 Haskell 构建高性能 CAD STEP 文件读写器的经验，称其在大型 CAD 装配上比部分 C 实现慢 20-30%。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://discourse.haskell.org/t/a-technical-vision-for-the-haskell-ecosystem/15078">A technical vision for the Haskell ecosystem - Haskell Foundation...</a></li>
<li><a href="https://dzen.ru/b/avdWQF0woA1Z8MqS">Haskell Foundation запустила техкомитет: цель — ускорить... | Дзен</a></li>

</ul>
</details>

**标签**: `#Haskell`, `#programming languages`, `#developer tooling`, `#open source`, `#ecosystem`

---

<a id="item-tech-news-5"></a>
### [AI 助力解读哥德尔手稿，或藏数百条已证定理](https://www.theguardian.com/science/2026/nov/13/kurt-godel-notebooks-ai-helps-unlock-hidden-discoveries-man-who-transformed-maths) ⭐️ 7.0/10

据《卫报》2026 年 11 月 13 日报道，研究人员正借助 AI 解读数学家库尔特·哥德尔（Kurt Gödel）留下的笔记本，其中据称可能包含数百条已被证明的定理。这些手稿以难以辨识的哥贝尔斯贝格速记法（Gabelsberger shorthand）写成，长期难以系统整理。目前报道仍属初步：哪些内容会被确认为新成果、其数学价值如何，尚待研究人员核实，不宜将“数百条定理”视为已经公开验证的发现。

hackernews · bookofjoe · 11月13日 17:30 · [社区讨论](https://news.ycombinator.com/item?id=50486748)

**「背景」** 库尔特·哥德尔是 20 世纪最具影响力的逻辑学家之一，他在 1931 年发表的两条不完备定理改变了数学基础研究。此后他只发表了少量论文，而大量手稿以几乎失传的 Gabelsberger 速记写成，长期难以解读。

**「潜在影响」** 对数学史和逻辑研究者而言，若 AI 辅助识别手稿的方法可靠，哥德尔未发表笔记可能成为检验其思想发展脉络的新材料；但相关结论仍需经过数学界核验，短期内更可能推动的是手稿整理与历史研究，而非直接产生可用的新定理。

**「社区讨论」** Hacker News 上的讨论偏谨慎。用户 iltennico 认为，哥德尔是极严格的自我审查者，通常只发表“无懈可击”的工作，因此笔记中未必会偶然藏着大量未被察觉的重要新定理。hobo123 则对解读哥贝尔斯贝格速记的难度表示怀疑，称其父亲直到 2020 年去世前仍使用该速记法，并调侃真正能读的人可能极少。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.theguardian.com/science/2026/nov/13/kurt-godel-notebooks-ai-helps-unlock-hidden-discoveries-man-who-transformed-maths">‘Ahead of his time’: AI helps unlock discoveries hidden... | The Guardian</a></li>
<li><a href="https://o-server.main.jp/hacker-news/en/articles/2026/11/14/ai-project-decodes-kurt-g-del-s-private-notebooks-using-gabelsber-50486748.html">AI Project Decodes Kurt Gödel&#x27;s Private Notebooks Using ...</a></li>

</ul>
</details>

**标签**: `#artificial intelligence`, `#mathematics`, `#history of science`, `#Kurt Gödel`, `#handwriting recognition`

---

<a id="item-tech-news-6"></a>
### [ICML 2027 推出两阶段评审与作者评审绑定新规](https://www.reddit.com/r/MachineLearning/comments/1xvkxbj/icml_2027_changes_d/) ⭐️ 7.0/10

根据 ICML 2027 征稿启事，会议将采用两阶段评审：先由领域主席（AC）判断论文是否进入完整评审，拟在第一阶段被拒的论文还需高级领域主席（SAC）确认；作者会在 2027 年 2 月 23 日前收到简短理由。新规还包括：每人最多出现在 20 篇投稿中，每篇论文必须从作者名单中指定一名互惠审稿人（每名审稿人最多负责 6 篇），有 3 篇及以上投稿的作者必须加入程序委员会，不合规论文可能被直接拒稿。最关键的限制是，每位作者最多只能有一篇论文没有任何符合条件的互惠审稿人；如果团队中常有本科生、实习生或领域外合作者无法承担审稿，作者只有一次“豁免”机会。

reddit · r/MachineLearning · /u/Gravitist · 11月13日 21:53

**「背景」** ICML 2027 将于 2027 年 7 月 31 日至 8 月 6 日在巴西里约热内卢 Riocentro 举行。会议组织方在说明中称，投稿数量持续增长且快于合格审稿人数量，因此 2027 年引入投稿配额并强化互惠审稿要求；这些规则与 ICLR 2027 已采用的规则类似。

**「对投稿人与审稿人的直接影响」** 对计划投稿 ICML 2027 的研究团队来说，作者身份现在会直接转化为审稿义务：每人最多参与 20 篇投稿；每篇论文必须从作者中指定一名 reciprocal reviewer，且每名 reviewer 最多承担 6 篇；有 3 篇及以上投稿的作者必须进入 program committee（担任 reviewer、area chair 或 senior area chair，AC/SAC/组委会成员可凭该角色满足要求）。团队还需要注意“无合格 reciprocal reviewer”的论文每位作者只能有一篇，否则可能被 desk reject。因此，跨组合作和包含本科生、实习生等难以审稿成员的论文，需要提前规划作者名单和审稿安排。

**「社区讨论」** 发帖人 /u/Gravitist 认为这些规则总体合理，尤其是把作者投稿数量与审稿义务挂钩，有助于缓解长期存在的审稿人负担问题。他主要担心第一阶段筛选可能因 AC 快速阅读而漏掉好论文，但认为 SAC 复核能部分降低这一风险。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://icml.cc/Conferences/2027/ReciprocalReviewingAndSubmissionQuotas">2027 Reciprocal Reviewing And Submission Quotas - icml.cc</a></li>
<li><a href="https://icml.cc/Conferences/2027">2027 Conference - icml.cc</a></li>
<li><a href="https://icml.cc/Conferences/2027/ReciprocalReviewingAndSubmissionQuotas">2027 Reciprocal Reviewing And Submission Quotas - icml.cc</a></li>

</ul>
</details>

**标签**: `#machine learning`, `#ICML`, `#peer review`, `#academic publishing`, `#conference policy`

---

<a id="item-tech-news-7"></a>
### [Reddit 用户用 3.1 万参数 Transformer 预测个人血糖](https://www.reddit.com/r/MachineLearning/comments/1xvja5n/i_have_trained_a_model_to_predict_my_blood_sugar_p/) ⭐️ 7.0/10

Reddit 用户 /u/0xdeadf1sh 发布了一个自研血糖预测模型：一个仅 31,253 参数的 encoder-only Transformer，先在约 19,200 CGM-年的合成数据上预训练，再用 LoRA 适配器在个人数据上微调。个人数据来自 115 天连续血糖监测（CGM），其中 80 天训练、35 天测试；模型可预测未来 2 小时血糖，并支持补全缺失曲线、回溯预测，以及输入胰岛素剂量（U）和碳水（克数 G、升糖指数 GI）作为动作曲线。训练目标使用 Kovatchev 风险空间的 \{DILATE, MSE\} 与 pinball loss，并结合学习到的 Kendall-Gal 权重。作者称其在已发表模型中具有竞争力，但这是自报结果，尚无公开基准或外部验证；作者也承认在预测未来约 30 分钟内低血糖方面仍不如自己。源代码已在 GitHub（0xdeadf1sh/T1DMAI）公开。

reddit · r/MachineLearning · /u/0xdeadf1sh · 11月13日 20:48

**「背景」** 连续血糖监测（CGM）设备会持续记录血糖曲线，而 1 型糖尿病管理需要同时考虑胰岛素剂量、碳水化合物摄入及其升糖指数对血糖的影响。作者此前开源了 T1DMAI 项目，用多种模型在自己的血糖数据上做 2 小时预测；本次报告的 31,253 参数编码器-only Transformer 是该方向的延续，并新增了约 19,200 CGM 年合成数据预训练和 LoRA 个性化微调。

**「意义与限制」** 对个人糖尿病管理工具开发者而言，这个项目展示了一条低成本个性化路线：用大规模合成 CGM 数据预训练极小模型，再用 LoRA 在个人短周期数据上适配，且模型原生支持 3.5–7.0 天的可变上下文窗口，并在 ≥48 小时上下文下涌现出从血糖轨迹推断时段的能力（而非把时段作为输入特征）。不过它目前只是单用户自报实验：合成模拟器面向反事实推理，但作者尚无下游基准验证该能力，碳水估计也存在误差，因此不能视为可推广或临床可用的证据。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/0xdeadf1sh/T1DMAI">GitHub - 0xdeadf1sh/T1DMAI: An encoder-only transformer that ...</a></li>
<li><a href="https://zeli.app/story/50444761">T1DMAI - Blood glucose forecasting model · Hacker News | Zeli</a></li>

</ul>
</details>

**标签**: `#machine learning`, `#transformers`, `#time series`, `#healthcare AI`, `#synthetic data`

---

<a id="item-tech-news-8"></a>
### [四款前沿模型在材料学七部分测试中得分 97.8–100](https://www.reddit.com/r/MachineLearning/comments/1xvgf6h/four_frontier_models_scored_978100_on_a_7part/) ⭐️ 7.0/10

一位石墨烯与二维材料研究者自建了一套模拟科研组日常技术工作的七部分测试，包括带单位与离群值陷阱的拉伸数据整理、隐藏结构校验的 CIF 密度函数、物理估算、含 10 处植入错误与 6 个可疑但正确诱饵的稿件评审、校准类问题、实验设计和受限摘要写作；全部使用合成数据并由代码评分，满分 100。在 Gemini 4 Carbon、Gemini 4 Hydrogen（Antigravity）、Claude Opus 5.5 和 Claude Fable 5.2 各跑 3 次的设置下，平均分为 100.0、99.7、99.3 和 98.5，12 次运行全部落在 97.8–100 之间，每次耗时 7–24 分钟。作者称所有运行都避开了单位陷阱、通过隐藏 CIF 测试、找齐 10 处植入错误且无误报，并拒绝了错误前提和伪造论文，失分主要在格式细节；有 3 次运行还发现了作者未植入的真实错误。作者将这一结果解读为：有明确流程的有限工作已被前沿模型饱和，真正的差距在长时程、开放式研究任务，因此下一步将构建 2–6 小时、带预算、仪器、目标规格和完整行动日志的模拟实验室评测。

reddit · r/MachineLearning · /u/v\_aravind · 11月13日 18:58

**「背景：为什么这个满分测试引出评测方法问题」** 作者提到的 FrontierScience 是 2026 年 1 月公开的科学推理基准，用按题定制的评分细则评估专家级物理、化学、生物任务，其动机正是传统科学基准已接近饱和。METR 的“时间跨度”指标则把模型能力表示为能可靠完成的人类任务时长，因此常被用来讨论长时程、开放式工作。这条背景解释了帖子把“有明确流程的短任务已饱和”与“下一步应评测 2–6 小时模拟实验和轨迹质量”联系起来的原因。

**「评测启示」** 对 AI 评测工作者而言，这个案例说明高结构化、可代码判分的领域基准可能很快失去区分度，需要把评分重心转向轨迹质量，例如从早期错误假设中恢复的能力，以及 2–6 小时量级任务的人类基线测量。作者也列出了重要限制：只有一名出题人、每个模型仅 3 次运行，且测试是在 Claude Opus 5.5 协助下设计的，因此结果不宜当作模型能力的强结论。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://arxiv.org/html/2601.21165v1">FrontierScience: Evaluating AI’s ability to perform expert ...</a></li>
<li><a href="https://arxiv.org/abs/2601.21165">[2601.21165] FrontierScience: Evaluating AI&#x27;s Ability to ... Evaluating AI’s ability to perform scientific research tasks FrontierScience Research Leaderboard — November 2026 FrontierScience Research Leaderboard FrontierScience Bench: Evaluating AI Research Capabilities in ... GitHub - medicalsphere/FrontierScience: Implementation of ...</a></li>

</ul>
</details>

**标签**: `#AI evaluation`, `#benchmarking`, `#materials science`, `#long-horizon agents`, `#frontier models`

---

<a id="item-tech-news-9"></a>
### [上海公布交大医学院基因编辑事件调查结果](https://mp.weixin.qq.com/s/p0iC3tcI1yr10EBl2NjUvg) ⭐️ 7.0/10

上海官方公布上海交通大学医学院基因编辑事件调查结果：涉事患儿确诊罕见病 Snijders Blok-Campeau 综合征，家属 2023 年联系仇某某团队定制基因编辑疗法，2025 年 3 月注射后因血栓性微血管病死亡，相关论文于 2026 年 2 月发表于《自然》。调查认定临床前研究、伦理审查和知情同意存在缺陷，部分人员收受家属财物约 106 万元。仇某某、杨某被开除并取消资格 5 年，相关机构被约谈整改和行政处罚。

telegram · zaihuapd · 11月13日 09:24

**「背景」** Snijders Blok-Campeau 综合征是一种罕见病，此前缺乏成熟疗法，因此家属在 2023 年联系上海交通大学医学院仇某某团队寻求定制基因编辑治疗。2026 年 7 月 26 日，上海交通大学医学院曾发布情况说明，称已针对仇某某相关论文和附属新华医院开展的一例临床研究成立专项工作组进行全面调查；本次通报是该调查的处置结果。

**「影响」** 对参与定制基因编辑疗法的研究者和机构而言，此案确立了更明确的问责边界：仇某某、杨某被开除并取消资格 5 年，相关机构被约谈整改和行政处罚，说明临床前研究、伦理审查和知情同意的缺陷可能带来职业与机构层面的直接后果。对计划开展个体化基因编辑治疗或早期临床试验的团队，这提示需要把安全性评估、独立伦理审查和知情同意流程作为前置条件，并避免与患者家属存在财物往来。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.nbd.com.cn/articles/2026-07-27/4515558.html">nbd.com.cn/articles/2026-07-27/4515558.html</a></li>
<li><a href="https://www.straitstimes.com/asia/east-asia/china-fires-researchers-after-child-dies-in-gene-editing-trial">China fires researchers after child dies in gene - editing trial</a></li>

</ul>
</details>

**标签**: `#gene editing`, `#bioethics`, `#clinical trials`, `#regulation`, `#biotechnology`

---

<a id="item-tech-news-10"></a>
### [微软 Outlook、Teams 全球宕机超 12 小时](https://www.reuters.com/technology/microsoft-365-outlook-down-thousands-us-users-downdetector-shows-2026-11-12/) ⭐️ 7.0/10

微软 Outlook、Teams 和 Copilot 在 11 月 13 日仍处于宕机状态，故障持续超过 12 小时，打乱了全球企业与政府的通信。微软将原因归为服务器问题，并表示未发现恶意活动，已扩大修复范围并看到服务回稳迹象。受影响方包括澳大利亚、日本和美国部分政府机构；欧交所 Euronext 的邮件受阻，台湾有金融机构改用传真确认交易。据该报道，这是微软 365 服务今年第二次中断。

telegram · zaihuapd · 11月13日 12:21

**「背景」** 微软 365 是许多企业和政府机构依赖的云端办公与通信套件，Outlook 负责邮件、Teams 负责即时消息和会议、Copilot 提供辅助功能，因此这类服务一旦同时中断，会直接影响日常业务流程。本次事件是微软 365 今年第二次重大中断；路透社后续报道显示，故障在持续超过 24 小时后于周五开始缓解。

**「影响」** 受影响的企业和政府机构需要为依赖 Microsoft 365 的关键通信准备备用渠道：本次故障已波及 70 多个国家，导致澳大利亚、日本和美国部分政府机构中断，欧交所 Euronext 邮件受阻，台湾有金融机构改用传真确认交易。对组织而言，应检查邮件、协作和 Copilot 相关流程是否有降级方案，并在服务恢复后核对延迟或丢失的消息。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.reuters.com/technology/microsoft-365-outlook-down-thousands-us-users-downdetector-shows-2026-11-12/">Microsoft Outlook, Teams outage eases after over a day ...</a></li>
<li><a href="https://en.wikipedia.org/wiki/2026_Microsoft_outage">2026 Microsoft outage - Wikipedia</a></li>

</ul>
</details>

**标签**: `#Microsoft 365`, `#Outage`, `#Cloud Services`, `#Enterprise Software`, `#Reliability`

---

<a id="item-tech-news-11"></a>
### [DeepSeek 开放全家桶应用 API，V4.1-Flash 支持搜索、文件与语音能力](https://mp.weixin.qq.com/s/78KBHc4-4N5b2vfL9SkutQ) ⭐️ 7.0/10

DeepSeek 于 2026 年 11 月 13 日宣布开放“全家桶应用 API”。开发者在原有 API 中开启对应参数后，即可获得深度思考搜索、文件输入、阅读链接、语音等对话能力，工具调用与上下文拼接由服务端自动完成。V4.1-Flash 模型已在三个接口支持这些能力；Search、Fetch、OCR、ASR、TTS 也可单独调用。官方同时开源了可导入历史对话的前端 Demo（deepseek-ai/chat-demo），开发者可基于 API 在本地部署类似 DeepSeek 网页端的应用，体验地址为 https://deepseek-ai.github.io/chat-demo/。公告未提供详细基准测试或实现细节。

telegram · zaihuapd · 11月13日 14:27

**「背景」** DeepSeek 此前主要通过网页端提供深度思考、联网搜索、文件解析和语音等应用能力，开发者若要复用这些体验，通常需要自行实现工具调用与上下文拼接。此次公告将 Search、Fetch、OCR、ASR、TTS 等能力拆分为可单独调用的 API，并配合 V4.1-Flash 模型开放，属于把网页端能力进一步 API 化的更新。

**「对开发者的影响」** 开发者现在可以通过在现有 DeepSeek API 调用中开启参数，直接获得深度思考搜索、文件输入、链接阅读、语音识别与语音合成等应用能力，无需自行搭建工具调用和上下文拼接流程；Search、Fetch、OCR、ASR、TTS 也可单独调用。第三方报道显示这些能力由 V4.1-Flash 在服务端处理，且已有公开定价信息（如 $0.058 起），但具体计费细节仍需以官方文档为准。团队还可以使用开源的 deepseek-ai/chat-demo 前端，把 DeepSeek 网页端体验本地部署，并导入历史对话。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://extrapolator.ai/2026/11/13/deepseek-flash-api-adds-web-search-file-parsing-and-ocr-tools/">DeepSeek Flash API adds web search, file parsing, and OCR ...</a></li>
<li><a href="https://explainx.ai/blog/deepseek-full-suite-application-apis-web-search-file-url-asr-tts-pricing-2026">DeepSeek App APIs: Search, Files, ASR, TTS From $0.058 ...</a></li>

</ul>
</details>

**标签**: `#DeepSeek`, `#API`, `#AI Agents`, `#Multimodal AI`, `#Open Source`

---

<a id="item-tech-news-12"></a>
### [OpenAI 推出 ChatGPT Wallet，智能体可代用户完成支付](https://openai.com/index/introducing-chatgpt-wallet/) ⭐️ 7.0/10

OpenAI 发布 ChatGPT Wallet，与美国运通、万事达和 Visa 合作，让 AI 智能体在不接触用户真实卡号的情况下完成付款。该功能自 2026 年 11 月 13 日起在美国通过 dots 面向 18 岁以上的 ChatGPT Pro 订阅用户开放，并要求使用美国发行的银行卡。用户需逐笔核对商品与金额，通过 Face ID 或指纹确认，再由支付网络下发替代真实卡号的支付令牌。

telegram · zaihuapd · 11月13日 15:43

**「背景」** ChatGPT Wallet 建立在“智能体商务”这一方向上：让 AI 助手代表用户完成交易，而不是只提供信息。其关键前提是支付行业的令牌化机制——支付网络用一次性或受限的支付令牌替代真实卡号，从而降低智能体持有敏感卡信息带来的风险。OpenAI 此前已围绕智能体执行任务推出 dots 等能力，这次则是把“执行”延伸到需要用户逐笔授权的支付环节。

**「对用户与支付生态的具体影响」** 对符合条件的美国 ChatGPT Pro 用户而言，这意味着可以把部分购物流程交给 ChatGPT 内的智能体执行，但每笔交易仍需用户核对商品与金额，并通过 Face ID 或指纹确认，支付时使用支付网络下发的令牌而非真实卡号。对开发者与商户来说，接入 dots 与现有卡网络成为让智能体完成交易的现实路径，同时需要处理智能体误选商品、数量或规格等争议场景。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://openai.com/index/introducing-chatgpt-wallet/">Introducing ChatGPT Wallet - OpenAI</a></li>
<li><a href="https://help.openai.com/en/articles/20001654-making-purchases-with-chatgpt-wallet">Making purchases with ChatGPT Wallet | OpenAI Help Center</a></li>
<li><a href="https://www.explainx.ai/blog/chatgpt-wallet-dots-agent-payments-pro-us-visa-mastercard-amex-2026">ChatGPT Wallet: Agents Pay With Tokens, Not Your Card ...</a></li>
<li><a href="https://tech.yahoo.com/ai/chatgpt/articles/openai-launches-chatgpt-wallet-ai-190219313.html">OpenAI Launches ChatGPT Wallet for AI Agent Payments</a></li>

</ul>
</details>

**标签**: `#OpenAI`, `#ChatGPT`, `#payments`, `#AI agents`, `#fintech`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [黄仁勋丑闻或令美中科技关系进一步紧张](https://www.cnbc.com/2026/11/13/jensen-huang-nvidia-us-china-relations.html) ⭐️ 8.0/10

英伟达前 CEO 黄仁勋被指与一名涉嫌中国间谍的商人有染，已辞职并同意在 11 月 26 日感恩节前到美国国会作证。分析人士认为，此事可能促使美国国会今年内收紧对华半导体出口管制，尽管美中仍维持脆弱的贸易休战。

rss · CNBC Finance · 11月13日 02:56

**「背景」** 华盛顿自 2022 年起限制英伟达向中国出售先进芯片，但特朗普政府在 2025 年放松了多项拜登时期的限制。黄仁勋已辞任英伟达 CEO，并同意在 11 月 26 日感恩节前到国会作证；特朗普与习近平预计将于 11 月 18 日至 19 日在深圳举行的 APEC 会议上会面。

**「影响」** 若美国收紧半导体出口管制，依赖先进 AI 芯片的中国企业可能加速转向国产替代，而英伟达等美国芯片公司则面临对华销售进一步受限的风险；北京也可能以稀土或芯片制造材料供应作为反制筹码。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.cnn.com/2026/11/11/business/live-news/nvidia-jensen-huang-investigation-fallout">Jensen Huang summoned to testify before Congress after resigning ...</a></li>
<li><a href="https://www.nytimes.com/live/2026/11/12/business/nvidia-jensen-huang-resigns">Nvidia Updates: Huang ’s Resignation Reverberates Through...</a></li>
<li><a href="https://www.bbc.com/news/live/c6zjry11v8w1t">Huang agrees to appear before Congress , US lawmakers... - BBC News</a></li>
<li><a href="https://www.theguardian.com/us-news/2026/nov/13/trump-nvidia-stock-jensen-huang-us-china">Trump bought Nvidia stock as he helped chipmaker... | The Guardian</a></li>
<li><a href="https://ru.wikipedia.org/wiki/%D0%A1%D0%B0%D0%BC%D0%BC%D0%B8%D1%82_%D0%90%D0%A2%D0%AD%D0%A1_2026">Саммит АТЭС 2026 — Википедия</a></li>
<li><a href="https://www.yahoo.com/news/politics/articles/explainer-five-features-apec-know-030536617.html">Explainer-Five facts about APEC with Trump , Putin and Xi set to attend</a></li>

</ul>
</details>

**标签**: `#US-China relations`, `#Nvidia`, `#export controls`, `#semiconductors`, `#geopolitics`

---

<a id="item-finance-news-2"></a>
### [卢特尼克因英伟达风波受质询，其家族公司与其关系密切](https://www.cnbc.com/2026/11/13/howard-lutnick-nvidia-jensen-huang-china-cantor-fitzgerald.html) ⭐️ 7.0/10

CNBC 报道，美国商务部长霍华德·卢特尼克之子执掌的 Cantor Fitzgerald 在 2025 年 9 月至 2026 年 3 月间将所报英伟达持股数量减少约 49%（从 350 万股以上降至 178 万股，价值从 6.52 亿美元降至 3.10 亿美元），同期卢特尼克被指抵制对涉嫌向中国走私英伟达芯片的新加坡公司 Megaspeed 的打击。目前没有证据表明其子事先知情、持股变化与情报警告有关，或公司业务影响了卢特尼克的决策。

rss · CNBC Finance · 11月13日 23:42

**「背景」** 霍华德·卢特尼克在 2025 年 2 月出任商务部长前，长期执掌华尔街投行 Cantor Fitzgerald；据 CBS News，他获提名时该行持有约 12 亿美元英伟达股票，目前则由他的儿子布兰登和凯尔负责经营。围绕英伟达的争议核心是出口管制：美国通过“实体清单”限制被怀疑将先进 AI 芯片转运至中国的公司，而新加坡公司 Megaspeed 正因涉嫌把英伟达芯片流入中国而成为白宫和情报官员要求打击的对象。据 Axios 及《纽约时报》报道，卢特尼克多次抵制相关限制，财政部长贝森特也公开表示财政部、国防部、国务院和贸易代表办公室数月来都支持把 Megaspeed 列入实体清单。

**「影响」** 该报道可能加剧对卢特尼克及商务部出口管制决策的利益冲突审视，并使 Cantor 与英伟达生态的融资业务受到更多公开关注。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.nytimes.com/2026/11/12/us/politics/lutnick-nvidia-commerce-china-chips.html">Howard Lutnick Took Softer Line on Nvidia as Calls for Tougher...</a></li>
<li><a href="https://www.cbsnews.com/news/lutnick-nvidia-ai-chips-china/">Lutnick should have prevented the diversion of sensitive Nvidia AI...</a></li>
<li><a href="https://www.thestreet.com/technology/scott-bessent-and-lutnick-clash-over-nvidia-chips-and-china">Scott Bessent and Lutnick clash over Nvidia chips and... - TheStreet</a></li>

</ul>
</details>

**标签**: `#Nvidia`, `#Howard Lutnick`, `#Cantor Fitzgerald`, `#export controls`, `#government ethics`

---

<a id="item-finance-news-3"></a>
### [芝加哥联储主席古尔斯比：美联储在通胀问题上“肯定还有工作要做”](https://www.cnbc.com/2026/11/13/chicago-feds-goolsbee-says-central-bank-has-definitely-got-work-to-do-on-inflation.html) ⭐️ 7.0/10

芝加哥联储主席古尔斯比表示，美联储在通胀问题上“肯定还有工作要做”，以重建政策公信力。此前数据显示，10 月生产者价格指数（PPI）同比上涨 6.5%，创 2022 年 11 月以来最高，市场普遍预期美联储 12 月将加息 25 个基点。

rss · CNBC Finance · 11月13日 14:22

**「背景」** 生产者价格指数（PPI）衡量企业批发环节的价格变化，常被视为通胀的领先指标。美国 10 月 PPI 同比上涨 6.5%，为 2022 年 11 月以来最高，而美联储的通胀目标是 2%。

**「潜在影响」** 若美联储在 12 月加息，借贷成本可能上升，影响企业融资、房贷利率及整体金融市场环境。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.cnbc.com/2026/11/13/ppi-inflation-report-october-2026.html">PPI inflation report October 2026</a></li>

</ul>
</details>

**标签**: `#Federal Reserve`, `#inflation`, `#monetary policy`, `#producer price index`, `#interest rates`

---

<a id="item-finance-news-4"></a>
### [月之暗面重组股权架构，为香港 IPO 铺路](https://www.wsj.com/tech/chinas-moonshot-ai-restructures-to-pave-way-for-ipo-49f09abb) ⭐️ 7.0/10

据《华尔街日报》援引知情人士报道，中国 AI 公司月之暗面正在重组公司架构，计划在香港进行 IPO；其开曼群岛控股公司将被停用，早期美元投资人的股份将转入中国境内主要运营实体。

telegram · zaihuapd · 11月13日 11:29

**「背景」** 月之暗面是 Kimi 的开发商，业务主要在中国，但此前在开曼群岛设有控股公司，许多早期投资者以美元投资该控股公司。

**「影响」** 若重组和上市推进，早期美元投资人将转为持有境内运营实体股份，而关注中国 AI 赛道的投资者可能获得一个新的港股标的。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.wsj.com/tech/chinas-moonshot-ai-restructures-to-pave-way-for-ipo-49f09abb">China’s Moonshot AI Restructures to Pave Way for IPO</a></li>
<li><a href="https://cn.wsj.com/articles/%E4%B8%AD%E5%9B%BDai%E5%85%AC%E5%8F%B8%E6%9C%88%E4%B9%8B%E6%9A%97%E9%9D%A2%E5%8D%B3%E5%B0%86%E5%AE%8C%E6%88%90%E6%9E%B6%E6%9E%84%E9%87%8D%E7%BB%84-%E4%B8%BAipo%E9%93%BA%E8%B7%AF-718a1b42">中国AI公司月之暗面即将完成架构重组，为IPO铺路 - WSJ</a></li>

</ul>
</details>

**标签**: `#Moonshot AI`, `#Hong Kong IPO`, `#corporate restructuring`, `#China AI`, `#capital markets`

---