<h1 align="center">Awesome Agentic On-Policy Distillation</h1>

<p align="center">Papers, benchmarks, datasets and codebases for <b>Agentic OPD / OPSD</b> —<br>organized by language, multimodal, omni-modal, embodied, video, audio and Agentic Generative Systems.</p>

<p align="center">
  <a href="https://yongtang2025.github.io/Awesome-Agentic-OPD/"><img src="https://img.shields.io/badge/Interactive_reader-EN_%2F_%E4%B8%AD%E6%96%87-1f6feb?style=flat-square" alt="Interactive reader"></a>
  <img src="https://img.shields.io/badge/papers-100-4E6813?style=flat-square" alt="papers">
  <img src="https://img.shields.io/badge/with_code-33-2E86C1?style=flat-square" alt="with code">
  <img src="https://img.shields.io/badge/updated-2026.10.30-purple?style=flat-square" alt="updated">
</p>

<p align="center">
  <a href="#llm-agentic-opd">LLM (78)</a> · <a href="#multimodal-agentic-opd">Multimodal (9)</a> · <a href="#omni-agentic-opd">Omni (0)</a> · <a href="#embodied-agentic-opd">Embodied (12)</a> · <a href="#video-agentic-opd">Video (0)</a> · <a href="#audio-agentic-opd">Audio (0)</a> · <a href="#ags-opd">AGS (1)</a>
</p>

> **On-policy distillation (OPD)** — the student learns from *its own* rollouts `y ~ π_student(·|x)`, while a teacher scores or corrects those student-generated samples. **OPSD** is the self-distillation case: the teacher is the same model, given privileged information.

### Inclusion criteria

This collection covers **on-policy distillation of interactive agent policies**. A paper must establish both:

1. **Agent interaction:** actions are executed through tools, software, a simulator, a robot, or another external interface, including task communication with users or other independently acting agents; returned observations or feedback inform subsequent decisions.
2. **On-policy distillation:** an explicit teacher, self-teacher, or target-policy alignment objective trains the agent on student-generated actions, responses, action-flow states, or student-visited interaction states.

Text decoding alone, fixed-image/video/audio QA, static screenshot-to-coordinate grounding, teacher-provided crops, visual-token compression, and internal denoising steps do not establish an agent interaction loop. Successful-trajectory or teacher-continuation SFT alone is not sufficient evidence of OPD.

Interaction and on-policy sampling are checked separately: a policy may train on offline contexts and still execute a closed-loop agent task. Embodied action-flow OPD, replay-based methods, and teacher-free target-policy variants are identified in the interactive reader; they are not described as fresh environment rollouts during distillation.

Agentic OP(S)D also includes methods that convert teacher re-scoring of student interaction trajectories into dense RL credit. The reader distinguishes these from standalone distribution-matching losses, state-level teacher corrections, and comparative studies.

See the [scope audit](ccfa-workfiles/checks/agentic-scope/scope-audit.md) for paper-level inclusion evidence and exclusions.

Search, filter and read a four-point summary of every paper in the **[interactive reader](https://yongtang2025.github.io/Awesome-Agentic-OPD/)** ([mirror](https://htmlpreview.github.io/?https://github.com/yongtang2025/Awesome-Agentic-OPD/blob/main/index.html)).

## 🔥 Most starred

| # | Paper | Domain | Affiliation | Code |
| :-: | :-- | :-- | :-- | :-: |
| 1 | [Self-Distilled Agentic Reinforcement Learning](https://arxiv.org/abs/2605.15155) | LLM | — | [⭐ 376](https://github.com/ZJU-REAL/SDAR) |
| 2 | [RetireOPD: Self-Retiring On-Policy Distillation for Agentic Reinforcement Learning](https://arxiv.org/abs/2609.20784) | LLM | — | [⭐ 376](https://github.com/ZJU-REAL/SDAR) |
| 3 | [SEED: Self-Evolving On-Policy Distillation for Agentic Reinforcement Learning](https://arxiv.org/abs/2607.14777) | LLM | — | [⭐ 304](https://github.com/jinyangwu/SEED) |
| 4 | [SOD: Step-wise On-policy Distillation for Small Language Model Agents](https://arxiv.org/abs/2605.07725) | LLM | — | [⭐ 166](https://github.com/YoungZ365/SOD) |
| 5 | [OPID: On-Policy Skill Distillation for Agentic Reinforcement Learning](https://arxiv.org/abs/2606.26790) | LLM | — | [⭐ 128](https://github.com/jinyangwu/OPID) |
| 6 | [TCOD: Exploring Temporal Curriculum in On-Policy Distillation for Multi-turn Autonomous Agents](https://arxiv.org/abs/2604.24005) | LLM | — | [⭐ 115](https://github.com/kokolerk/TCOD) |
| 7 | [AgentOPSD: Recursive Self-Distillation for Agentic Reinforcement Learning](https://arxiv.org/abs/2608.05987) | LLM | — | [⭐ 86](https://github.com/ZethWang/AgentOPSD) |
| 8 | [UI-MOPD: Multi-Platform On-Policy Distillation for Unified GUI Agents](https://arxiv.org/abs/2607.04425) | Multimodal | Tsinghua University | [⭐ 62](https://github.com/EliSpectre/UI-MOPD) |
| 9 | [From Proprietary to Open-Source: Bridging the Distribution Gap via Multi-Agent Protocol Distillation in Agentic Search](https://arxiv.org/abs/2607.24280) | LLM | — | [⭐ 44](https://github.com/AaronLiu0702/MAPD) |
| 10 | [MAD-OPD: Breaking the Ceiling in On-Policy Distillation via Multi-Agent Debate](https://arxiv.org/abs/2605.01347) | LLM | Huazhong University of Science and Technology; Alibaba Group | [⭐ 38](https://github.com/chiefovoavicii/MAD-OPD) |

<h2 id="llm-agentic-opd">🧠 LLM Agentic OPD</h2>

On-policy distillation for language-model agents that execute tools, operate external environments, or exchange task feedback with users and other agents. **78 papers**, 29 with code.

| Paper | Affiliation | Date | Code | Cited |
| :-- | :-- | :-: | :-: | :-: |
| [Self-Distilled Agentic Reinforcement Learning](https://arxiv.org/abs/2605.15155) | — | 2026-05-14 | [⭐ 376](https://github.com/ZJU-REAL/SDAR) | 60 |
| [RetireOPD: Self-Retiring On-Policy Distillation for Agentic Reinforcement Learning](https://arxiv.org/abs/2609.20784) | — | 2026-09-17 | [⭐ 376](https://github.com/ZJU-REAL/SDAR) | 4 |
| [SEED: Self-Evolving On-Policy Distillation for Agentic Reinforcement Learning](https://arxiv.org/abs/2607.14777) | — | 2026-07-16 | [⭐ 304](https://github.com/jinyangwu/SEED) | 43 |
| [SOD: Step-wise On-policy Distillation for Small Language Model Agents](https://arxiv.org/abs/2605.07725) | — | 2026-05-08 | [⭐ 166](https://github.com/YoungZ365/SOD) | 26 |
| [OPID: On-Policy Skill Distillation for Agentic Reinforcement Learning](https://arxiv.org/abs/2606.26790) | — | 2026-06-25 | [⭐ 128](https://github.com/jinyangwu/OPID) | 38 |
| [TCOD: Exploring Temporal Curriculum in On-Policy Distillation for Multi-turn Autonomous Agents](https://arxiv.org/abs/2604.24005) | — | 2026-04-27 | [⭐ 115](https://github.com/kokolerk/TCOD) | 55 |
| [AgentOPSD: Recursive Self-Distillation for Agentic Reinforcement Learning](https://arxiv.org/abs/2608.05987) | — | 2026-08-06 | [⭐ 86](https://github.com/ZethWang/AgentOPSD) | 13 |
| [From Proprietary to Open-Source: Bridging the Distribution Gap via Multi-Agent Protocol Distillation in Agentic Search](https://arxiv.org/abs/2607.24280) | — | 2026-07-27 | [⭐ 44](https://github.com/AaronLiu0702/MAPD) | 9 |
| [MAD-OPD: Breaking the Ceiling in On-Policy Distillation via Multi-Agent Debate](https://arxiv.org/abs/2605.01347) | Huazhong University of Science and Technology; Alibaba Group | 2026-05-02 | [⭐ 38](https://github.com/chiefovoavicii/MAD-OPD) | 18 |
| [UCOB: Learning to Utilize and Evolve Agentic Skills via Credit-Aware On-Policy Bidirectional Self-Distillation](https://arxiv.org/abs/2606.29502) | — | 2026-06-28 | [⭐ 34](https://github.com/TU2021/UCOB) | 15 |
| [Look Ahead Before You Distill: Future Trajectory Validation of Teacher Guidance for Agentic On-Policy Distillation](https://arxiv.org/abs/2608.01953) | — | 2026-08-03 | [⭐ 26](https://github.com/ChenChiShui/FutureBridge-OPD) | 14 |
| [ATOD: Annealed Turn-Aware On-Policy Distillation for Multi-Turn Agentic Tasks](https://arxiv.org/abs/2606.27814) | — | 2026-06-26 | [⭐ 21](https://github.com/TanQitai/ATOD) | 11 |
| [Group-Reflective Self-Distillation for Agentic Reinforcement Learning](https://arxiv.org/abs/2607.28076) | — | 2026-07-30 | [⭐ 21](https://github.com/BinbZheng1/GRSD) | 7 |
| [SecOPD: Mitigating Adaptive Prompt Injections by On-Policy Distillation](https://arxiv.org/abs/2608.21500) | — | 2026-08-21 | [⭐ 15](https://github.com/pppyb/SecOPD) | 7 |
| [Agentic Reinforcement Learning with Observation-Calibrated Self-Distillation](https://arxiv.org/abs/2608.04788) | — | 2026-08-05 | [⭐ 9](https://github.com/yiy1x/OCSD) | 7 |
| [DASH-OPD: Discrepancy-Aware Switching with Hysteresis for On-Policy Distillation](https://arxiv.org/abs/2607.29078) | — | 2026-07-31 | [⭐ 7](https://github.com/Lucian1115/DASH-OPD) | 4 |
| [Agentic Reinforcement Learning with Self-Distilled Reward Shaping](https://arxiv.org/abs/2608.03223) | — | 2026-08-04 | [⭐ 7](https://github.com/gitrxh/ADRS-arxiv) | 3 |
| [MemOPD: On-Policy Distillation through Memory State Alignment for Long-Horizon Agents](https://arxiv.org/abs/2608.07068) | — | 2026-08-07 | [⭐ 5](https://github.com/TPssp/MemOPD) | 2 |
| [Beyond Timestamps: Decision-Aligned On-Policy Distillation for Long-Horizon Agents](https://arxiv.org/abs/2609.33391) | — | 2026-09-27 | [⭐ 4](https://github.com/mingju-c/Align-OPSD) | 2 |
| [ToolOPD: Credit-Aware On-Policy Distillation for Tool-Use Agents](https://arxiv.org/abs/2610.25693) | Northeastern University; Honor Device Co., Ltd. | 2026-10-19 | [⭐ 4](https://github.com/MagicAgent-Search/ToolOPD) | 0 |
| [When Privileged Guidance Misaligns: State-Matched Routing and Contextualized Self-Distillation for Multi-Turn Agents](https://arxiv.org/abs/2608.05219) | — | 2026-08-05 | [⭐ 3](https://github.com/liujunzhuo/SMRC-SD) | 6 |
| [From Scoring to Acting: Outcome-Verified Comparative Self-Distillation for LLM Agents](https://arxiv.org/abs/2607.27937) | — | 2026-07-30 | [⭐ 3](https://github.com/shane990928-xia/OVCSD) | 3 |
| [Beyond the Teacher: Understanding and Preserving Distillation Overshoot in Agentic On-Policy Distillation](https://arxiv.org/abs/2610.25034) | University of Southern California; University of Florida; Emory University; University of Alabama; University of Maryland; Amazon AGI; Boston University; The Ohio State University; National Taiwan University | 2026-10-18 | [⭐ 2](https://github.com/Jike338/SPOD) | 0 |
| [UniOPSD: Unifying Outcome and Hindsight Feedback for Agentic Reinforcement Learning](https://arxiv.org/abs/2609.34810) | — | 2026-09-28 | [⭐ 2](https://github.com/Zenghuang-Fu/Uniopsd) | 0 |
| [PR-OPD: Privileged Representation On-policy Self-Distillation for Agentic Reinforcement Learning](https://arxiv.org/abs/2609.36642) | — | 2026-09-29 | [⭐ 1](https://github.com/balibata/PR-OPD) | 1 |
| [Trust Is Not Enough: Influence Calibration for On-Policy Self-Distillation in Agentic RL](https://arxiv.org/abs/2608.14945) | — | 2026-08-14 | [⭐ 0](https://github.com/lanqz7766/Influence-Calibration-for-On-Policy-Self-Distillation-in-Agentic-RL) | 7 |
| [DivOPD: Spread Wide, Look Close for Asynchronous On-Policy Distillation of Multi-turn Agents](https://arxiv.org/abs/2609.34838) | University of Chicago; Meituan; University of Chinese Academy of Sciences; HKUST (GZ) | 2026-09-28 | [⭐ 0](https://github.com/HanyangWang0418-oss/DivOPD) | 1 |
| [GraphOPD: Graph-Augmented On-Policy Distillation for LLM Agents](https://arxiv.org/abs/2610.08959) | University of Science and Technology of China; Xiaohongshu; HKUST (GZ) | 2026-10-06 | [⭐ 0](https://github.com/BoHan-LIN04/GraphOPD) | 0 |
| [SERL-SQL: Selective Hindsight Distillation for Text-to-SQL Reinforcement Agentic Learning](https://arxiv.org/abs/2608.00485) | — | 2026-08-01 | [Code](https://github.com/Ffunkytao/SERL-SQL) | 0 |

<details>
<summary>📄 49 more without public code (newest first)</summary>

| Paper | Affiliation | Date | Code | Cited |
| :-- | :-- | :-: | :-: | :-: |
| [Capable Teacher, Myopic Scorer: Reward-Free Teacher Repair for Agentic On-Policy Distillation](https://arxiv.org/abs/2610.28586) | NVIDIA | 2026-10-20 | — | 0 |
| [MultiAgent-OPD: End-to-End Training of Hierarchical Multi-Agent Systems with On-Policy Distillation](https://arxiv.org/abs/2610.23234) | Alibaba Group; Zhejiang University | 2026-10-16 | — | 0 |
| [OPRD: On-Policy Reminder Distillation for Long-Horizon Coding Agents](https://arxiv.org/abs/2610.21496) | — | 2026-10-15 | — | 0 |
| [Teaching Agents in their Own Style: Blackbox Teacher Distillation for Web Agents](https://arxiv.org/abs/2610.19834) | University of Utah | 2026-10-14 | — | 0 |
| [ActionOPD: Distilling Decisions, Not Tokens](https://arxiv.org/abs/2610.19820) | Tsinghua University | 2026-10-14 | — | 0 |
| [More Methods, Better Agents? A Reality Check on Self-Distillation in Agentic Reinforcement Learning](https://arxiv.org/abs/2610.19789) | — | 2026-10-14 | — | 0 |
| [DTDD: Divergence-Triggered Dynamic Distillation for Reliable On-Policy Supervision](https://arxiv.org/abs/2610.19302) | — | 2026-10-13 | — | 0 |
| [Branching On-Policy Distillation](https://arxiv.org/abs/2610.13481) | — | 2026-10-09 | — | 0 |
| [State-OPD: State-Grounded On-Policy Distillation for Multi-Turn Agents](https://arxiv.org/abs/2610.13238) | Alibaba Group; Tsinghua University; Shanghai Jiao Tong University; USTC | 2026-10-09 | — | 0 |
| [Stochastic Teacher Intervention for Agentic On-Policy Distillation](https://arxiv.org/abs/2610.10878) | Monash University; The Hong Kong Polytechnic University; Zhongguancun Laboratory | 2026-10-07 | — | 0 |
| [SCAD: Structured Credit Assignment and Distillation for Long-Horizon Agents](https://arxiv.org/abs/2610.03372) | Beijing University of Posts and Telecommunications; Tsinghua University; Nanyang Technological University | 2026-10-02 | — | 0 |
| [Harness-Aware Distillation for Small Language Model Agents](https://arxiv.org/abs/2610.02858) | KAIST AI; Independent researcher | 2026-10-02 | — | 0 |
| [RISED: RubrIcs for agentic multi-environment Selection and sElf-Distillation](https://arxiv.org/abs/2610.00979) | — | 2026-10-01 | — | 0 |
| [PivotOPD: Learning to Recover from Pivotal Mistakes in Multi-Turn Agents](https://arxiv.org/abs/2609.40285) | Princeton University; NVIDIA; University of Maryland | 2026-09-30 | — | 0 |
| [From Imitation to Reward Discovery: On-Policy Warmup for Agentic RL](https://arxiv.org/abs/2609.39436) | — | 2026-09-30 | — | 0 |
| [ReSAIL: Mitigating Collapse in Iterative Agent Self-Distillation](https://arxiv.org/abs/2609.39306) | Renmin University of China | 2026-09-30 | — | 0 |
| [Graph-Conditioned On-Policy Agent Distillation from Off-the-Shelf Teachers](https://arxiv.org/abs/2609.37522) | — | 2026-09-29 | — | 1 |
| [Act First, Reason Later: Accelerating On-Policy Distillation for Multi-Turn Agents via Reference-Conditioned Inverse Dynamics](https://arxiv.org/abs/2609.36608) | Southern University of Science and Technology; Zhongguancun Academy; Hong Kong Polytechnic University; DeepCybo; Nanyang Technological University | 2026-09-29 | — | 1 |
| [Teacher–Student Gaps Are Not Enough: Outcome-Guided On-Policy Distillation for Multi-Turn Autonomous Agents](https://arxiv.org/abs/2609.35319) | Alibaba; Peking University; University of Chinese Academy of Sciences; Shanghai Jiao Tong University | 2026-09-28 | — | 0 |
| [TIDE: Teacher-Student Transition via Informative Distillation and Exploration for Agentic RL](https://arxiv.org/abs/2609.35058) | — | 2026-09-28 | — | 0 |
| [MAS-OPD: On-Policy Distillation for Multi-agent Systems](https://arxiv.org/abs/2609.34234) | — | 2026-09-28 | — | 0 |
| [UOPD: Uncertainty-Aware Intervention for On-Policy Distillation of Multi-Turn Agents](https://arxiv.org/abs/2609.34036) | — | 2026-09-27 | — | 2 |
| [Dense Is Not Enough: Hierarchical Supervision Allocation for Long-Horizon On-Policy Distillation](https://arxiv.org/abs/2609.33409) | — | 2026-09-27 | — | 0 |
| [Know When to Stop, Where to Restart: Accelerating Multi-Turn Agentic On-Policy Distillation](https://arxiv.org/abs/2609.14636) | — | 2026-09-13 | — | 2 |
| [RISE: Recursive Improvement via Self-Extrapolating Policy Distillation](https://arxiv.org/abs/2609.05295) | — | 2026-09-04 | — | 5 |
| [Reconciling Process Supervision with Outcome-Based Credit in Agentic Policy Optimization](https://arxiv.org/abs/2608.31077) | — | 2026-08-31 | — | 4 |
| [AHEAD: Adaptive Hindsight with Environment-Augmented Distillation for Agentic RL](https://arxiv.org/abs/2608.24114) | — | 2026-08-25 | — | 2 |
| [Step-Level On-Policy Distillation: Interpolating Between On-Policy Distillation and Supervised Fine-Tuning](https://arxiv.org/abs/2608.16333) | Nanjing University; XingYun Lab, HUJING Digital Media & Entertainment Group; University of Chinese Academy of Sciences; Fudan University | 2026-08-17 | — | 9 |
| [Latent On-Policy Self-Distillation](https://arxiv.org/abs/2608.13040) | National University of Singapore; Beijing University of Posts and Telecommunications; Shanghai Jiao Tong University | 2026-08-13 | — | 8 |
| [Bidirectional Context Self-Distillation for Reinforcement Learning of Skill-Based LLM Agents](https://arxiv.org/abs/2608.09555) | — | 2026-08-10 | — | 1 |
| [PCSD: Persistent Consistency for Self-Distillation in Agentic Reinforcement Learning](https://arxiv.org/abs/2608.01837) | — | 2026-08-03 | — | 9 |
| [The Physics of Multi-Turn Long-Horizon Planning: From Pre-training to Post-training via Single- and Multi-Teacher On-Policy Agentic Distillation](https://arxiv.org/abs/2607.24720) | — | 2026-07-27 | — | 4 |
| [TurnOPD: Making On-Policy Distillation Turn-Aware for Efficient Long-Horizon Agent Training](https://arxiv.org/abs/2607.05804) | — | 2026-07-07 | — | 24 |
| [Multi-Turn On-Policy Distillation with Prefix Replay](https://arxiv.org/abs/2607.04763) | — | 2026-07-06 | — | 24 |
| [Building Multi-Task Agentic LLMs via Two-Phase Distillation](https://arxiv.org/abs/2606.30044) | — | 2026-06-29 | — | 1 |
| [CRAFT: Counterfactual Credit Assignment from Free Sibling Rollouts for Self-Distilled Agentic Reinforcement Learning](https://arxiv.org/abs/2606.29476) | — | 2026-06-28 | — | 9 |
| [SAGE-OPD: Selective Agent-Guided Intervention for Multi-Turn On-Policy Distillation](https://arxiv.org/abs/2606.19659) | — | 2026-06-17 | — | 19 |
| [OPD-Evolver: Cultivating Holistic Agent Evolver via On-Policy Distillation](https://arxiv.org/abs/2606.17628) | — | 2026-06-16 | — | 2 |
| [On-Policy Distillation with Curriculum Turn-level Guidance for Multi-turn Agents](https://arxiv.org/abs/2606.15912) | — | 2026-06-14 | — | 34 |
| [Keep Policy Gradient in Charge: Sibling-Guided Credit Distillation for Long-Horizon Tool-Use Agents](https://arxiv.org/abs/2606.12634) | — | 2026-06-10 | — | 7 |
| [GAPD: Gold-Action Policy Distillation for Agentic Reinforcement Learning in Knowledge Base Question Answering](https://arxiv.org/abs/2605.29584) | — | 2026-05-28 | — | 2 |
| [StepOPSD: Step-Aware Online Preference Self-Distillation for Agent Reinforcement Learning](https://arxiv.org/abs/2605.27140) | — | 2026-05-26 | — | 15 |
| [SD-Search: On-Policy Hindsight Self-Distillation for Search-Augmented Reasoning](https://arxiv.org/abs/2605.18299) | Kuaishou | 2026-05-18 | — | 8 |
| [f-OPD: Stabilizing Long-Horizon On-Policy Distillation with Freshness-Aware Control](https://arxiv.org/abs/2605.17862) | — | 2026-05-18 | — | 6 |
| [Skill-SD: Skill-Conditioned Self-Distillation for Multi-turn LLM Agents](https://arxiv.org/abs/2604.10674) | vivo AI Lab; Hangzhou Institute for Advanced Study, University of Chinese Academy of Sciences; University of Science and Technology of China; The Chinese University of Hong Kong; University of Chinese Academy of Sciences | 2026-04-12 | — | 99 |
| [Revisiting On-Policy Distillation: Empirical Failure Modes and Simple Fixes](https://arxiv.org/abs/2603.25562) | — | 2026-03-26 | — | 157 |
| [Online Experiential Learning for Language Models](https://arxiv.org/abs/2603.16856) | Microsoft Research | 2026-03-17 | — | 28 |
| [On-Policy Context Distillation for Language Models](https://arxiv.org/abs/2602.12275) | Microsoft Research | 2026-02-12 | — | 200 |
| [OVD: On-policy Verbal Distillation](https://arxiv.org/abs/2601.21968) | — | 2026-01-29 | — | 9 |

</details>

<h2 id="multimodal-agentic-opd">🧩 Multimodal Agentic OPD</h2>

On-policy distillation for multimodal agents with action-observation loops, including visual tools, multimodal search and multi-turn GUI interaction. **9 papers**, 3 with code.

| Paper | Affiliation | Date | Code | Cited |
| :-- | :-- | :-: | :-: | :-: |
| [UI-MOPD: Multi-Platform On-Policy Distillation for Unified GUI Agents](https://arxiv.org/abs/2607.04425) | Tsinghua University | 2026-07-05 | [⭐ 62](https://github.com/EliSpectre/UI-MOPD) | 7 |
| [On-Policy Visual Evidence Distillation](https://arxiv.org/abs/2609.36838) | — | 2026-09-29 | [⭐ 3](https://github.com/sylvain-wei/ReVuE) | 0 |
| [VISTA: Internalizing Collective Visual Experience via On-Policy Distillation for Active Multimodal Agents](https://arxiv.org/abs/2609.38086) | Tsinghua University | 2026-09-29 | [⭐ 1](https://github.com/jiangz20/VISTA) | 0 |

<details>
<summary>📄 6 more without public code (newest first)</summary>

| Paper | Affiliation | Date | Code | Cited |
| :-- | :-- | :-: | :-: | :-: |
| [MMSearch-OPD: Easy Made Hard, Hard Made Learnable for Long-Horizon Multimodal Search Agents](https://arxiv.org/abs/2610.22240) | Peking University; HKUST (GZ); Tsinghua University; The University of Hong Kong; Zhejiang University; Huawei Cloud | 2026-10-15 | — | 1 |
| [ECHOES: Seeing Beyond the Current Image via Recursive History Compression and Privileged On-Policy Distillation](https://arxiv.org/abs/2610.22408) | Tsinghua University; StepFun; Nanyang Technological University; Leapmotor; Honor | 2026-10-14 | — | 0 |
| [Information-Gain Calibrated On-Policy Distillation for Deep Search Agents](https://arxiv.org/abs/2610.20664) | The Chinese University of Hong Kong, Shenzhen; Renmin University of China; Beijing University of Posts and Telecommunications; BAAI | 2026-10-14 | — | 0 |
| [PIVOT: Pivot-Aware On Policy Self Distillation for Multi-Turn VLM Agents](https://arxiv.org/abs/2609.35303) | HKUST (GZ); IDEA; The Hong Kong Polytechnic University; Nanyang Technological University; Tsinghua University | 2026-09-28 | — | 0 |
| [Learn How to Act from Your Own Interactions: On-Policy Self-Distillation for GUI Agents](https://arxiv.org/abs/2609.27307) | Tsinghua University; Tencent; Chinese Academy of Sciences; Institute of Information Engineering; Nankai University | 2026-09-23 | — | 0 |
| [The Next Screenshot Knows: Gated Hindsight Distillation for Mobile GUI Agents](https://arxiv.org/abs/2608.06065) | University of Electronic Science and Technology of China | 2026-08-06 | — | 2 |

</details>

<h2 id="omni-agentic-opd">🌐 Omni Agentic OPD</h2>

On-policy distillation for omni-modal agents that jointly perceive and act across text, vision, audio and other modalities, including omni-modal tool calling, cross-modal tool results and multi-turn agent interaction. **0 papers**, 0 with code.

No papers currently listed meet both the interaction and distillation criteria.

| Paper | Affiliation | Date | Code | Cited |
| :-- | :-- | :-: | :-: | :-: |

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
| [Reflect-VLA: Internalizing Reflective Guidance via Dual-Path On-Policy Self-Distillation for Autonomous Driving](https://arxiv.org/abs/2610.13453) | Tsinghua University; University of Macau; University of Science and Technology of China; Beijing Jiaotong University | 2026-10-09 | — | 2 |
| [JoyInside-VLM-Agent: Product-Conditioned Multimodal Policy Learning for Embodied Agents](https://arxiv.org/abs/2610.12957) | JD.COM | 2026-10-09 | — | 0 |
| [FastOPD: On-Policy Distillation for Lightweight VLA Deployment](https://arxiv.org/abs/2610.02832) | KAIST; Sungkyunkwan University | 2026-10-02 | — | 0 |
| [DriftOPD: Sequence-Level Reverse-KL Distillation for One-Step VLA Policies](https://arxiv.org/abs/2610.00317) | Korea Advanced Institute of Science and Technology; Sungkyunkwan University | 2026-09-29 | — | 0 |
| [WAM-OPD: Sharpening World Action Models via On-Policy Distillation](https://arxiv.org/abs/2609.34250) | USTC; Zhejiang University; Shandong Normal University; Tencent Hunyuan3D | 2026-09-28 | — | 0 |
| [RE-0: Verified Recursive Improvement of Embodied Code-as-Policy Agents through Local On-Policy Distillation](https://arxiv.org/abs/2609.32416) | Jilin University; Dalian University of Technology | 2026-09-26 | — | 1 |
| [WAM-OPD: Joint Video-Action Supervision for World Action Model Post-Training with On-Policy Distillation](https://arxiv.org/abs/2608.22364) | University College London | 2026-08-23 | — | 2 |
| [FORCE: Efficient VLA Reinforcement Fine-Tuning via Value-Calibrated Warm-up and Self-Distillation](https://arxiv.org/abs/2606.26006) | Peking University; Beijing Academy of Artificial Intelligence; Institute of Physics | 2026-06-24 | — | 2 |
| [ROAD-VLA: Robust Online Adaptation via Self-Distillation for Vision-Language-Action Models](https://arxiv.org/abs/2606.25800) | UNSW Sydney; Deakin University; United States Air Force Research Laboratory | 2026-06-24 | — | 0 |
| [VLA-OPD: Bridging Offline SFT and Online RL for Vision-Language-Action Models via On-Policy Distillation](https://arxiv.org/abs/2603.26666) | HKUST (GZ) | 2026-03-27 | — | 15 |

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

Add an entry to [`papers.json`](papers.json) and open a PR. `README.md` and `index.html` are generated by [`scripts/update_stats.py`](scripts/update_stats.py), so please do not edit them by hand. Stars come from the GitHub API and citations from Semantic Scholar, refreshed daily by [a GitHub Action](.github/workflows/refresh.yml) (last run: 2026-10-30 10:07 UTC).

## License

[CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/) — public-domain dedication.

## Acknowledgments

> **With gratitude and respect to [Awesome-Multimodal-OPD](https://github.com/Jingchensun/Awesome-Multimodal-OPD).** We acknowledge its foundational contribution to organizing the multimodal on-policy distillation literature. If you want to understand the **Multimodal OPD field as a whole**, please visit [Awesome-Multimodal-OPD](https://github.com/Jingchensun/Awesome-Multimodal-OPD).

Summaries are paraphrased from abstracts and may contain errors — the papers are the reference.
