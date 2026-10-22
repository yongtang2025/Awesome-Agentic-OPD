<h1 align="center">Awesome Agentic On-Policy Distillation</h1>

<p align="center">Papers, benchmarks, datasets and codebases for <b>Agentic OPD / OPSD</b> —<br>organized by language, multimodal, embodied, video, audio and Agentic Generative Systems.</p>

<p align="center">
  <a href="https://yongtang2025.github.io/Awesome-Agentic-OPD/"><img src="https://img.shields.io/badge/Interactive_reader-EN_%2F_%E4%B8%AD%E6%96%87-1f6feb?style=flat-square" alt="Interactive reader"></a>
  <img src="https://img.shields.io/badge/papers-102-4E6813?style=flat-square" alt="papers">
  <img src="https://img.shields.io/badge/with_code-17-2E86C1?style=flat-square" alt="with code">
  <img src="https://img.shields.io/badge/updated-2026.10.22-purple?style=flat-square" alt="updated">
</p>

<p align="center">
  <a href="#llm-agentic-opd">LLM (17)</a> · <a href="#multimodal-agentic-opd">Multimodal (51)</a> · <a href="#embodied-agentic-opd">Embodied (15)</a> · <a href="#video-agentic-opd">Video (10)</a> · <a href="#audio-agentic-opd">Audio (8)</a> · <a href="#ags-opd">AGS (1)</a>
</p>

> **On-policy distillation (OPD)** — the student learns from *its own* rollouts `y ~ π_student(·|x)`, while a teacher scores or corrects those student-generated samples. **OPSD** is the self-distillation case: the teacher is the same model, given privileged information.

Search, filter and read a four-point summary of every paper in the **[interactive reader](https://yongtang2025.github.io/Awesome-Agentic-OPD/)** ([mirror](https://htmlpreview.github.io/?https://github.com/yongtang2025/Awesome-Agentic-OPD/blob/main/index.html)).

## 🔥 Most starred

| # | Paper | Domain | Affiliation | Code |
| :-: | :-- | :-- | :-- | :-: |
| 1 | [UI-MOPD: Multi-Platform On-Policy Distillation for Unified GUI Agents](https://arxiv.org/abs/2607.04425) | Multimodal | Tsinghua University | [⭐ 61](https://github.com/EliSpectre/UI-MOPD) |
| 2 | [OPOD: On-Policy Omni Distillation](https://arxiv.org/abs/2607.20918) | Audio | Renmin University of China; Tencent | [⭐ 58](https://github.com/VincentZhao2002/OPOD) |
| 3 | [Refined Policy Distillation: From VLA Generalists to RL Experts](https://arxiv.org/abs/2503.05833) | Embodied | University of Technology Nuremberg | [⭐ 24](https://github.com/Refined-Policy-Distillation/RPD) |
| 4 | [Reward-Tilted On-Policy Distillation for Acoustic Grounding in Audio-Language Models](https://arxiv.org/abs/2609.28778) | Audio | NEC Laboratories America; University of Connecticut | [⭐ 1](https://github.com/KaiyangLi1992/RT-OPD) |

<h2 id="llm-agentic-opd">🧠 LLM Agentic OPD</h2>

On-policy distillation for language-model agents, tool use, planning, memory and long-horizon reasoning. **17 papers**, 4 with code.

| Paper | Affiliation | Date | Code | Cited |
| :-- | :-- | :-: | :-: | :-: |
| [DivOPD: Spread Wide, Look Close for Asynchronous On-Policy Distillation of Multi-turn Agents](https://arxiv.org/abs/2609.34838) | University of Chicago; Meituan; University of Chinese Academy of Sciences; HKUST (GZ) | 2026-09-28 | [Code](https://github.com/HanyangWang0418-oss/DivOPD) | 1 |
| [ToolOPD: Credit-Aware On-Policy Distillation for Tool-Use Agents](https://arxiv.org/abs/2610.25693) | Northeastern University; Honor Device Co., Ltd. | 2026-10-19 | [Code](https://github.com/MagicAgent-Search/ToolOPD) | 0 |
| [Beyond the Teacher: Understanding and Preserving Distillation Overshoot in Agentic On-Policy Distillation](https://arxiv.org/abs/2610.25034) | University of Southern California; University of Florida; Emory University; University of Alabama; University of Maryland; Amazon AGI; Boston University; The Ohio State University; National Taiwan University | 2026-10-18 | [Code](https://github.com/Jike338/SPOD) | 0 |
| [GraphOPD: Graph-Augmented On-Policy Distillation for LLM Agents](https://arxiv.org/abs/2610.08959) | University of Science and Technology of China; Xiaohongshu; HKUST (GZ) | 2026-10-06 | [Code](https://github.com/BoHan-LIN04/GraphOPD) | 0 |

<details>
<summary>📄 13 more without public code (newest first)</summary>

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
| [DeepSearch-World: Self-Distillation for Deep Search Agents in a Verifiable Environment](https://arxiv.org/abs/2607.07820) | HKUST Shenzhen Research Institute; HKUST (GZ) | 2026-07-08 | — | 4 |
| [OPD-Evolver: Cultivating Holistic Agent Evolver via On-Policy Distillation](https://arxiv.org/abs/2606.17628) | — | 2026-06-16 | — | 2 |
| [SD-Search: On-Policy Hindsight Self-Distillation for Search-Augmented Reasoning](https://arxiv.org/abs/2605.18299) | Kuaishou | 2026-05-18 | — | 8 |

</details>

<h2 id="multimodal-agentic-opd">🧩 Multimodal Agentic OPD</h2>

Agentic on-policy distillation for vision-language and other multimodal agents that perceive, reason and act. **51 papers**, 10 with code.

| Paper | Affiliation | Date | Code | Cited |
| :-- | :-- | :-: | :-: | :-: |
| [UI-MOPD: Multi-Platform On-Policy Distillation for Unified GUI Agents](https://arxiv.org/abs/2607.04425) | Tsinghua University | 2026-07-05 | [⭐ 61](https://github.com/EliSpectre/UI-MOPD) | 6 |
| [Beyond SFT-to-RL: Pre-alignment via Black-Box On-Policy Distillation for Multimodal RL](https://arxiv.org/abs/2604.28123) | HKUST (GZ); Nanyang Technological University; Tsinghua University; Renmin University of China; USTC; University of Chinese Academy of Sciences | 2026-04-30 | [Code](https://github.com/XIAO4579/PRISM) | 9 |
| [Stabilizing On-Policy Distillation for MLLM Reasoning with Global Normalization](https://arxiv.org/abs/2606.09091) | — | 2026-06-08 | [Code](https://github.com/OPPO-Mente-Lab/GNDPO) | 3 |
| [OPD-Aha: From Linguistic Momentum to Visual Reflection in Multimodal On-Policy Distillation](https://arxiv.org/abs/2609.16459) | Arizona State University; University of Virginia; Stevens Institute of Technology | 2026-09-15 | [Code](https://github.com/Echochef/OPD-Aha) | 1 |
| [Skill-Decoupled On-Policy Expert Distillation for Unified Vision-Language Models](https://arxiv.org/abs/2610.22217) | Northeastern University; Alibaba Group | 2026-10-15 | [Code](https://github.com/NEUIR/SCOPED) | 0 |
| [Where-OPD: Spatially Guided On-Policy Self-Distillation of MLLMs with Synthetic Scenes](https://arxiv.org/abs/2610.02117) | Centre National de la Recherche Scientifique; Sorbonne Université; Institut Systèmes Intelligents et de Robotique | 2026-10-01 | [Code](https://github.com/sirkosophia/Where-OPD) | 0 |
| [Distill the Visual Evidence, Not Just the Answer: Cross-World On-Policy Distillation for Vision-Language Models](https://arxiv.org/abs/2609.38777) | — | 2026-09-30 | [Code](https://github.com/baokou-fw2/CWAD) | 0 |
| [VISTA: Internalizing Collective Visual Experience via On-Policy Distillation for Active Multimodal Agents](https://arxiv.org/abs/2609.38086) | Tsinghua University | 2026-09-29 | [Code](https://github.com/jiangz20/VISTA) | 0 |
| [On-Policy Visual Evidence Distillation](https://arxiv.org/abs/2609.36838) | — | 2026-09-29 | [Code](https://github.com/sylvain-wei/ReVuE) | 0 |
| [ADOPD: Reference-Privileged On-Policy Distillation for MLLM-Based Industrial Anomaly Detection](https://arxiv.org/abs/2608.09789) | Zhejiang University | 2026-08-10 | [Code](https://github.com/withTai/ADOPD) | 0 |

<details>
<summary>📄 41 more without public code (newest first)</summary>

| Paper | Affiliation | Date | Code | Cited |
| :-- | :-- | :-: | :-: | :-: |
| [MMSearch-OPD: Easy Made Hard, Hard Made Learnable for Long-Horizon Multimodal Search Agents](https://arxiv.org/abs/2610.22240) | Peking University; HKUST (GZ); Tsinghua University; The University of Hong Kong; Zhejiang University; Huawei Cloud | 2026-10-15 | — | 0 |
| [ECHOES: Seeing Beyond the Current Image via Recursive History Compression and Privileged On-Policy Distillation](https://arxiv.org/abs/2610.22408) | Tsinghua University; StepFun; Nanyang Technological University; Leapmotor; Honor | 2026-10-14 | — | 0 |
| [Do As I Do, Not As I Say: On-Policy Distillation Inherits the Teacher in Vision-Language Models](https://arxiv.org/abs/2610.20989) | Georgia Institute of Technology | 2026-10-14 | — | 0 |
| [Information-Gain Calibrated On-Policy Distillation for Deep Search Agents](https://arxiv.org/abs/2610.20664) | The Chinese University of Hong Kong, Shenzhen; Renmin University of China; Beijing University of Posts and Telecommunications; BAAI | 2026-10-14 | — | 0 |
| [VC-OPD: Visual Counterfactual On-Policy Distillation for Grounded Vision-Language Reasoning](https://arxiv.org/abs/2610.14939) | Tianjin University | 2026-10-10 | — | 0 |
| [CV-OPD: Contrastive Vision On-policy Distillation](https://arxiv.org/abs/2610.13264) | Xiamen University; Shanxi Science and Technology Department | 2026-10-09 | — | 0 |
| [Is Better Teacher Supervision Enough? Unlocking Student-side Learning in Multimodal On-Policy Distillation](https://arxiv.org/abs/2609.39120) | Nanjing University; Fudan University; Nanjing University of Posts and Telecommunications | 2026-09-30 | — | 0 |
| [LEGO-OPD: Factorized Teacher Composition for Multimodal On-Policy Distillation](https://arxiv.org/abs/2610.00333) | Korea Advanced Institute of Science and Technology | 2026-09-29 | — | 0 |
| [PIVOT: Pivot-Aware On Policy Self Distillation for Multi-Turn VLM Agents](https://arxiv.org/abs/2609.35303) | HKUST (GZ); IDEA; The Hong Kong Polytechnic University; Nanyang Technological University; Tsinghua University | 2026-09-28 | — | 0 |
| [Evidence-Aligned Multimodal On-Policy Self-Distillation for Fine-Grained Visual Understanding](https://arxiv.org/abs/2609.34672) | Beihang University; Chinese Academy of Sciences; University of Chinese Academy of Sciences | 2026-09-28 | — | 0 |
| [SCOPD: Sparse-Context On-Policy Self-Distillation for Efficient Vision-Language Models](https://arxiv.org/abs/2609.34044) | University of Toronto; Vector Institute; Samsung; University of Waterloo; Stanford University; University of British Columbia | 2026-09-28 | — | 0 |
| [Fewer Tokens, More Self-Teaching: On-Policy Self-Distillation for Extreme Visual Token Reduction](https://arxiv.org/abs/2609.32353) | Shanghai Jiao Tong University; Xi'an Jiaotong University; University of Cambridge; Xidian University | 2026-09-26 | — | 0 |
| [Progressive-View On-Policy Distillation for Regional-to-Global Transfer in Multimodal LLMs](https://arxiv.org/abs/2609.32333) | Baidu | 2026-09-26 | — | 0 |
| [Learn How to Act from Your Own Interactions: On-Policy Self-Distillation for GUI Agents](https://arxiv.org/abs/2609.27307) | Tsinghua University; Tencent; Chinese Academy of Sciences; Institute of Information Engineering; Nankai University | 2026-09-23 | — | 0 |
| [BAS-OPD: Budget-Aware Selective On-Policy Self-Distillation for Fine-Grained Multimodal Perception](https://arxiv.org/abs/2609.25891) | University of Science and Technology of China; Chinese Academy of Sciences; University of California, Los Angeles | 2026-09-22 | — | 0 |
| [CA-OPD: Confidence-Aware On-Policy Distillation for Structured Visual Prediction](https://arxiv.org/abs/2609.02401) | Tianjin University; Shanghai Jiao Tong University; University of Science and Technology of China | 2026-09-02 | — | 2 |
| [Self-Supervised Visual On-Policy Distillation](https://arxiv.org/abs/2608.14144) | Johns Hopkins University; University of Oxford; Georgia Institute of Technology; University of California San Diego; University of Maryland | 2026-08-14 | — | 9 |
| [Test-Time Self-Evolving GUI Visual Grounding via Reflection-Guided On-Policy Self-Distillation](https://arxiv.org/abs/2608.11191) | Nanjing University of Science and Technology | 2026-08-11 | — | 2 |
| [SkillLens: Visual Skill Cards for Retrieval-Augmented GUI Action Prediction and On-Policy Distillation](https://arxiv.org/abs/2608.10775) | Peking University; ByteDance; Shanghai Jiao Tong University | 2026-08-11 | — | 3 |
| [The Next Screenshot Knows: Gated Hindsight Distillation for Mobile GUI Agents](https://arxiv.org/abs/2608.06065) | University of Electronic Science and Technology of China | 2026-08-06 | — | 2 |
| [OPD-V: Visual On-Policy Self-Distillation with Modality Balance](https://arxiv.org/abs/2608.05131) | National Sun Yat-sen University; Ludwig-Maximilians-Universität München; National University of Singapore | 2026-08-05 | — | 10 |
| [Distill What the Student Can See: Fisher-Projected On-Policy Distillation for Vision-Language Models](https://arxiv.org/abs/2608.01263) | Tianjin University | 2026-08-02 | — | 5 |
| [VAD: Attributing Visual Evidence for Target Reconstruction in Multimodal On-Policy Distillation](https://arxiv.org/abs/2607.28590) | Shanghai Jiao Tong University; Xiaohongshu; Chinese University of Hong Kong; Zhejiang University | 2026-07-30 | — | 8 |
| [OPLD: On-Policy Latent Distillation for Multimodal Reasoning](https://arxiv.org/abs/2607.28154) | — | 2026-07-30 | — | 0 |
| [RP-OPSD: Resolution-Privileged On-Policy Self-Distillation for Multimodal Large Language Models](https://arxiv.org/abs/2607.24447) | — | 2026-07-27 | — | 7 |
| [Visual Contrastive Self-Distillation](https://arxiv.org/abs/2607.21556) | University of Maryland; University of California San Diego; Duke University; Mohamed bin Zayed University of Artificial Intelligence | 2026-07-23 | — | 10 |
| [MOPDA: Mixed-Trajectory On-Policy Distillation for Language-Guided Industrial Anomaly Detection](https://arxiv.org/abs/2607.18850) | Tsinghua University; Guangdong Laboratory of Artificial Intelligence and Digital Economy; Shenzhen University | 2026-07-21 | — | 1 |
| [Med-OPD: Improving Medical Vision-Language Models via Evidence-Aware On-Policy Distillation](https://arxiv.org/abs/2607.16303) | National University of Singapore; University of Science and Technology of China | 2026-07-14 | — | 2 |
| [H-OPD: Confidence Aware Heterogeneous Multi-Teacher Multimodal On-policy Distillation](https://arxiv.org/abs/2607.02592) | Beijing University of Posts and Telecommunications; ByteDance | 2026-07-01 | — | 12 |
| [V-Zero: Answer-Label-Free On-Policy Distillation with Contrastive Evidence Gating for Fine-Grained Visual Reasoning](https://arxiv.org/abs/2606.25319) | Sichuan University; Xi'an Jiaotong University; China Telecom; Peking University | 2026-06-24 | — | 12 |
| [Seeing Before Reasoning: Decoupling Perception and Reasoning for Shortcut-Resilient Multimodal On-Policy Self-Distillation](https://arxiv.org/abs/2606.19120) | Shenyang Institute of Automation; Chinese Academy of Sciences; University of Chinese Academy of Sciences | 2026-06-17 | — | 5 |
| [Visual-OPSD: Cross-Modal On-Policy Self-Distillation for Efficient Unified Multimodal Reasoning](https://arxiv.org/abs/2606.18974) | Xi'an Jiaotong University; Sun Yat-sen University | 2026-06-17 | — | 17 |
| [Skill-Guided Continuation Distillation for GUI Agents](https://arxiv.org/abs/2606.18890) | University of Science and Technology Beijing; Nanyang Technological University; Tsinghua University | 2026-06-17 | — | 2 |
| [Trust the Right Teacher: Quality-Aware Self-Distillation for GUI Grounding](https://arxiv.org/abs/2606.18101) | University of Georgia; Tencent; Hong Kong Polytechnic University | 2026-06-16 | — | 4 |
| [Thinking Without Images: Internalizing Visual Manipulation with On-Policy Self-Distillation](https://arxiv.org/abs/2606.08719) | Peking University; Central South University; University of Science and Technology of China; Huawei | 2026-06-07 | — | 10 |
| [Teaching the Way, Not the Answer: Privileged Tutoring Distillation for Multimodal Policy Optimization](https://arxiv.org/abs/2606.07000) | Tianjin University; Beijing Institute of Technology; Singapore Management University; University of Chinese Academy of Sciences; Xiaomi | 2026-06-05 | — | 2 |
| [ViCuR: Visual Cues as Recoverable Privilege for Multimodal On-Policy Distillation](https://arxiv.org/abs/2606.05718) | Fudan University; Shanghai Artificial Intelligence Laboratory; Nanjing University | 2026-06-04 | — | 14 |
| [Decomposed On-Policy Distillation for Vision-Language Reasoning: Steering Gradients for Visual Grounding](https://arxiv.org/abs/2606.00564) | — | 2026-05-30 | — | 12 |
| [Visual-Advantage On-Policy Distillation for Vision-Language Models](https://arxiv.org/abs/2605.21924) | Institute of Automation; University of Chinese Academy of Sciences; National Sun Yat-sen University; Sun Yat-sen Memorial Hospital | 2026-05-21 | — | 28 |
| [Vision-OPD: Learning to See Fine Details for Multimodal LLMs via On-Policy Self-Distillation](https://arxiv.org/abs/2605.18740) | Chinese Academy of Sciences; Institute of Software; University of Chinese Academy of Sciences; Xiaohongshu | 2026-05-18 | — | 87 |
| [Learn where to Click from Yourself: On-Policy Self-Distillation for GUI Grounding](https://arxiv.org/abs/2605.00642) | IIE, CAS | 2026-05-01 | — | 12 |

</details>

<h2 id="embodied-agentic-opd">🤖 Embodied Agentic OPD</h2>

On-policy distillation for vision-language-action models, world action models, robot navigation and manipulation, autonomous driving, and embodied code-as-policy agents. **15 papers**, 1 with code.

| Paper | Affiliation | Date | Code | Cited |
| :-- | :-- | :-: | :-: | :-: |
| [Refined Policy Distillation: From VLA Generalists to RL Experts](https://arxiv.org/abs/2503.05833) | University of Technology Nuremberg | 2025-03-06 | [⭐ 24](https://github.com/Refined-Policy-Distillation/RPD) | 32 |

<details>
<summary>📄 14 more without public code (newest first)</summary>

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
| [SOPD-SocialNav: Selective On-Policy Distillation for Vision-Language Social Navigation](https://arxiv.org/abs/2607.19850) | Hokkaido University | 2026-07-22 | — | 0 |
| [FORCE: Efficient VLA Reinforcement Fine-Tuning via Value-Calibrated Warm-up and Self-Distillation](https://arxiv.org/abs/2606.26006) | Peking University; Beijing Academy of Artificial Intelligence; Institute of Physics | 2026-06-24 | — | 2 |
| [ROAD-VLA: Robust Online Adaptation via Self-Distillation for Vision-Language-Action Models](https://arxiv.org/abs/2606.25800) | UNSW Sydney; Deakin University; United States Air Force Research Laboratory | 2026-06-24 | — | 0 |
| [On-Policy Distillation of Language Models for Autonomous Vehicle Motion Planning](https://arxiv.org/abs/2604.07944) | — | 2026-04-09 | — | 1 |
| [SnapFlow: One-Step Action Generation for Flow-Matching VLAs via Progressive Self-Distillation](https://arxiv.org/abs/2604.05656) | Jilin University; Chongqing University; University of Liverpool | 2026-04-07 | — | 17 |
| [VLA-OPD: Bridging Offline SFT and Online RL for Vision-Language-Action Models via On-Policy Distillation](https://arxiv.org/abs/2603.26666) | HKUST (GZ) | 2026-03-27 | — | 14 |

</details>

<h2 id="video-agentic-opd">🎬 Video Agentic OPD</h2>

On-policy distillation for agents that understand, retrieve, reason over or interact with video. **10 papers**, 0 with code.

<details>
<summary>📄 10 more without public code (newest first)</summary>

| Paper | Affiliation | Date | Code | Cited |
| :-- | :-- | :-: | :-: | :-: |
| [OWLET: On-Policy Weighted Learning via Evidence Transfer for Video Large Language Model Post-Training](https://arxiv.org/abs/2610.13272) | USTC; Shanghai AI Laboratory; Tsinghua University | 2026-10-09 | — | 0 |
| [MeSD: Multi-Evidence Self-Distillation for VideoLLM](https://arxiv.org/abs/2610.06342) | Beijing Academy of Artificial Intelligence; University of Chinese Academy of Sciences; Zhejiang University; Beijing Jiaotong University; Beihang University | 2026-10-05 | — | 0 |
| [Frame Differential On-Policy Self-Distillation for Video Reasoning](https://arxiv.org/abs/2609.39021) | King Abdullah University of Science and Technology | 2026-09-30 | — | 0 |
| [Counterfactual Attention Policy Distillation for Temporal Video Grounding](https://arxiv.org/abs/2609.34581) | Xiamen University; Fudan University; Chinese University of Hong Kong; Chinese Academy of Sciences | 2026-09-28 | — | 0 |
| [Video-MOPD: Multi-Teacher On-Policy Distillation for Video Understanding](https://arxiv.org/abs/2609.09300) | Tongji University | 2026-09-08 | — | 1 |
| [Video-OPSD: Exploiting Privileged Visual Evidence for On-Policy Self-Distillation in Video Large Language Models](https://arxiv.org/abs/2608.27065) | Nanyang Technological University; The Chinese University of Hong Kong | 2026-08-27 | — | 5 |
| [Where to Look Matters: On-Policy Self-Distillation for Long-Video Understanding](https://arxiv.org/abs/2608.25356) | University of Maryland | 2026-08-26 | — | 6 |
| [StreamOPD: A Post-Training Recipe with Spatio-Temporal Cue Gating for Streaming Video Understanding](https://arxiv.org/abs/2608.16320) | Tsinghua University | 2026-08-17 | — | 2 |
| [Deep Thought Alignment: Trajectory-Level Latent Distillation for Video Reasoning](https://arxiv.org/abs/2608.16316) | Tencent; Fudan University | 2026-08-17 | — | 2 |
| [Video-OPD: Efficient Post-Training of Multimodal Large Language Models for Temporal Video Grounding via On-Policy Distillation](https://arxiv.org/abs/2602.02994) | — | 2026-02-03 | — | 37 |

</details>

<h2 id="audio-agentic-opd">🔊 Audio Agentic OPD</h2>

On-policy distillation for speech, audio-language and voice-interaction agents. **8 papers**, 2 with code.

| Paper | Affiliation | Date | Code | Cited |
| :-- | :-- | :-: | :-: | :-: |
| [OPOD: On-Policy Omni Distillation](https://arxiv.org/abs/2607.20918) | Renmin University of China; Tencent | 2026-07-23 | [⭐ 58](https://github.com/VincentZhao2002/OPOD) | 1 |
| [Reward-Tilted On-Policy Distillation for Acoustic Grounding in Audio-Language Models](https://arxiv.org/abs/2609.28778) | NEC Laboratories America; University of Connecticut | 2026-09-23 | [⭐ 1](https://github.com/KaiyangLi1992/RT-OPD) | 0 |

<details>
<summary>📄 6 more without public code (newest first)</summary>

| Paper | Affiliation | Date | Code | Cited |
| :-- | :-- | :-: | :-: | :-: |
| [OP-CAD: On-Policy Clean-Audio Distillation for Robust Audio-Visual Reasoning](https://arxiv.org/abs/2609.39150) | Tsinghua Shenzhen International Graduate School; Tsinghua University | 2026-09-30 | — | 0 |
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

Add an entry to [`papers.json`](papers.json) and open a PR. `README.md` and `index.html` are generated by [`scripts/update_stats.py`](scripts/update_stats.py), so please do not edit them by hand. Stars come from the GitHub API and citations from Semantic Scholar, refreshed daily by [a GitHub Action](.github/workflows/refresh.yml) (last run: 2026-10-22 06:39 UTC).

## Acknowledgments

The initial layout is adapted from [README-Reference.md](README-Reference.md). Summaries are paraphrased from abstracts and may contain errors — the papers are the reference.

## License

[CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/) — public-domain dedication.
