<h1 align="center">Awesome Agentic On-Policy Distillation</h1>

<p align="center">Papers, benchmarks, datasets and codebases for <b>Agentic OPD / OPSD</b> —<br>organized by language, multimodal, video, audio and Agentic Generative Systems.</p>

<p align="center">
  <a href="https://yongtang2025.github.io/Awesome-Agentic-OPD/"><img src="https://img.shields.io/badge/Interactive_reader-EN_%2F_%E4%B8%AD%E6%96%87-1f6feb?style=flat-square" alt="Interactive reader"></a>
  <img src="https://img.shields.io/badge/papers-42-4E6813?style=flat-square" alt="papers">
  <img src="https://img.shields.io/badge/with_code-9-2E86C1?style=flat-square" alt="with code">
  <img src="https://img.shields.io/badge/updated-2026.10.22-purple?style=flat-square" alt="updated">
</p>

<p align="center">
  <a href="#llm-agentic-opd">LLM (15)</a> · <a href="#multimodal-agentic-opd">Multimodal (14)</a> · <a href="#video-agentic-opd">Video (5)</a> · <a href="#audio-agentic-opd">Audio (7)</a> · <a href="#ags-opd">AGS (1)</a>
</p>

> **On-policy distillation (OPD)** — the student learns from *its own* rollouts `y ~ π_student(·|x)`, while a teacher scores or corrects those student-generated samples. **OPSD** is the self-distillation case: the teacher is the same model, given privileged information.

Search, filter and read a four-point summary of every paper in the **[interactive reader](https://yongtang2025.github.io/Awesome-Agentic-OPD/)** ([mirror](https://htmlpreview.github.io/?https://github.com/yongtang2025/Awesome-Agentic-OPD/blob/main/index.html)).

## 🔥 Most starred

| # | Paper | Domain | Affiliation | Code |
| :-: | :-- | :-- | :-- | :-: |
| 1 | [UI-MOPD: Multi-Platform On-Policy Distillation for Unified GUI Agents](https://arxiv.org/abs/2607.04425) | Multimodal | Tsinghua University | [⭐ 61](https://github.com/EliSpectre/UI-MOPD) |
| 2 | [OPOD: On-Policy Omni Distillation](https://arxiv.org/abs/2607.20918) | Audio | Renmin University of China; Tencent | [⭐ 58](https://github.com/VincentZhao2002/OPOD) |
| 3 | [Refined Policy Distillation: From VLA Generalists to RL Experts](https://arxiv.org/abs/2503.05833) | Multimodal | University of Technology Nuremberg | [⭐ 24](https://github.com/Refined-Policy-Distillation/RPD) |
| 4 | [Reward-Tilted On-Policy Distillation for Acoustic Grounding in Audio-Language Models](https://arxiv.org/abs/2609.28778) | Audio | NEC Laboratories America; University of Connecticut | [⭐ 1](https://github.com/KaiyangLi1992/RT-OPD) |

<h2 id="llm-agentic-opd">🧠 LLM Agentic OPD</h2>

On-policy distillation for language-model agents, tool use, planning, memory and long-horizon reasoning. **15 papers**, 4 with code.

| Paper | Affiliation | Date | Code | Cited |
| :-- | :-- | :-: | :-: | :-: |
| [ToolOPD: Credit-Aware On-Policy Distillation for Tool-Use Agents](https://arxiv.org/abs/2610.25693) | Northeastern University; Honor Device Co., Ltd. | 2026-10-19 | [Code](https://github.com/MagicAgent-Search/ToolOPD) | — |
| [Beyond the Teacher: Understanding and Preserving Distillation Overshoot in Agentic On-Policy Distillation](https://arxiv.org/abs/2610.25034) | University of Southern California; University of Florida; Emory University; University of Alabama; University of Maryland; Amazon AGI; Boston University; The Ohio State University; National Taiwan University | 2026-10-18 | [Code](https://github.com/Jike338/SPOD) | — |
| [GraphOPD: Graph-Augmented On-Policy Distillation for LLM Agents](https://arxiv.org/abs/2610.08959) | University of Science and Technology of China; Xiaohongshu; HKUST (GZ) | 2026-10-06 | [Code](https://github.com/BoHan-LIN04/GraphOPD) | — |
| [DivOPD: Spread Wide, Look Close for Asynchronous On-Policy Distillation of Multi-turn Agents](https://arxiv.org/abs/2609.34838) | University of Chicago; Meituan; University of Chinese Academy of Sciences; HKUST (GZ) | 2026-09-28 | [Code](https://github.com/HanyangWang0418-oss/DivOPD) | — |

<details>
<summary>📄 11 more without public code (newest first)</summary>

| Paper | Affiliation | Date | Code | Cited |
| :-- | :-- | :-: | :-: | :-: |
| [Capable Teacher, Myopic Scorer: Reward-Free Teacher Repair for Agentic On-Policy Distillation](https://arxiv.org/abs/2610.28586) | NVIDIA | 2026-10-20 | — | — |
| [MultiAgent-OPD: End-to-End Training of Hierarchical Multi-Agent Systems with On-Policy Distillation](https://arxiv.org/abs/2610.23234) | Alibaba Group; Zhejiang University | 2026-10-16 | — | — |
| [Information-Gain Calibrated On-Policy Distillation for Deep Search Agents](https://arxiv.org/abs/2610.20664) | The Chinese University of Hong Kong, Shenzhen; Renmin University of China; Beijing University of Posts and Telecommunications; BAAI | 2026-10-14 | — | — |
| [ActionOPD: Distilling Decisions, Not Tokens](https://arxiv.org/abs/2610.19820) | Tsinghua University | 2026-10-14 | — | — |
| [State-OPD: State-Grounded On-Policy Distillation for Multi-Turn Agents](https://arxiv.org/abs/2610.13238) | Alibaba Group; Tsinghua University; Shanghai Jiao Tong University; USTC | 2026-10-09 | — | — |
| [Stochastic Teacher Intervention for Agentic On-Policy Distillation](https://arxiv.org/abs/2610.10878) | Monash University; The Hong Kong Polytechnic University; Zhongguancun Laboratory | 2026-10-07 | — | — |
| [SCAD: Structured Credit Assignment and Distillation for Long-Horizon Agents](https://arxiv.org/abs/2610.03372) | Beijing University of Posts and Telecommunications; Tsinghua University; Nanyang Technological University | 2026-10-02 | — | — |
| [Harness-Aware Distillation for Small Language Model Agents](https://arxiv.org/abs/2610.02858) | KAIST AI; Independent researcher | 2026-10-02 | — | — |
| [PivotOPD: Learning to Recover from Pivotal Mistakes in Multi-Turn Agents](https://arxiv.org/abs/2609.40285) | Princeton University; NVIDIA; University of Maryland | 2026-09-30 | — | — |
| [Act First, Reason Later: Accelerating On-Policy Distillation for Multi-Turn Agents via Reference-Conditioned Inverse Dynamics](https://arxiv.org/abs/2609.36608) | Southern University of Science and Technology; Zhongguancun Academy; Hong Kong Polytechnic University; DeepCybo; Nanyang Technological University | 2026-09-29 | — | — |
| [Teacher–Student Gaps Are Not Enough: Outcome-Guided On-Policy Distillation for Multi-Turn Autonomous Agents](https://arxiv.org/abs/2609.35319) | Alibaba; Peking University; University of Chinese Academy of Sciences; Shanghai Jiao Tong University | 2026-09-28 | — | — |

</details>

<h2 id="multimodal-agentic-opd">🧩 Multimodal Agentic OPD</h2>

Agentic on-policy distillation for vision-language and other multimodal agents that perceive, reason and act. **14 papers**, 3 with code.

| Paper | Affiliation | Date | Code | Cited |
| :-- | :-- | :-: | :-: | :-: |
| [UI-MOPD: Multi-Platform On-Policy Distillation for Unified GUI Agents](https://arxiv.org/abs/2607.04425) | Tsinghua University | 2026-07-05 | [⭐ 61](https://github.com/EliSpectre/UI-MOPD) | 6 |
| [Refined Policy Distillation: From VLA Generalists to RL Experts](https://arxiv.org/abs/2503.05833) | University of Technology Nuremberg | 2025-03-06 | [⭐ 24](https://github.com/Refined-Policy-Distillation/RPD) | 32 |
| [VISTA: Internalizing Collective Visual Experience via On-Policy Distillation for Active Multimodal Agents](https://arxiv.org/abs/2609.38086) | Tsinghua University | 2026-09-29 | [Code](https://github.com/jiangz20/VISTA) | — |

<details>
<summary>📄 11 more without public code (newest first)</summary>

| Paper | Affiliation | Date | Code | Cited |
| :-- | :-- | :-: | :-: | :-: |
| [MMSearch-OPD: Easy Made Hard, Hard Made Learnable for Long-Horizon Multimodal Search Agents](https://arxiv.org/abs/2610.22240) | Peking University; HKUST (GZ); Tsinghua University; The University of Hong Kong; Zhejiang University; Huawei Cloud | 2026-10-15 | — | — |
| [Multi-Teacher On-Policy Distillation for Flow-Based Vision-Language-Action Models](https://arxiv.org/abs/2610.21522) | Huawei Technologies; Tsinghua University | 2026-10-15 | — | — |
| [ECHOES: Seeing Beyond the Current Image via Recursive History Compression and Privileged On-Policy Distillation](https://arxiv.org/abs/2610.22408) | Tsinghua University; StepFun; Nanyang Technological University; Leapmotor; Honor | 2026-10-14 | — | — |
| [JoyInside-VLM-Agent: Product-Conditioned Multimodal Policy Learning for Embodied Agents](https://arxiv.org/abs/2610.12957) | JD.COM | 2026-10-09 | — | — |
| [FastOPD: On-Policy Distillation for Lightweight VLA Deployment](https://arxiv.org/abs/2610.02832) | KAIST; Sungkyunkwan University | 2026-10-02 | — | — |
| [PIVOT: Pivot-Aware On Policy Self Distillation for Multi-Turn VLM Agents](https://arxiv.org/abs/2609.35303) | HKUST (GZ); IDEA; The Hong Kong Polytechnic University; Nanyang Technological University; Tsinghua University | 2026-09-28 | — | 0 |
| [WAM-OPD: Sharpening World Action Models via On-Policy Distillation](https://arxiv.org/abs/2609.34250) | USTC; Zhejiang University; Shandong Normal University; Tencent Hunyuan3D | 2026-09-28 | — | 2 |
| [Test-Time Self-Evolving GUI Visual Grounding via Reflection-Guided On-Policy Self-Distillation](https://arxiv.org/abs/2608.11191) | Nanjing University of Science and Technology | 2026-08-11 | — | 2 |
| [SOPD-SocialNav: Selective On-Policy Distillation for Vision-Language Social Navigation](https://arxiv.org/abs/2607.19850) | Hokkaido University | 2026-07-22 | — | 0 |
| [Learn where to Click from Yourself: On-Policy Self-Distillation for GUI Grounding](https://arxiv.org/abs/2605.00642) | IIE, CAS | 2026-05-01 | — | 12 |
| [VLA-OPD: Bridging Offline SFT and Online RL for Vision-Language-Action Models via On-Policy Distillation](https://arxiv.org/abs/2603.26666) | HKUST (GZ) | 2026-03-27 | — | 14 |

</details>

<h2 id="video-agentic-opd">🎬 Video Agentic OPD</h2>

On-policy distillation for agents that understand, retrieve, reason over or interact with video. **5 papers**, 0 with code.

<details>
<summary>📄 5 more without public code (newest first)</summary>

| Paper | Affiliation | Date | Code | Cited |
| :-- | :-- | :-: | :-: | :-: |
| [OWLET: On-Policy Weighted Learning via Evidence Transfer for Video Large Language Model Post-Training](https://arxiv.org/abs/2610.13272) | USTC; Shanghai AI Laboratory; Tsinghua University | 2026-10-09 | — | — |
| [Video-MOPD: Multi-Teacher On-Policy Distillation for Video Understanding](https://arxiv.org/abs/2609.09300) | Tongji University | 2026-09-08 | — | 1 |
| [Video-OPSD: Exploiting Privileged Visual Evidence for On-Policy Self-Distillation in Video Large Language Models](https://arxiv.org/abs/2608.27065) | Nanyang Technological University; The Chinese University of Hong Kong | 2026-08-27 | — | 5 |
| [Where to Look Matters: On-Policy Self-Distillation for Long-Video Understanding](https://arxiv.org/abs/2608.25356) | University of Maryland | 2026-08-26 | — | 6 |
| [StreamOPD: A Post-Training Recipe with Spatio-Temporal Cue Gating for Streaming Video Understanding](https://arxiv.org/abs/2608.16320) | Tsinghua University | 2026-08-17 | — | 2 |

</details>

<h2 id="audio-agentic-opd">🔊 Audio Agentic OPD</h2>

On-policy distillation for speech, audio-language and voice-interaction agents. **7 papers**, 2 with code.

| Paper | Affiliation | Date | Code | Cited |
| :-- | :-- | :-: | :-: | :-: |
| [OPOD: On-Policy Omni Distillation](https://arxiv.org/abs/2607.20918) | Renmin University of China; Tencent | 2026-07-23 | [⭐ 58](https://github.com/VincentZhao2002/OPOD) | 1 |
| [Reward-Tilted On-Policy Distillation for Acoustic Grounding in Audio-Language Models](https://arxiv.org/abs/2609.28778) | NEC Laboratories America; University of Connecticut | 2026-09-23 | [⭐ 1](https://github.com/KaiyangLi1992/RT-OPD) | 0 |

<details>
<summary>📄 5 more without public code (newest first)</summary>

| Paper | Affiliation | Date | Code | Cited |
| :-- | :-- | :-: | :-: | :-: |
| [TS-OPD: Reconciling ASR and QA in Speech Language Models via Task-Specific On-Policy Distillation](https://arxiv.org/abs/2609.29464) | Nankai University; China Telecom Artificial Intelligence Technology Co. | 2026-09-24 | — | 0 |
| [X$^3$-OPD: Distilling Reasoning into Large Audio-Language Models via On-Policy Alignment](https://arxiv.org/abs/2607.21550) | Tencent Hunyuan; Zhejiang University | 2026-07-23 | — | 4 |
| [OmniOPSD: Rationale-Privileged On-Policy Self-Distillation for Affective Computing](https://arxiv.org/abs/2606.15920) | Shenzhen University; Tsinghua University; Shanghai Jiao Tong University; USTC; Shenzhen Technology University; Tongji University; Huawei | 2026-06-14 | — | 6 |
| [X-OPD: Cross-Modal On-Policy Distillation for Capability Alignment in Speech LLMs](https://arxiv.org/abs/2603.24596) | Tencent Hunyuan; Zhejiang University | 2026-03-06 | — | 17 |
| [CORD: Bridging the Audio-Text Reasoning Gap via Weighted On-policy Cross-modal Distillation](https://arxiv.org/abs/2601.16547) | Baidu; Tsinghua University; Inner Mongolia University | 2026-01-23 | — | 11 |

</details>

<h2 id="ags-opd">🎨 Agentic Generative Systems (AGS) OPD</h2>

On-policy distillation for Agentic Generative Systems that plan toward goals, execute generation tools and refine outputs from feedback; generic iterative diffusion distillation is excluded. **1 paper**, 0 with code.

<details>
<summary>📄 1 more without public code (newest first)</summary>

| Paper | Affiliation | Date | Code | Cited |
| :-- | :-- | :-: | :-: | :-: |
| [GenEvolve: Self-Evolving Image Generation Agents via Tool-Orchestrated Visual Experience Distillation](https://arxiv.org/abs/2605.21605) | HKUST (GZ); Meituan; HKUST; National University of Singapore | 2026-05-20 | — | 20 |

</details>

## Contributing

Add an entry to [`papers.json`](papers.json) and open a PR. `README.md` and `index.html` are generated by [`scripts/update_stats.py`](scripts/update_stats.py), so please do not edit them by hand. Stars come from the GitHub API and citations from Semantic Scholar, refreshed daily by [a GitHub Action](.github/workflows/refresh.yml) (last run: 2026-10-22 03:19 UTC).

## Acknowledgments

The initial layout is adapted from [README-Reference.md](README-Reference.md). Summaries are paraphrased from abstracts and may contain errors — the papers are the reference.

## License

[CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/) — public-domain dedication.
