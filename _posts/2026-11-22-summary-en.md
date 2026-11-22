---
layout: default
title: "Horizon Summary: 2026-11-22 (EN)"
date: 2026-11-22
lang: en
---

> From 24 items, 9 important content pieces were selected

---

**Technology News**
1. [Lean verification of the Riemann Hypothesis](#item-tech-news-1) ⭐️ 9.0/10
2. [GPGME double-free vulnerability prompts patches across GnuPG-dependent software](#item-tech-news-2) ⭐️ 8.0/10
3. [Zhejiang University reports first real-machine QRAM on superconducting chip](#item-tech-news-3) ⭐️ 8.0/10
4. [Monitor Ethernet passthrough cut download speed by 75%](#item-tech-news-4) ⭐️ 7.0/10
5. [Muru: A Rust Server for Python ASGI and WSGI Apps](#item-tech-news-5) ⭐️ 7.0/10
6. [Microsoft previews RDMA over USB4 to run one AI model across multiple Windows PCs](#item-tech-news-6) ⭐️ 7.0/10
7. [Tesla begins rolling out FSD v15 with Reality View and safety-scenario claims](#item-tech-news-7) ⭐️ 7.0/10

**Technology Blog**
1. [To Code Well, Avoid Blunders](#item-tech-blog-1) ⭐️ 7.0/10

**Financial News**
1. [Trump backs Commerce Secretary Lutnick, says Nvidia&\#x27;s Huang should apologize before returning](#item-finance-news-1) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Lean verification of the Riemann Hypothesis](https://leanprover-community.github.io/blog/posts/riemann-hypothesis/) ⭐️ 9.0/10

On November 20, 2026, Levent Alpöge released a Lean formalization of a proof of the Riemann Hypothesis, with a codebase of about 17 million lines. On November 21, the Lean FRO and Mathlib Initiative issued a joint statement certifying that both the proposition and the proof are correct: the community confirmed that the stated proposition matches Mathlib&\#x27;s RiemannHypothesis, the codebase compiles without errors, and multiple independent proof checkers validated the proof. The formalization reportedly involved large-scale AI assistance with human expert oversight, though the certification statement itself rests on the machine-checked artifacts rather than on that process.

hackernews · g-b-r · Nov 21, 14:36 · [Discussion](https://news.ycombinator.com/item?id=50589618)

**「Background」** The Riemann Hypothesis is a long-standing conjecture in number theory about the locations of the nontrivial zeros of the Riemann zeta function, and a proof would have major consequences for the distribution of prime numbers. Lean is an interactive proof assistant whose kernel checks formal proofs, and Mathlib is its large community-maintained mathematical library; a formalization is considered verified when it compiles against the relevant Lean/Mathlib definitions and is accepted by the proof checker. Levent Alpöge is a number theorist who has worked at Anthropic, and the current announcement follows earlier efforts to formalize major mathematical results in Lean, making the scale and AI-assisted nature of this 17-million-line development notable.

**「Impact」** For mathematicians and users of proof assistants, the immediate consequence is that the Riemann Hypothesis can now be treated as a machine-checked theorem in the Lean/Mathlib ecosystem, provided the Lean FRO and Mathlib Initiative&\#x27;s reported checks hold up under continued community scrutiny. The result also demonstrates that AI-assisted formalization at very large scale can produce complete, kernel-checked proofs, which may lower the barrier for formalizing other major results. However, the practical caveat is trust in the toolchain: independent checkers reduce but do not eliminate the risk of a shared kernel bug, so users should treat the proof&\#x27;s validity as tied to the specific Lean version, Mathlib state, and verification setup used.

**「Community discussion」** Commenters argued that a false proof is now very unlikely because several independent kernels with their own consistency proofs would all need to share a bug affecting both the consistency arguments and this proof, though one commenter cautioned that independent checkers are not perfectly independent and cited a past fake Collatz refutation that passed one checker. Others emphasized that the result matters beyond the Riemann Hypothesis itself—formalizing a large portion of modern mathematics—and that Levent Alpöge deserves substantial credit for directing the AI-assisted effort.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Levent_Alp%C3%B6ge">Levent Alpöge - Wikipedia</a></li>
<li><a href="https://leanprover-community.github.io/blog/posts/riemann-hypothesis/">Lean verification of the Riemann Hypothesis | Lean community blog</a></li>
<li><a href="https://www.newscientist.com/article/2600134-anthropic-mathematician-claims-ai-assisted-proof-of-the-riemann-hypothesis/">Anthropic mathematician claims AI - assisted proof of the Riemann ...</a></li>
<li><a href="https://github.com/CocoSgt/riemann-hypothesis-lean">GitHub - CocoSgt/ riemann - hypothesis - lean : Mirror of Levent...</a></li>

</ul>
</details>

**Tags**: `#formal-verification`, `#Lean`, `#Riemann-Hypothesis`, `#AI-assisted-mathematics`, `#proof-assistants`

---

<a id="item-tech-news-2"></a>
### [GPGME double-free vulnerability prompts patches across GnuPG-dependent software](https://lists.gnupg.org/pipermail/gnupg-announce/2026q4/000517.html) ⭐️ 8.0/10

A vulnerability in GPGME, the library that lets applications use GnuPG, was disclosed on 2026-11-20 after being discovered by Johan Carlsson and reported to the GnuPG project through GitLab on 2026-11-12. According to the announcement quoted in the discussion, all software using a GPGME version prior to 2.3.0—whether linked as a shared library, DLL, or statically—is affected, with examples including Gpg4win, GnuPG Desktop, GnuPG VS-Desktop, many mail and XMPP clients, Samba, and Flatpak. The disclosure was originally planned for 2026-11-25 but was moved up because GitLab had to disclose the related Ruby2Shell bug earlier. Commenters describe the flaw as a double-free memory-safety bug rather than a confirmed remote code execution chain, so the practical exploitability remains uncertain despite the headline framing.

hackernews · gdgghhhhh · Nov 21, 08:32 · [Discussion](https://news.ycombinator.com/item?id=50587208)

**「Background」** GPGME is the GnuPG Made Easy library that applications use to integrate GnuPG cryptographic operations, and the advisory says every version before 2.3.0 is affected when linked as a shared library, DLL, or statically. The flaw is a double-free memory-safety bug that GnuPG says can be triggered through signed data to exfiltrate application data, while warning that remote code execution cannot be ruled out. GPGME 2.3.1 is the first fixed release; 2.3.0 was never publicly available.

**「Impact」** Applications that link GPGME before version 2.3.0—shared, DLL, or statically linked—need to update or rebuild against the patched release. The affected list includes Gpg4win, GnuPG Desktop, GnuPG VS-Desktop, many mail and XMPP clients, Samba, and Flatpak. For GitLab in particular, a commenter notes that signed-commit verification is a sensitive path, so code execution there would be especially serious; however, another commenter argues the bug is a double free rather than a demonstrated RCE chain, so operators should treat exploitability as unconfirmed and follow vendor advisories and patches.

**「Community discussion」** Commenters pushed back on the RCE framing: mik1998 argued it is a double-free bug, not an RCE chain, and asked whether vulnerability reports are being overstated. Others focused on remediation and scope—uptrails noted Red Hat appears to have fixed the issue in its packages about five years ago even though upstream missed it, wannabe44 asked whether the flaw is confined to GPGME rather than tools such as apt, and dehrmann argued the incident shows the risks of writing C/C++ without Rust-level memory-safety tooling.

<details><summary>References</summary>
<ul>
<li><a href="https://thehackernews.com/2026/11/gnupg-warns-critical-gpgme-flaw-could.html">GnuPG Warns Critical GPGME Flaw Could Expose App Data via...</a></li>
<li><a href="https://lists.gnupg.org/pipermail/gnupg-announce/2026q4/000517.html">[Announce] GnuPG Security Advisory for GPGME ...</a></li>
<li><a href="https://www.phoronix.com/news/GnuPG-GPGME-Critical">GnuPG&#x27;s GPGME Affected By Critical Security Bug In Turn... - Phoronix</a></li>
<li>RCE in Gnupg - Hacker News</li>

</ul>
</details>

**Tags**: `#security`, `#vulnerability`, `#gpgme`, `#gnupg`, `#memory-safety`

---

<a id="item-tech-news-3"></a>
### [Zhejiang University reports first real-machine QRAM on superconducting chip](https://finance.sina.com.cn/stock/2026-11-21/doc-iniznhsk3530826.shtml) ⭐️ 8.0/10

Zhejiang University says it has implemented quantum random-access memory \(QRAM\) on its self-fabricated superconducting quantum chip, Tianmu-2, and published the result in Nature Physics. The team ran prototypes that can retrieve 4-bit and 8-bit data, with reported accuracies of 80.9% and 60.4%, respectively. The implementation reportedly reduced circuit depth by more than 30% compared with an unoptimized scheme and demonstrated local noise resilience. The team says its next step is scaling QRAM research, but the reported devices remain small prototypes with modest accuracies.

telegram · zaihuapd · Nov 21, 08:31

**「Why QRAM matters」** Quantum random-access memory \(QRAM\) is a proposed architectural component that would let a quantum processor retrieve classical data in superposition, addressing a data-access bottleneck for algorithms that promise speedups in areas such as search and simulation. Earlier reports in June 2026 described Zhejiang University&\#x27;s experimental QRAM demonstration on a superconducting processor using a bucket-brigade architecture, with four-bit and eight-bit query fidelities of roughly 81% and 60%. The current report places that work on the university&\#x27;s Tianmu-2 superconducting chip and adds reported reductions in circuit depth and local noise resilience.

**「Impact」** For quantum-computing researchers and algorithm developers, the demonstration moves QRAM from a largely theoretical assumption to a small-scale hardware capability: Zhejiang University says its Tianmu-2 superconducting chip ran 4-bit and 8-bit QRAM prototypes with 80.9% and 60.4% accuracy, over 30% lower circuit depth than an unoptimized scheme, and local noise resilience. The practical consequence is that algorithms that depend on fast quantum access to classical data now have an experimental reference point on superconducting hardware, though the small memory sizes and modest fidelities mean it is not yet a deployable memory subsystem. Teams working on QRAM should watch the promised scale-up work and compare their architectures against this superconducting implementation.

<details><summary>References</summary>
<ul>
<li><a href="https://thequbitreport.com/hardware/2026/06/06/zhejiang-university-achieves-breakthrough-with-worlds-first-superconducting-qram-prototype/">Zhejiang University Achieves Breakthrough with World’s First ...</a></li>
<li><a href="https://thequantuminsider.com/2026/06/05/chinese-scientists-demonstrate-quantum-random-access-memory-architecture-aimed-at-solving-data-bottleneck/">Chinese Scientists Demonstrate Quantum Random Access Memory ...</a></li>
<li><a href="https://arxiv.org/abs/2305.10310">[2305.10310] QRAM: A Survey and Critique - arXiv.org A bucket-brigade quantum random access memory - Nature QRAM: A Survey and Critique – Quantum Chinese Scientists Demonstrate Quantum Random Access Memory ... Intro to quantum random access memory (QRAM) | PennyLane Demos A new architecture for Quantum RAM | PME | The University of ...</a></li>
<li><a href="https://www.nature.com/articles/s41567-026-03218-2">A bucket-brigade quantum random access memory - Nature</a></li>

</ul>
</details>

**Tags**: `#quantum computing`, `#QRAM`, `#superconducting qubits`, `#hardware`, `#research`

---

<a id="item-tech-news-4"></a>
### [Monitor Ethernet passthrough cut download speed by 75%](https://blog.tymscar.com/posts/studiodisplayethernet/) ⭐️ 7.0/10

A detailed debugging investigation found that routing Ethernet through a monitor&\#x27;s built-in network passthrough cut the author&\#x27;s download speed by about 75%. The extra latency added by the monitor caused a USB network adapter&\#x27;s buffer to overflow, leading to dropped packets and severely reduced throughput. The problem was fixed by switching to a different USB Ethernet adapter that required less frequent packet acknowledgment. The case is a specific hardware and networking troubleshooting result rather than a broad product or industry change.

hackernews · soheilpro · Nov 21, 10:36 · [Discussion](https://news.ycombinator.com/item?id=50587875)

**「Why this can happen」** Some monitors with Ethernet ports act as pass-through devices: a laptop connects by USB or Thunderbolt, and the monitor forwards network traffic to a wired LAN. In this setup, the added forwarding latency can interact badly with a USB adapter&\#x27;s buffering and acknowledgment behavior, causing packet loss even though the link itself appears to work.

**「Practical takeaway」** Users with slow wired speeds through a monitor, dock, or USB hub should consider the passthrough path and adapter as possible causes, not just the ISP or cable. As the article found, trying a different USB Ethernet adapter with different acknowledgment behavior can resolve severe packet loss.

**「Community response」** Commenters largely found the diagnosis credible: one summarized that the monitor&\#x27;s added latency prevented the laptop from acknowledging packets quickly enough, filling the Ethernet adapter&\#x27;s buffer and causing drops, while another argued the headline could equally be &quot;my USB network switch was cutting my download speed&quot; because the monitor itself was somewhat incidental. Others shared similar opaque hardware interactions, including a Ghostty terminal and Baldur&\#x27;s Gate 3 shader-compilation throttling case and a MacBook plus Thunderbolt dock issue that persisted for over a year.

**Tags**: `#networking`, `#ethernet`, `#usb`, `#packet-loss`, `#hardware-debugging`

---

<a id="item-tech-news-5"></a>
### [Muru: A Rust Server for Python ASGI and WSGI Apps](https://simonwillison.net/2026/Nov/21/muru/) ⭐️ 7.0/10

Graham Dumpleton, the creator of mod\_wsgi, has introduced Muru, a new AI-assisted server written in Rust for running Python ASGI and WSGI applications in both development and production. The project is being developed in the open, with Dumpleton publishing a detailed series of posts over the past three weeks covering its architecture, worker model, HTTPS support, Kubernetes integration, scaling behavior, and built-in developer tooling such as a per-page toolbar with tracing. The project is early-stage and actively evolving, with the design informed by two decades of experience maintaining mod\_wsgi.

rss · Simon Willison · Nov 21, 23:56

**「Background」** Muru builds on Graham Dumpleton&\#x27;s long history with Python web deployment: he created mod\_wsgi about 20 years ago, a widely used Apache module for hosting WSGI applications. The new project extends that problem to modern Python apps by supporting both WSGI and ASGI in the same Rust-based server, including handing requests to ASGI in the same worker so features such as WebSockets can be added alongside existing WSGI applications.

**「Practical impact for Python web developers」** For teams running Python web applications, Muru could consolidate several deployment concerns—WSGI and ASGI serving, WebSocket support, zero-downtime releases, traffic management, and Python-aware process management—into a single Rust-based edge and runtime. The most immediately actionable capability is running WSGI and ASGI in the same worker, which lets developers add WebSockets or other ASGI endpoints to an existing WSGI application without replacing the whole stack. Teams evaluating it should treat it as a new project from a highly experienced author rather than a proven production standard, and follow its public build log and repository for maturity, compatibility, and operational guidance.

**「Community Discussion」** No community comments are available for this item. Simon Willison&\#x27;s post highlights the unusually detailed public development log, particularly Dumpleton&\#x27;s reflection that AI assists with much of the implementation work but that deciding what is &quot;good enough&quot; still depends on his long experience with mod\_wsgi.

<details><summary>References</summary>
<ul>
<li><a href="https://grahamdumpleton.me/posts/2026/11/muru-wsgi-and-asgi-together/">Muru: WSGI and ASGI together - Graham Dumpleton</a></li>
<li><a href="https://docs.muruhq.dev/">Muru ¶</a></li>
<li><a href="https://grahamdumpleton.me/posts/2026/11/muru-wsgi-and-asgi-together/">Muru: WSGI and ASGI together - Graham Dumpleton</a></li>
<li><a href="https://github.com/GrahamDumpleton/muru">GitHub - GrahamDumpleton/muru: Routing edge, control plane ...</a></li>

</ul>
</details>

**Tags**: `#Python`, `#ASGI`, `#WSGI`, `#Rust`, `#web servers`

---

<a id="item-tech-news-6"></a>
### [Microsoft previews RDMA over USB4 to run one AI model across multiple Windows PCs](https://videocardz.com/newz/microsoft-brings-rdma-over-usb4-to-windows-allowing-multiple-pcs-to-run-one-local-ai-model) ⭐️ 7.0/10

Microsoft has released a developer preview of RDMA over USB4 for Windows, allowing multiple PCs to share memory and GPU compute over ordinary USB4 connections to run the same local AI model without dedicated network cards or switches. The reported demonstration used three AMD Ryzen AI Max+ 395 machines to run Qwen3-235B-A22B at 4-bit quantization, reaching about 18.5 tokens per second. Microsoft plans to distribute the capability through Windows Insider, so it is a preview rather than a generally available Windows feature.

telegram · zaihuapd · Nov 21, 06:13

**「Background」** RDMA \(Remote Direct Memory Access\) lets one computer read or write another machine&\#x27;s memory with minimal CPU involvement, and it is normally used over specialized high-speed networking hardware. Microsoft has now brought RDMA to Windows over USB4, so ordinary USB4 cables can link PCs into a shared compute cluster for large workloads such as local AI inference. The reported demonstration used three AMD Ryzen AI Max+ 395 systems running Qwen3-235B-A22B at 4-bit quantization at about 18.5 tokens per second, with the feature arriving through Windows Insider.

**「Why it matters」** For developers and small organizations, RDMA over USB4 could make it possible to combine the memory and GPU resources of several consumer or workstation PCs for local AI inference, potentially avoiding specialized interconnect hardware. The practical near-term step is to watch for the Windows Insider rollout and evaluate whether the preview&\#x27;s supported hardware and performance meet specific workloads.

<details><summary>References</summary>
<ul>
<li><a href="https://www.techpowerup.com/355062/microsoft-brings-rdma-over-usb4-to-windows-11-for-daisy-chained-pcs">Microsoft Brings RDMA over USB 4 to Windows 11... | TechPowerUp</a></li>
<li><a href="https://www.goha.ru/microsoft-dobavila-v-windows-11-tehnologiyu-rdma-po-usb4-dlya-obedineniya-neskolkih-pk-v-edinyj-lokalnyj-ii-klaster-lWoPRN">Microsoft добавила в Windows 11 технологию RDMA по USB 4 для...</a></li>

</ul>
</details>

**Tags**: `#AI infrastructure`, `#RDMA`, `#USB4`, `#distributed inference`, `#Windows`

---

<a id="item-tech-news-7"></a>
### [Tesla begins rolling out FSD v15 with Reality View and safety-scenario claims](https://x.com/Tesla/status/2124222447855743019) ⭐️ 7.0/10

Tesla has started pushing Full Self-Driving \(FSD\) v15 to vehicles overseas. The update introduces a &quot;Tesla Reality View&quot; visualization that overlays camera imagery and FSD driving plans on the in-car screen, with full-screen, map, split-screen, and quiet-mode display options. Tesla says v15 improves handling of safety-critical driving scenarios by 25x, a vendor claim not accompanied by independent validation in the source. The release also adds turn information overlays in navigation, softer and gradually fading turn-signal sounds, and tuning for potholes, debris, school zones, and bad-weather speed control.

telegram · zaihuapd · Nov 22, 00:03

**「Background」** Tesla&\#x27;s Full Self-Driving \(FSD\) is its advanced driver-assistance software suite, and major version updates have historically been used to introduce new driving-policy behavior and interface features. FSD v15 follows that pattern: the rollout adds Tesla Reality View, a live on-screen visualization that overlays camera imagery with FSD&\#x27;s planned path, and Tesla says it improves handling of safety-critical cases by 25x. These claims come from Tesla&\#x27;s own release notes and coverage of the rollout, not from independent testing.

**「Why it matters」** For FSD-equipped Tesla owners in the initial overseas rollout, v15 changes how the system presents its perception and planned path, which can make it easier to see what the software is doing while driving. The claimed 25x safety-critical improvement should be treated as a manufacturer statement until independently measured. Availability and feature behavior may vary by region and vehicle, so owners should check their in-car update prompts rather than assume immediate access.

<details><summary>References</summary>
<ul>
<li><a href="https://electrek.co/2026/11/21/tesla-fsd-v15-rollout-25x-safety-reality-view/">Tesla launches FSD v15, targets its biggest weaknesses, from ...</a></li>
<li><a href="https://www.teslarati.com/tesla-full-self-driving-v15-rollout-begins-full-release-notes-improvements/">Tesla Full Self-Driving v15 rollout begins: full release ...</a></li>

</ul>
</details>

**Tags**: `#Tesla`, `#autonomous driving`, `#FSD`, `#AI systems`, `#automotive software`

---

## Technology Blog

<a id="item-tech-blog-1"></a>
### [To Code Well, Avoid Blunders](https://seangoedecke.com/to-code-well-avoid-blunders/) ⭐️ 7.0/10

rss · Sean Goedecke · Nov 22, 00:00

**「Background」** Sean Goedecke argues that many engineers misunderstand what makes programming skill: they imagine it comes from brilliant insights or beautiful abstractions, when in large commercial codebases the decisive factor is avoiding catastrophic mistakes. His concern is that cleverness can distract from the real work of keeping an existing system coherent.

**「Solution」** Goedecke compares good programming to chess or tennis: consistently not hanging pieces or missing easy returns beats occasional brilliance. Programming is especially unforgiving because, unlike a basketball lead, a codebase does not retain a durable winning advantage—one blunder can turn an elegant system into a janky one. His examples include adding a parallel system for the same task, creating a second source of truth, converting a safe synchronous operation into a delicate asynchronous one, adding subtle failure modes, and complicating a key interface. The cardinal sins are inconsistency and unnecessary requirements. Inconsistency is dangerous because it breaks engineers’ trust: they can no longer assume code behaves the sensible way and must hunt for surprises. Unnecessary requirements are sticky because later engineers usually cannot tell they are unnecessary without costly research, and they combine dangerously: once a system supports X, every new feature must consider its interaction with X, producing the combinatorial complexity that makes large codebases hard. His practical discipline is to place each task where it fits most naturally in the current codebase and trim it to the smallest viable set of requirements. If you start thinking about a clever pattern or “extra credit” feature, he treats that as a warning sign of distraction. He notes this applies whether writing code yourself or driving an AI agent, and adds that current coding agents are about as good as humans at consistency but worse at avoiding unnecessary requirements. He also scopes the claim: this is advice for large-team commercial software, not necessarily every kind of programming.

**「Takeaway」** Great programming work depends less on cleverness than on attention to detail: maintain consistency, avoid unnecessary requirements, and don’t blunder.

**Tags**: `#software-engineering`, `#code-quality`, `#technical-debt`, `#large-codebases`, `#engineering-practices`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Trump backs Commerce Secretary Lutnick, says Nvidia&\#x27;s Huang should apologize before returning](https://www.reuters.com/world/us/trump-says-he-still-backs-lutnick-urges-nvidias-huang-apologize-2026-11-20/) ⭐️ 7.0/10

On November 20, President Trump said he still supports Commerce Secretary Lutnick, saying he is doing a good job despite questions over the handling of chip sales to China, and said he wants resigned Nvidia CEO Jensen Huang to return after a serious apology. Trump also said he had discussed the matter with Chinese President Xi Jinping, contradicting Treasury Secretary Bessent&\#x27;s account that the call did not involve Huang.

telegram · zaihuapd · Nov 21, 05:03

**「Background」** The dispute centers on the Commerce Department&\#x27;s oversight of Nvidia&\#x27;s advanced AI chip sales to China, an issue that had already drawn criticism of Secretary Howard Lutnick after his department cleared such sales in May 2026 despite earlier promises to take a tough line on technology exports to China. Jensen Huang&\#x27;s resignation from Nvidia and Trump&\#x27;s claim that he discussed the matter with Chinese President Xi Jinping are the immediate events behind the latest statements.

**「Impact」** The dispute touches U.S. export-control policy for advanced AI chips to China and the leadership of Nvidia, so conflicting accounts from senior U.S. officials add uncertainty for the company and for U.S.-China technology policy.

<details><summary>References</summary>
<ul>
<li><a href="https://www.nytimes.com/2026/11/12/us/politics/lutnick-nvidia-commerce-china-chips.html">Howard Lutnick Took Softer Line on Nvidia as Calls for Tougher...</a></li>
<li><a href="https://www.axios.com/2026/11/10/lutnick-nvidia-jensen-huang-china-memo">The agency cleared advanced AI chip sales in May.</a></li>

</ul>
</details>

**Tags**: `#US-China tech policy`, `#Nvidia`, `#chip export controls`, `#Trump administration`, `#corporate leadership`

---