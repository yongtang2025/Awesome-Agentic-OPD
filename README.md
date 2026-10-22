<h1 align="center">Awesome Agentic On-Policy Distillation</h1>

<p align="center">Papers, benchmarks, datasets and codebases for <b>Agentic OPD / OPSD</b> —<br>organized by language, multimodal, embodied, video, audio and Agentic Generative Systems.</p>

<p align="center">
  <a href="https://yongtang2025.github.io/Awesome-Agentic-OPD/"><img src="https://img.shields.io/badge/Interactive_reader-EN_%2F_%E4%B8%AD%E6%96%87-1f6feb?style=flat-square" alt="Interactive reader"></a>
  <img src="https://img.shields.io/badge/papers-38-4E6813?style=flat-square" alt="papers">
  <img src="https://img.shields.io/badge/with_code-8-2E86C1?style=flat-square" alt="with code">
  <img src="https://img.shields.io/badge/updated-2026.10.22-purple?style=flat-square" alt="updated">
</p>

<p align="center">
  <a href="#llm-agentic-opd">LLM (16)</a> · <a href="#multimodal-agentic-opd">Multimodal (9)</a> · <a href="#embodied-agentic-opd">Embodied (12)</a> · <a href="#video-agentic-opd">Video (0)</a> · <a href="#audio-agentic-opd">Audio (0)</a> · <a href="#ags-opd">AGS (1)</a>
</p>

> **On-policy distillation (OPD)** — the student learns from *its own* rollouts `y ~ π_student(·|x)`, while a teacher scores or corrects those student-generated samples. **OPSD** is the self-distillation case: the teacher is the same model, given privileged information.

### Inclusion criteria

This collection covers **on-policy distillation of interactive agent policies**. A paper must establish both:

1. **Agent interaction:** actions are executed through tools, software, a simulator, a robot, or another external interface; returned observations or execution feedback inform subsequent decisions.
2. **On-policy distillation:** an explicit teacher, self-teacher, or target-policy alignment objective trains the agent on student-generated actions, responses, action-flow states, or student-visited interaction states.

Text decoding alone, fixed-image/video/audio QA, static screenshot-to-coordinate grounding, teacher-provided crops, visual-token compression, and internal denoising steps do not establish an agent interaction loop. Successful-trajectory or teacher-continuation SFT alone is not sufficient evidence of OPD.

Interaction and on-policy sampling are checked separately: a policy may train on offline contexts and still execute a closed-loop agent task. Embodied action-flow OPD, replay-based methods, and teacher-free target-policy variants are identified in the interactive reader; they are not described as fresh environment rollouts during distillation.

See the [scope audit](ccfa-workfiles/checks/agentic-scope/scope-audit.md) for paper-level inclusion evidence and exclusions.

Search, filter and read a four-point summary of every paper in the **[interactive reader](https://yongtang2025.github.io/Awesome-Agentic-OPD/)** ([mirror](https://htmlpreview.github.io/?https://github.com/yongtang2025/Awesome-Agentic-OPD/blob/main/index.html)).

## 🔥 Most starred

| # | Paper | Domain | Affiliation | Code |
| :-: | :-- | :-- | :-- | :-: |
| 1 | [UI-MOPD: Multi-Platform On-Policy Distillation for Unified GUI Agents](https://arxiv.org/abs/2607.04425) | Multimodal | Tsinghua University | [⭐ 61](https://github.com/EliSpectre/UI-MOPD) |
| 2 | [Refined Policy Distillation: From VLA Generalists to RL Experts](https://arxiv.org/abs/2503.05833) | Embodied | University of Technology Nuremberg | [⭐ 24](https://github.com/Refined-Policy-Distillation/RPD) |

<h2 id="llm-agentic-opd">🧠 LLM Agentic OPD</h2>

On-policy distillation for language-model agents that execute tools or interact with external environments and use returned feedback. **16 papers**, 4 with code.

| Paper | Affiliation | Date | Code | Cited |
| :-- | :-- | :-: | :-: | :-: |
| [DivOPD: Spread Wide, Look Close for Asynchronous On-Policy Distillation of Multi-turn Agents](https://arxiv.org/abs/2609.34838) | University of Chicago; Meituan; University of Chinese Academy of Sciences; HKUST (GZ) | 2026-09-28 | [Code](https://github.com/HanyangWang0418-oss/DivOPD) | 1 |
| [ToolOPD: Credit-Aware On-Policy Distillation for Tool-Use Agents](https://arxiv.org/abs/2610.25693) | Northeastern University; Honor Device Co., Ltd. | 2026-10-19 | [Code](https://github.com/MagicAgent-Search/ToolOPD) | 0 |
| [Beyond the Teacher: Understanding and Preserving Distillation Overshoot in Agentic On-Policy Distillation](https://arxiv.org/abs/2610.25034) | University of Southern California; University of Florida; Emory University; University of Alabama; University of Maryland; Amazon AGI; Boston University; The Ohio State University; National Taiwan University | 2026-10-18 | [Code](https://github.com/Jike338/SPOD) | 0 |
| [GraphOPD: Graph-Augmented On-Policy Distillation for LLM Agents](https://arxiv.org/abs/2610.08959) | University of Science and Technology of China; Xiaohongshu; HKUST (GZ) | 2026-10-06 | [Code](https://github.com/BoHan-LIN04/GraphOPD) | 0 |

<details>
<summary>📄 12 more without public code (newest first)</summary>

| Paper | Affiliation | Date | Code | Cited |
| :-- | :-- | :-: | :-: | :-: |
| [Capable Teacher, Myopic Scorer: Reward-Free Teacher Repair for Agentic On-Policy Distillation](https://arxiv.org/abs/2610.28586) | NVIDIA | 2026-10-20 | — | 0 |
| [MultiAgent-OPD: End-to-End Training of Hierarchical Multi-Agent Systems with On-Policy Distillation](https://arxiv.org/abs/2610.23234) | Alibaba Group; Zhejiang University | 2026-10-16 | — | 0 |
| [ActionOPD: Distilling Decisions, Not Tokens](https://arxiv.org/abs/2610.19820) | Tsinghua University | 2026-10-14 | — | 0 |
| [State-OPD: State-Grounded On-Policy Distillation for Multi-Turn Agents](https://arxiv.org/abs/2610.13238) | Alibaba Group; Tsinghua University; Shanghai Jiao Tong University; USTC | 2026-10-09 | — | 0 |
| [Stochastic Teacher Intervention for Agentic On-Policy Distillation](https://arxiv.org/abs/2610.10878) | Monash University; The Hong Kong Polytechnic University; Zhongguancun Laboratory | 2026-10-07 | — | 0 |
| [SCAD: Structured Credit Assignment and Distillation for Long-Horizon Agents](https://arxiv.org/abs/2610.03372) | Beijing University of Posts and Telecommunications; Tsinghua University; Nanyang Technological University | 2026-10-02 | — | 0 |
| [Harness-Aware Distillation for Small Language Model Agents](https://arxiv.org/abs/2610.02858) | KAIST AI; Independent researcher | 2026-10-02 | — | 0 |
| [PivotOPD: Learning to Recover from Pivotal Mistakes in Multi-Turn Agents](https://arxiv.org/abs/2609.40285) | Princeton University; NVIDIA; University of Maryland | 2026-09-30 | — | 0 |
| [Act First, Reason Later: Accelerating On-Policy Distillation for Multi-Turn Agents via Reference-Conditioned Inverse Dynamics](https://arxiv.org/abs/2609.36608) | Southern University of Science and Technology; Zhongguancun Academy; Hong Kong Polytechnic University; DeepCybo; Nanyang Technological University | 2026-09-29 | — | 1 |
| [Teacher–Student Gaps Are Not Enough: Outcome-Guided On-Policy Distillation for Multi-Turn Autonomous Agents](https://arxiv.org/abs/2609.35319) | Alibaba; Peking University; University of Chinese Academy of Sciences; Shanghai Jiao Tong University | 2026-09-28 | — | 0 |
| [OPD-Evolver: Cultivating Holistic Agent Evolver via On-Policy Distillation](https://arxiv.org/abs/2606.17628) | — | 2026-06-16 | — | 2 |
| [SD-Search: On-Policy Hindsight Self-Distillation for Search-Augmented Reasoning](https://arxiv.org/abs/2605.18299) | Kuaishou | 2026-05-18 | — | 8 |

</details>

<h2 id="multimodal-agentic-opd">🧩 Multimodal Agentic OPD</h2>

On-policy distillation for multimodal agents with action-observation loops, including visual tools, multimodal search and multi-turn GUI interaction. **9 papers**, 3 with code.

| Paper | Affiliation | Date | Code | Cited |
| :-- | :-- | :-: | :-: | :-: |
| [UI-MOPD: Multi-Platform On-Policy Distillation for Unified GUI Agents](https://arxiv.org/abs/2607.04425) | Tsinghua University | 2026-07-05 | [⭐ 61](https://github.com/EliSpectre/UI-MOPD) | 6 |
| [VISTA: Internalizing Collective Visual Experience via On-Policy Distillation for Active Multimodal Agents](https://arxiv.org/abs/2609.38086) | Tsinghua University | 2026-09-29 | [Code](https://github.com/jiangz20/VISTA) | 0 |
| [On-Policy Visual Evidence Distillation](https://arxiv.org/abs/2609.36838) | — | 2026-09-29 | [Code](https://github.com/sylvain-wei/ReVuE) | 0 |

<details>
<summary>📄 6 more without public code (newest first)</summary>

| Paper | Affiliation | Date | Code | Cited |
| :-- | :-- | :-: | :-: | :-: |
| [MMSearch-OPD: Easy Made Hard, Hard Made Learnable for Long-Horizon Multimodal Search Agents](https://arxiv.org/abs/2610.22240) | Peking University; HKUST (GZ); Tsinghua University; The University of Hong Kong; Zhejiang University; Huawei Cloud | 2026-10-15 | — | 0 |
| [ECHOES: Seeing Beyond the Current Image via Recursive History Compression and Privileged On-Policy Distillation](https://arxiv.org/abs/2610.22408) | Tsinghua University; StepFun; Nanyang Technological University; Leapmotor; Honor | 2026-10-14 | — | 0 |
| [Information-Gain Calibrated On-Policy Distillation for Deep Search Agents](https://arxiv.org/abs/2610.20664) | The Chinese University of Hong Kong, Shenzhen; Renmin University of China; Beijing University of Posts and Telecommunications; BAAI | 2026-10-14 | — | 0 |
| [PIVOT: Pivot-Aware On Policy Self Distillation for Multi-Turn VLM Agents](https://arxiv.org/abs/2609.35303) | HKUST (GZ); IDEA; The Hong Kong Polytechnic University; Nanyang Technological University; Tsinghua University | 2026-09-28 | — | 0 |
| [Learn How to Act from Your Own Interactions: On-Policy Self-Distillation for GUI Agents](https://arxiv.org/abs/2609.27307) | Tsinghua University; Tencent; Chinese Academy of Sciences; Institute of Information Engineering; Nankai University | 2026-09-23 | — | 0 |
| [The Next Screenshot Knows: Gated Hindsight Distillation for Mobile GUI Agents](https://arxiv.org/abs/2608.06065) | University of Electronic Science and Technology of China | 2026-08-06 | — | 2 |

</details>

<h2 id="embodied-agentic-opd">🤖 Embodied Agentic OPD</h2>

On-policy distillation of policies evaluated through closed-loop robot, driving or embodied software execution, including VLA and world action models. **12 papers**, 1 with code.

| Paper | Affiliation | Date | Code | Cited |
| :-- | :-- | :-: | :-: | :-: |
| [Refined Policy Distillation: From VLA Generalists to RL Experts](https://arxiv.org/abs/2503.05833) | University of Technology Nuremberg | 2025-03-06 | [⭐ 24](https://github.com/Refined-Policy-Distillation/RPD) | 32 |

<details>
<summary>📄 11 more without public code (newest first)</summary>

| Paper | Affiliation | Date | Code | Cited |
| :-- | :-- | :-: | :-: | :-: |
| [Multi-Teacher On-Policy Distillation for Flow-Based Vision-Language-Action Models](https://arxiv.org/abs/2610.21522) | Huawei Technologies; Tsinghua University | 2026-10-15 | — | 0 |
| [Reflect-VLA: Internalizing Reflective Guidance via Dual-Path On-Policy Self-Distillation for Autonomous Driving](https://arxiv.org/abs/2610.13453) | Tsinghua University; University of Macau; University of Science and Technology of China; Beijing Jiaotong University | 2026-10-09 | — | 0 |
| [JoyInside-VLM-Agent: Product-Conditioned Multimodal Policy Learning for Embodied Agents](https://arxiv.org/abs/2610.12957) | JD.COM | 2026-10-09 | — | 0 |
| [FastOPD: On-Policy Distillation for Lightweight VLA Deployment](https://arxiv.org/abs/2610.02832) | KAIST; Sungkyunkwan University | 2026-10-02 | — | 0 |
| [DriftOPD: Sequence-Level Reverse-KL Distillation for One-Step VLA Policies](https://arxiv.org/abs/2610.00317) | Korea Advanced Institute of Science and Technology; Sungkyunkwan University | 2026-09-29 | — | 0 |
| [WAM-OPD: Sharpening World Action Models via On-Policy Distillation](https://arxiv.org/abs/2609.34250) | USTC; Zhejiang University; Shandong Normal University; Tencent Hunyuan3D | 2026-09-28 | — | 0 |
| [RE-0: Verified Recursive Improvement of Embodied Code-as-Policy Agents through Local On-Policy Distillation](https://arxiv.org/abs/2609.32416) | Jilin University; Dalian University of Technology | 2026-09-26 | — | 0 |
| [WAM-OPD: Joint Video-Action Supervision for World Action Model Post-Training with On-Policy Distillation](https://arxiv.org/abs/2608.22364) | University College London | 2026-08-23 | — | 2 |
| [FORCE: Efficient VLA Reinforcement Fine-Tuning via Value-Calibrated Warm-up and Self-Distillation](https://arxiv.org/abs/2606.26006) | Peking University; Beijing Academy of Artificial Intelligence; Institute of Physics | 2026-06-24 | — | 2 |
| [ROAD-VLA: Robust Online Adaptation via Self-Distillation for Vision-Language-Action Models](https://arxiv.org/abs/2606.25800) | UNSW Sydney; Deakin University; United States Air Force Research Laboratory | 2026-06-24 | — | 0 |
| [VLA-OPD: Bridging Offline SFT and Online RL for Vision-Language-Action Models via On-Policy Distillation](https://arxiv.org/abs/2603.26666) | HKUST (GZ) | 2026-03-27 | — | 14 |

</details>

<h2 id="video-agentic-opd">🎬 Video Agentic OPD</h2>

On-policy distillation for agents that act on video tools or video-based environments and use the resulting observations; static video QA and temporal grounding alone are excluded. **0 papers**, 0 with code.

No papers currently listed meet both the interaction and distillation criteria.

| Paper | Affiliation | Date | Code | Cited |
| :-- | :-- | :-: | :-: | :-: |

<h2 id="audio-agentic-opd">🔊 Audio Agentic OPD</h2>

On-policy distillation for agents in interactive speech, audio-tool or audio-environment tasks; fixed-input ASR, audio QA and affect recognition alone are excluded. **0 papers**, 0 with code.

No papers currently listed meet both the interaction and distillation criteria.

| Paper | Affiliation | Date | Code | Cited |
| :-- | :-- | :-: | :-: | :-: |

<h2 id="ags-opd">🎨 Agentic Generative Systems (AGS) OPD</h2>

On-policy distillation for Agentic Generative Systems that plan toward goals, execute generation tools and refine outputs from feedback; generic iterative diffusion distillation is excluded. **1 paper**, 0 with code.

<details>
<summary>📄 1 more without public code (newest first)</summary>

| Paper | Affiliation | Date | Code | Cited |
| :-- | :-- | :-: | :-: | :-: |
| [GenEvolve: Self-Evolving Image Generation Agents via Tool-Orchestrated Visual Experience Distillation](https://arxiv.org/abs/2605.21605) | HKUST (GZ); Meituan; HKUST; National University of Singapore | 2026-05-20 | — | 20 |

</details>

## Contributing

Add an entry to [`papers.json`](papers.json) and open a PR. `README.md` and `index.html` are generated by [`scripts/update_stats.py`](scripts/update_stats.py), so please do not edit them by hand. Stars come from the GitHub API and citations from Semantic Scholar, refreshed daily by [a GitHub Action](.github/workflows/refresh.yml) (last run: 2026-10-22 06:39 UTC).

## Acknowledgments

The initial layout is adapted from [README-Reference.md](README-Reference.md). Summaries are paraphrased from abstracts and may contain errors — the papers are the reference.

## License

[CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/) — public-domain dedication.
