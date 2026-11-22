---
layout: default
title: "Horizon Summary: 2026-11-22 (ZH)"
date: 2026-11-22
lang: zh
---

> 从 24 条内容中筛选出 9 条重要资讯。

---

**科技新闻**
1. [黎曼猜想 Lean 形式化证明获多方验证](#item-tech-news-1) ⭐️ 9.0/10
2. [GPGME 双重释放漏洞披露，影响大量使用 GnuPG 的软件](#item-tech-news-2) ⭐️ 8.0/10
3. [浙江大学在超导芯片上首次真机实现量子随机存储器](#item-tech-news-3) ⭐️ 8.0/10
4. [显示器以太网直通导致下载速度下降约 75% 的排查](#item-tech-news-4) ⭐️ 7.0/10
5. [Muru：mod\_wsgi 作者用 Rust 打造的 Python ASGI/WSGI 服务器](#item-tech-news-5) ⭐️ 7.0/10
6. [微软推出 RDMA over USB4 预览，多台 Windows PC 可合跑一个本地 AI 模型](#item-tech-news-6) ⭐️ 7.0/10
7. [特斯拉海外推送 FSD v15，新增 Reality View 可视化](#item-tech-news-7) ⭐️ 7.0/10

**科技博客**
1. [写好代码的关键：避免灾难性失误](#item-tech-blog-1) ⭐️ 7.0/10

**财经新闻**
1. [特朗普称仍支持商务部长卢特尼克，并希望黄仁勋道歉后回归](#item-finance-news-1) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [黎曼猜想 Lean 形式化证明获多方验证](https://leanprover-community.github.io/blog/posts/riemann-hypothesis/) ⭐️ 9.0/10

2026 年 11 月 20 日，Levent Alpöge 发布了黎曼猜想的 Lean 形式化证明，代码库约 1700 万行。11 月 21 日，Lean FRO 与 Mathlib Initiative 联合声明称该命题与证明均正确：社区确认其命题与 Mathlib 中的 RiemannHypothesis 一致，代码库可无错编译，并有多个独立证明检查器验证证明有效。社区评论提到该工作涉及大规模 AI 辅助形式化，且有人类专家参与把关；这些属于讨论中的说法，最终意义仍取决于更广泛的数学界验证与接受。

hackernews · g-b-r · 11月21日 14:36 · [社区讨论](https://news.ycombinator.com/item?id=50589618)

**「背景」** 黎曼猜想是数论中关于黎曼 ζ 函数非平凡零点分布的核心未解问题，其形式化验证依赖 Lean 这类证明助手和 Mathlib 数学库。此前，Levent Alpöge 已作为研究数论与算术统计的数学家为人所知，并加入 Anthropic 担任技术成员；2026 年 11 月 20 日，他发布了约 1700 万行代码的 Lean 证明库，随后 Lean 与 Mathlib 社区于 11 月 21 日联合认证该证明成立。

**「对数学与形式化验证的影响」** 对数学界而言，若该证明经更广泛审查后保持成立，黎曼猜想这一 1859 年提出的素数分布核心问题将获得机器可检查的证明，相关依赖性结果也可能随之被重新评估。对形式化验证社区，这次验证展示了 Lean/Mathlib 已能承载超大规模前沿数学证明，并推动对多内核交叉验证、独立检查器可靠性以及 AI 辅助形式化流程可信度的进一步检验。对研究者和工程团队，更直接的影响是：大规模 AI 生成证明需要人类专家逐层把关，且最终结论应等待 Mathlib/Lean FRO 之外更多独立复核后再作为定论引用。

**「社区讨论」** 有评论认为，由于存在多个不同实现和一致性证明的内核，若黎曼猜想为假，则需要所有内核同时出现影响一致性证明和该证明本身的漏洞，因此“利用漏洞通过验证”的可能性已很小。也有评论提出独立检查器未必完全独立，并举例称过去曾有伪造的 Collatz 猜想反驳通过过某个检查器，但认为本次有人类专家参与，模型绕过专家的可能性较低。还有评论强调应给 Levent Alpöge 本人很高评价，认为他极善于发挥 AI 工具的能力。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Levent_Alp%C3%B6ge">Levent Alpöge - Wikipedia</a></li>
<li><a href="https://kingy.ai/blog/levent-alpoge-claude-riemann-hypothesis-proof/">Riemann hypothesis proof verified in Lean</a></li>
<li><a href="https://leanprover-community.github.io/blog/posts/riemann-hypothesis/">Lean verification of the Riemann Hypothesis | Lean community blog</a></li>
<li><a href="https://www.newscientist.com/article/2600134-anthropic-mathematician-claims-ai-assisted-proof-of-the-riemann-hypothesis/">Anthropic mathematician claims AI - assisted proof of the Riemann ...</a></li>
<li><a href="https://www.scientificamerican.com/article/the-ai-riemann-hypothesis-proof-is-almost-certainly-true-independent-mathematicians-attest/">The AI Riemann hypothesis proof is almost... | Scientific American</a></li>
<li><a href="https://github.com/CocoSgt/riemann-hypothesis-lean">GitHub - CocoSgt/ riemann - hypothesis - lean : Mirror of Levent...</a></li>

</ul>
</details>

**标签**: `#formal-verification`, `#Lean`, `#Riemann-Hypothesis`, `#AI-assisted-mathematics`, `#proof-assistants`

---

<a id="item-tech-news-2"></a>
### [GPGME 双重释放漏洞披露，影响大量使用 GnuPG 的软件](https://lists.gnupg.org/pipermail/gnupg-announce/2026q4/000517.html) ⭐️ 8.0/10

GnuPG 项目披露了 GPGME 中的一个内存安全漏洞，所有通过共享库、DLL 或静态链接方式使用 2.3.0 之前版本 GPGME 的软件都受影响。该漏洞由 Johan Carlsson 发现，GitLab 于 2026-11-12 通知 GnuPG；双方原定 2026-11-25 协调披露，但因 GitLab 需要提前发布 Ruby2Shell 漏洞修复，GPGME 漏洞于 2026-11-20 提前披露。受影响软件的例子包括 Gpg4win、GnuPG Desktop、GnuPG VS-Desktop、大多数邮件客户端、许多 XMPP 客户端、Samba 和 Flatpak。GitLab 已发布 Omnibus 相关补丁。该漏洞被描述为双重释放（double free）问题；是否有可用的远程代码执行链尚未得到确认。

hackernews · gdgghhhhh · 11月21日 08:32 · [社区讨论](https://news.ycombinator.com/item?id=50587208)

**「背景」** GPGME 是 GnuPG 提供的加密库，被邮件客户端、Samba、Flatpak、GitLab 等大量软件以共享库、DLL 或静态链接方式集成，用于调用 OpenPGP 签名和加密功能。GnuPG 项目在 GitLab 于 2026-11-12 通报后，原定 2026-11-25 协调披露，但因 GitLab 需要提前披露 Ruby2Shell 漏洞，GPGME 漏洞也于 2026-11-20 提前公开。官方安全公告指出，所有 2.3.0 之前的 GPGME 版本都受影响，而 2.3.0 从未公开发布，首个修复版本是本周发布的 GPGME 2.3.1。

**「影响与应对」** 使用 GPGME 2.3.0 之前版本的应用——包括 Gpg4win、GnuPG Desktop、多数邮件客户端、许多 XMPP 客户端、Samba 和 Flatpak——需要升级或应用补丁。GitLab 因支持签名提交而尤其需要关注该路径上的代码执行风险，并已提供 Omnibus 相关补丁。不过，社区指出这是双重释放漏洞，而非已确认的 RCE 利用链，实际可利用性仍需以官方公告和发行版安全更新为准。

**「社区讨论」** 有评论者指出，从常规工具的输出看，Red Hat 似乎约 5 年前就修复过该问题，但上游漏掉了这一修复。也有人认为该漏洞对支持签名提交的 GitLab 尤其重要，因为若该路径可被利用实现代码执行，后果会很严重；但另一位评论者强调这是双重释放漏洞，而非已确认的 RCE 链，并质疑漏洞报告是否被夸大。还有评论者询问该问题是否位于 gpgme 中、是否不影响 apt 等工具，尚待确认。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://thehackernews.com/2026/11/gnupg-warns-critical-gpgme-flaw-could.html">GnuPG Warns Critical GPGME Flaw Could Expose App Data via...</a></li>
<li><a href="https://lists.gnupg.org/pipermail/gnupg-announce/2026q4/000517.html">[Announce] GnuPG Security Advisory for GPGME ...</a></li>
<li><a href="https://www.phoronix.com/news/GnuPG-GPGME-Critical">GnuPG&#x27;s GPGME Affected By Critical Security Bug In Turn... - Phoronix</a></li>
<li>RCE in Gnupg - Hacker News</li>

</ul>
</details>

**标签**: `#security`, `#vulnerability`, `#gpgme`, `#gnupg`, `#memory-safety`

---

<a id="item-tech-news-3"></a>
### [浙江大学在超导芯片上首次真机实现量子随机存储器](https://finance.sina.com.cn/stock/2026-11-21/doc-iniznhsk3530826.shtml) ⭐️ 8.0/10

浙江大学团队在自主制备的超导量子芯片「天目 2 号」上实现了量子随机存储器（QRAM）的真机运行，相关成果发表于《自然·物理》。该芯片成功运行了可调取 4 位和 8 位数据的原型，准确率分别为 80.9% 和 60.4%；与未优化方案相比，线路深度降低 30% 以上，并首次验证该架构具备局部抗噪特性。团队表示下一步将推进 QRAM 的规模化研究。

telegram · zaihuapd · 11月21日 08:31

**「背景」** 量子随机存储器（QRAM）是量子算法访问经典数据的关键架构组件，长期被视为量子计算实用化中的数据访问瓶颈之一。此前，浙江大学团队已在超导量子处理器上实验演示了基于 bucket-brigade 架构的 4 位和 8 位 QRAM，查询保真度分别约为 81% 和 60%，相关成果发表于《自然·物理》。本次报道进一步说明该工作在自主制备的「天目 2 号」超导芯片上完成，并报告了线路深度降低 30% 以上和局部抗噪特性。

**「对量子计算研究与应用的影响」** 对量子计算研究而言，这一结果把 QRAM 从理论架构推进到可运行的超导硬件原型：4 位和 8 位数据调取准确率分别为 80.9% 和 60.4%，线路深度较未优化方案降低 30% 以上，并验证了局部抗噪特性。QRAM 被视为许多依赖高效加载经典数据的量子算法获得加速的前提，因此该原型为后续算法验证和架构优化提供了实验平台。不过，当前原型规模仍小、准确率有限，距离支撑大规模量子算法所需的容错、大容量 QRAM 还有明显差距；团队下一步将推进 QRAM 的规模化研究。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://thequbitreport.com/hardware/2026/06/06/zhejiang-university-achieves-breakthrough-with-worlds-first-superconducting-qram-prototype/">Zhejiang University Achieves Breakthrough with World’s First ...</a></li>
<li><a href="https://thequantuminsider.com/2026/06/05/chinese-scientists-demonstrate-quantum-random-access-memory-architecture-aimed-at-solving-data-bottleneck/">Chinese Scientists Demonstrate Quantum Random Access Memory ...</a></li>
<li><a href="https://arxiv.org/abs/2305.10310">[2305.10310] QRAM: A Survey and Critique - arXiv.org A bucket-brigade quantum random access memory - Nature QRAM: A Survey and Critique – Quantum Chinese Scientists Demonstrate Quantum Random Access Memory ... Intro to quantum random access memory (QRAM) | PennyLane Demos A new architecture for Quantum RAM | PME | The University of ...</a></li>
<li><a href="https://www.nature.com/articles/s41567-026-03218-2">A bucket-brigade quantum random access memory - Nature</a></li>

</ul>
</details>

**标签**: `#quantum computing`, `#QRAM`, `#superconducting qubits`, `#hardware`, `#research`

---

<a id="item-tech-news-4"></a>
### [显示器以太网直通导致下载速度下降约 75% 的排查](https://blog.tymscar.com/posts/studiodisplayethernet/) ⭐️ 7.0/10

作者发现，把以太网线经由显示器直通再连接到笔记本后，下载速度被削减了约 75%。排查显示，显示器引入的额外延迟使笔记本来不及及时确认数据包，导致 USB 网络适配器上的缓冲区被填满并开始丢包。更换一个对确认频率要求更低的适配器后，问题得到解决。

hackernews · soheilpro · 11月21日 10:36 · [社区讨论](https://news.ycombinator.com/item?id=50587875)

**「背景知识」** 许多显示器和扩展坞会把网口通过 USB 网络适配器转发给电脑，而不是提供原生 PCIe 网卡。这类链路的吞吐量不仅取决于标称带宽，还受延迟、确认包节奏和适配器缓冲区大小影响；一旦发送端等待确认过久或缓冲区溢出，TCP 就会因丢包而降速。

**「实际影响」** 使用显示器、扩展坞或 USB 网卡直通网络的用户，如果遇到速度远低于宽带标称值的问题，应把中间链路延迟和适配器缓冲行为纳入排查范围。可行的做法包括更换确认机制更高效的 USB 网络适配器，或尽量让电脑直接连接网线。

**「社区讨论」** 有评论认为标题中的“显示器”并非关键，更准确的说法是 USB 网络链路拖慢了速度；也有读者补充解释，认为文章价值在于揭示了 USB 集线器和适配器极不透明的行为。另有用户表示自己在 MacBook 加雷雳扩展坞环境下遇到类似问题，长期反复出现，直到启用流控后才缓解。

**标签**: `#networking`, `#ethernet`, `#usb`, `#packet-loss`, `#hardware-debugging`

---

<a id="item-tech-news-5"></a>
### [Muru：mod\_wsgi 作者用 Rust 打造的 Python ASGI/WSGI 服务器](https://simonwillison.net/2026/Nov/21/muru/) ⭐️ 7.0/10

Graham Dumpleton 推出了新项目 Muru，这是一个由 AI 辅助开发的 Rust 服务器，目标是在开发和生产环境中运行 Python 的 ASGI 与 WSGI 应用。Dumpleton 是 20 年前 mod\_wsgi 的作者，Muru 试图重新设计 Python Web 应用的生产部署方式。项目已公开 GitHub 仓库，并在过去三周内连续发布了 17 篇详细开发日志，涵盖 worker 架构、WSGI 与 ASGI 共存、HTTPS 开发支持、Kubernetes 集成、缩容到零、金丝雀发布和页面级调试工具栏等主题。目前它仍处于早期公开开发阶段，尚未被描述为成熟或经过大规模生产验证的稳定版本。

rss · Simon Willison · 11月21日 23:56

**「背景」** Muru 的核心定位是同时服务 Python 生态中两代应用接口：WSGI 是长期用于同步 Web 应用的标准，而 ASGI 则支持异步请求和 WebSocket 等长连接。作者 Graham Dumpleton 此前创建的 mod\_wsgi 已有约 20 年历史，长期被用于在生产环境运行 WSGI 应用，因此 Muru 可视为他基于 Rust 和 AI 辅助开发经验，对“如何更好地运行 Python Web 应用”的延续性尝试。

**「对 Python Web 部署的实际影响」** 对运行 Python Web 应用的团队来说，Muru 提供了一个把 WSGI 与 ASGI 放进同一运行时的选项：同一 worker 内可同时处理传统 WSGI 请求和 WebSocket/ASGI 请求，并宣称支持零停机发布、流量管理与按 worker 指标扩缩容。对现有项目，这意味着可以尝试在不重写应用的情况下为旧 WSGI 服务增加 WebSocket、gRPC 或 ASGI 能力，或用同一套进程模型管理两类应用；但该项目刚公开约三周，主要证据仍是作者的开发日志和项目文档，尚缺乏大规模生产案例和独立基准，建议先在开发、预发或非关键服务中评估兼容性与稳定性，再决定是否用于核心生产流量。

**「社区讨论」** 目前没有可用的社区评论。Simon Willison 在原文中特别推荐了 Dumpleton 的《AI as a lifestyle choice》一文，其中 Dumpleton 表示 AI 虽然承担了大量表面工作，但判断哪些部分还不够好仍依赖他 20 年使用 mod\_wsgi 积累的经验，并计划持续打磨 Muru 直到自己和用户都能信任它。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://grahamdumpleton.me/posts/2026/11/muru-wsgi-and-asgi-together/">Muru: WSGI and ASGI together - Graham Dumpleton</a></li>
<li><a href="https://github.com/GrahamDumpleton/muru">GitHub - GrahamDumpleton/muru: Routing edge, control plane ...</a></li>
<li><a href="https://docs.muruhq.dev/">Muru ¶</a></li>
<li><a href="https://grahamdumpleton.me/posts/2026/11/muru-wsgi-and-asgi-together/">Muru: WSGI and ASGI together - Graham Dumpleton</a></li>
<li><a href="https://github.com/GrahamDumpleton/muru">GitHub - GrahamDumpleton/muru: Routing edge, control plane ...</a></li>

</ul>
</details>

**标签**: `#Python`, `#ASGI`, `#WSGI`, `#Rust`, `#web servers`

---

<a id="item-tech-news-6"></a>
### [微软推出 RDMA over USB4 预览，多台 Windows PC 可合跑一个本地 AI 模型](https://videocardz.com/newz/microsoft-brings-rdma-over-usb4-to-windows-allowing-multiple-pcs-to-run-one-local-ai-model) ⭐️ 7.0/10

微软发布了 Windows 的 RDMA over USB4 开发者预览，让多台 PC 通过普通 USB4 连接共享内存和 GPU 算力，从而共同运行同一个本地 AI 大模型，而不需要专用网卡或交换机。演示中，三台搭载 AMD Ryzen AI Max+ 395 的机器以 4-bit 量化运行 Qwen3-235B-A22B，速度约为 18.5 token/s。该功能将通过 Windows Insider 推送，目前属于开发者预览阶段。

telegram · zaihuapd · 11月21日 06:13

**「背景：RDMA 与 USB4 的结合」** RDMA（远程直接内存访问）是一种让一台计算机直接读写另一台计算机内存、绕过操作系统网络栈的技术，传统上依赖专用网卡和交换机，常用于数据中心高性能计算。USB4 则是消费级 PC 常见的接口协议，支持高带宽和设备菊花链连接。微软此次将两者结合，使多台 Windows PC 能通过普通 USB4 线缆组成计算集群，共享内存与 GPU 算力，而无需购置专用网络设备。

**「对本地 AI 部署和开发者的意义」** 对需要在本地运行大模型的开发者和用户来说，这项预览提供了一条不依赖专用网络硬件的横向扩展路径：可以用多台带 USB4 的 Windows PC 组合内存与 GPU 算力，运行单机装不下或跑不动的模型。由于它仍处于开发者预览并通过 Windows Insider 推送，实际部署前需要关注驱动、系统版本和硬件兼容性要求。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.techpowerup.com/355062/microsoft-brings-rdma-over-usb4-to-windows-11-for-daisy-chained-pcs">Microsoft Brings RDMA over USB 4 to Windows 11... | TechPowerUp</a></li>
<li><a href="https://www.goha.ru/microsoft-dobavila-v-windows-11-tehnologiyu-rdma-po-usb4-dlya-obedineniya-neskolkih-pk-v-edinyj-lokalnyj-ii-klaster-lWoPRN">Microsoft добавила в Windows 11 технологию RDMA по USB 4 для...</a></li>

</ul>
</details>

**标签**: `#AI infrastructure`, `#RDMA`, `#USB4`, `#distributed inference`, `#Windows`

---

<a id="item-tech-news-7"></a>
### [特斯拉海外推送 FSD v15，新增 Reality View 可视化](https://x.com/Tesla/status/2124222447855743019) ⭐️ 7.0/10

特斯拉已在海外开始推送 FSD v15。官方称该版本将安全关键场景的处理能力提升至 25 倍，并新增“Tesla Reality View”可视化界面，把摄像头画面与 FSD 行驶规划叠加显示在车机屏幕上，支持全屏、地图或分屏视图以及安静模式。导航可将转弯等信息叠加显示，转向灯提示音更轻柔并逐渐减弱；更新还优化了坑洼、碎片等路况下的行驶体验，以及学校区域和恶劣天气下的速度控制。这些能力提升目前来自特斯拉官方说明，尚无独立测试结果佐证。

telegram · zaihuapd · 11月22日 00:03

**「背景」** FSD（Full Self-Driving）是特斯拉面向其车辆的高级驾驶辅助软件，此前版本已能在部分道路条件下执行导航、变道等辅助驾驶任务，但官方能力声明通常仍需结合实际道路表现评估。此次 v15 的变化是在该既有系统上叠加新的可视化界面，并针对安全关键场景、学校区域与恶劣天气速度控制、坑洼和碎片路况等具体弱点进行更新。

**「用户影响」** 对已开通 FSD 的海外车主而言，v15 主要改变的是信息呈现和特定场景下的驾驶策略：Reality View 让驾驶员能直接看到系统对摄像头画面的理解与规划，便于判断何时需要接管；学校区域、恶劣天气和坑洼路况的速度与行驶控制调整，则可能影响日常通勤中的乘坐体验。由于“25 倍安全关键场景提升”是厂商声明，车主仍应按监管和特斯拉指引保持对系统的监督，不应将其理解为已获独立验证的安全指标。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://electrek.co/2026/11/21/tesla-fsd-v15-rollout-25x-safety-reality-view/">Tesla launches FSD v15, targets its biggest weaknesses, from ...</a></li>
<li><a href="https://www.teslarati.com/tesla-full-self-driving-v15-rollout-begins-full-release-notes-improvements/">Tesla Full Self-Driving v15 rollout begins: full release ...</a></li>

</ul>
</details>

**标签**: `#Tesla`, `#autonomous driving`, `#FSD`, `#AI systems`, `#automotive software`

---

## 科技博客

<a id="item-tech-blog-1"></a>
### [写好代码的关键：避免灾难性失误](https://seangoedecke.com/to-code-well-avoid-blunders/) ⭐️ 7.0/10

rss · Sean Goedecke · 11月22日 00:00

**「背景」** Sean Goedecke 认为，很多工程师把编程想象成靠“灵光一现”取胜的活动，以为好代码来自漂亮的新抽象或聪明技巧。但他认为在大型商业代码库中，真正决定代码质量的是能否持续避免灾难性失误，而不是追求 brilliance。

**「方案」** 作者用国际象棋和网球作类比：如果棋手不送子、网球手稳定回球，即使没有惊人操作也能击败大多数对手。编程之所以类似，是因为代码库很难建立“ durable winning advantage ”——篮球里 99:1 领先时一次失误只变成 99:4，但代码库里一次 blunder 就可能把优雅系统变成混乱系统。他列举的典型失误包括：为同一任务引入并行系统、给关键数据引入第二个 source of truth、把安全的同步操作改成脆弱的异步操作、增加隐蔽故障点，以及复杂化关键接口。其中最大的问题是 inconsistency 和 unnecessary requirements：不一致会破坏信任，工程师不能再假设代码按合理方式工作，而必须寻找意外；不必要的需求则很“粘”，写需求时有上下文判断必要性，后来者若不愿花时间调查就只能假设它必要，于是需求长期残留。更糟的是需求之间会组合，如果系统已支持 X，每个新功能都要考虑与 X 的交互，这种组合爆炸正是大型代码库难维护的原因。因此作者建议写代码时优先找到任务在现有代码库中最自然的落点，并把任务裁剪成最小必要需求；当开始想“我可以用这个聪明模式实现”时，反而要警惕自己正在偏离主线。

**「启示」** 作者的核心结论是：优秀的编程工作不需要特别聪明，而需要关注细节，并持续保持一致性、砍掉不必要需求，从而避免让代码库恶化的灾难性失误。

**标签**: `#software-engineering`, `#code-quality`, `#technical-debt`, `#large-codebases`, `#engineering-practices`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [特朗普称仍支持商务部长卢特尼克，并希望黄仁勋道歉后回归](https://www.reuters.com/world/us/trump-says-he-still-backs-lutnick-urges-nvidias-huang-apologize-2026-11-20/) ⭐️ 7.0/10

据路透社报道，美国总统特朗普 11 月 20 日表示，他仍支持商务部长卢特尼克，称其“做得很好”，尽管外界质疑其处理英伟达对华芯片销售的方式。特朗普还称，希望已辞职的英伟达 CEO 黄仁勋“郑重道歉后回归”，并透露已与中国国家主席习近平谈及此事；但这一说法与财长贝森特所称通话未涉及黄仁勋相矛盾。

telegram · zaihuapd · 11月21日 05:03

**「背景」** 此前，美国商务部在卢特尼克领导下负责审批英伟达等公司的对华芯片出口，而卢特尼克在确认听证会上曾承诺对相关技术销售采取强硬立场。据 Axios 报道，该部门今年 5 月批准了先进 AI 芯片对华销售；随后英伟达 CEO 黄仁勋离职，引发外界对商务部处理方式的质疑。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.nytimes.com/2026/11/12/us/politics/lutnick-nvidia-commerce-china-chips.html">Howard Lutnick Took Softer Line on Nvidia as Calls for Tougher...</a></li>
<li><a href="https://www.axios.com/2026/11/10/lutnick-nvidia-jensen-huang-china-memo">The agency cleared advanced AI chip sales in May.</a></li>

</ul>
</details>

**标签**: `#US-China tech policy`, `#Nvidia`, `#chip export controls`, `#Trump administration`, `#corporate leadership`

---