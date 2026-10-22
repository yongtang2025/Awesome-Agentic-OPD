# Agentic OPD 收录范围核验

核验日期：2026-10-22。模式：citation-audit / scope audit。检查对象：`papers.json`、生成的 `README.md` / `index.html` 及统计缓存。

本次按用户要求检查两项条件：任务中有实际动作执行、返回观察或执行反馈及后续决策；方法中有作用于学生采样输出、动作生成路径或学生访问状态的明确蒸馏/目标策略对齐。普通 VLM 推理、视觉证据教师、内部迭代和论文中的 agent/rollout 字样均不能单独满足第一项。

在线采集环境轨迹不是统一的硬性门槛：离线前缀上的学生采样蒸馏、机器人动作 flow 蒸馏或固定历史回放，在具有闭环执行证据时仍可收录，但必须说明各自的 on-policy 层级。仅有成功轨迹筛选 SFT 或教师接管后 continuation SFT，不等同于本目录的 OPD 对齐目标。

证据覆盖：逐条读取原清单 102 篇论文的 arXiv 摘要并核对标题/标识符；对 GUI grounding、SkillLens、SGCD、DeepSearch-World、SOPD-SocialNav、RPD、FastOPD、DriftOPD、FORCE 和 SnapFlow 等边界条目进一步核对正文方法或评测段落。其余条目是摘要级范围判断，不表示全文科学评审或代码复现。这里的“移出”是本目录的收录决定，不等于否定论文价值或断言其所有扩展均不可能交互。

共移出 64 篇，保留 38 篇。Video/Audio 分类保留为空占位；零收录仅描述原清单经本次核验后的结果，不声称该领域不存在相关工作。

| 分类 | 核验前 | 保留 | 移出 |
| :-- | --: | --: | --: |
| LLM | 17 | 16 | 1 |
| Multimodal | 51 | 9 | 42 |
| Embodied | 15 | 12 | 3 |
| Video | 10 | 0 | 10 |
| Audio | 8 | 0 | 8 |
| AGS | 1 | 1 | 0 |

## 保留：多模态 Agentic OPD

| 论文 / 主来源 | 交互与蒸馏证据 |
| :-- | :-- |
| [Information-Gain Calibrated On-Policy Distillation for Deep Search Agents](https://arxiv.org/abs/2610.20664) | 搜索查询返回外部证据并影响下一轮；用检索后的信息增益校准学生查询的 OPD。 |
| [MMSearch-OPD: Easy Made Hard, Hard Made Learnable for Long-Horizon Multimodal Search Agents](https://arxiv.org/abs/2610.22240) | 长程多模态搜索持续获取证据；在不完美学生交互轨迹上联合 RL 和 token-level OPD。 |
| [ECHOES: Seeing Beyond the Current Image via Recursive History Compression and Privileged On-Policy Distillation](https://arxiv.org/abs/2610.22408) | GUI 中的 Compression-Think-Action 多轮执行；多历史截图教师对学生 CTA rollout 蒸馏。 |
| [VISTA: Internalizing Collective Visual Experience via On-Policy Distillation for Active Multimodal Agents](https://arxiv.org/abs/2609.38086) | 学生主动调用视觉工具取得观察，部署仍保留工具；跨轨迹视觉经验条件教师评分学生前缀。 |
| [PIVOT: Pivot-Aware On Policy Self Distillation for Multi-Turn VLM Agents](https://arxiv.org/abs/2609.35303) | 多轮视觉任务的动作日志、状态变化及失败后果；诊断教师对失败 token 作 confidence-gated OPD。 |
| [UI-MOPD: Multi-Platform On-Policy Distillation for Unified GUI Agents](https://arxiv.org/abs/2607.04425) | 桌面/移动端可执行交互；平台专用教师监督共享学生访问状态，评测 OSWorld/MobileWorld 任务成功。 |
| [On-Policy Visual Evidence Distillation](https://arxiv.org/abs/2609.36838) | ReVuE 交替执行图像操作与推理并获得视觉观察；视觉证据相关教师信号用于 on-policy 蒸馏。 |
| [Learn How to Act from Your Own Interactions: On-Policy Self-Distillation for GUI Agents](https://arxiv.org/abs/2609.27307) | GUI-SD-v2 明确扩展到多轮软件交互；蒸馏步骤推理与记忆，评测 AndroidWorld/MobileWorld。 |
| [The Next Screenshot Knows: Gated Hindsight Distillation for Mobile GUI Agents](https://arxiv.org/abs/2608.06065) | GHD 在离线历史前缀采样学生回答，由下一截图特权教师重评分；AndroidWorld/AndroidLab 评测闭环任务成功。 |

## 移出条目与理由

正文定位：GUI Test-Time Self-Evolving 的方法中 Exploration / Evaluation & Reflection 及实验的 grounding metric；SkillLens 的 Experimental Setup / CardDistill Results；SGCD §4.4–4.5；DeepSearch-World 的 Supervised self-distillation update；SOPD-SocialNav §IV-E；SnapFlow 的 shortcut objective。其他行依据作者摘要列出的任务与训练机制。

### LLM：移出 1 篇

| 论文 / 主来源 | 范围判定 |
| :-- | :-- |
| [DeepSearch-World: Self-Distillation for Deep Search Agents in a Verifiable Environment](https://arxiv.org/html/2607.07820v2) | DeepSearch-World 有搜索/读页交互，但 DeepSearch-Evolve 的更新为轨迹生成、筛选、混合和 SFT；正文将其描述为 evolving SFT，未建立学生输出上的 OPD 对齐目标。 |

### Multimodal：移出 42 篇

| 论文 / 主来源 | 范围判定 |
| :-- | :-- |
| [Learn where to Click from Yourself: On-Policy Self-Distillation for GUI Grounding](https://arxiv.org/abs/2605.00642) | GUI-SD v1：固定截图上的坐标定位，以六个 grounding 基准评测；与多轮 GUI-SD-v2 区分。 |
| [Test-Time Self-Evolving GUI Visual Grounding via Reflection-Guided On-Policy Self-Distillation](https://arxiv.org/html/2608.11191v1) | 正文中的 Exploration 是从截图预测坐标，Reflector 查看同一截图评判；六个基准用点落在目标框内的准确率，未执行 GUI 动作形成后续屏幕。 |
| [Skill-Decoupled On-Policy Expert Distillation for Unified Vision-Language Models](https://arxiv.org/abs/2610.22217) | 静态图像理解、视觉推理或感知蒸馏；摘要中的 student rollout 是输出序列，未提供动作执行后接收新观察的交互证据。 |
| [Do As I Do, Not As I Say: On-Policy Distillation Inherits the Teacher in Vision-Language Models](https://arxiv.org/abs/2610.20989) | 静态图像理解、视觉推理或感知蒸馏；摘要中的 student rollout 是输出序列，未提供动作执行后接收新观察的交互证据。 |
| [VC-OPD: Visual Counterfactual On-Policy Distillation for Grounded Vision-Language Reasoning](https://arxiv.org/abs/2610.14939) | 静态图像理解、视觉推理或感知蒸馏；摘要中的 student rollout 是输出序列，未提供动作执行后接收新观察的交互证据。 |
| [LEGO-OPD: Factorized Teacher Composition for Multimodal On-Policy Distillation](https://arxiv.org/abs/2610.00333) | 静态图像理解、视觉推理或感知蒸馏；摘要中的 student rollout 是输出序列，未提供动作执行后接收新观察的交互证据。 |
| [Is Better Teacher Supervision Enough? Unlocking Student-side Learning in Multimodal On-Policy Distillation](https://arxiv.org/abs/2609.39120) | 静态图像理解、视觉推理或感知蒸馏；摘要中的 student rollout 是输出序列，未提供动作执行后接收新观察的交互证据。 |
| [Distill the Visual Evidence, Not Just the Answer: Cross-World On-Policy Distillation for Vision-Language Models](https://arxiv.org/abs/2609.38777) | Cross-World 指受控视觉证据变化；不能据此认定有智能体驱动的环境交互。 |
| [Evidence-Aligned Multimodal On-Policy Self-Distillation for Fine-Grained Visual Understanding](https://arxiv.org/abs/2609.34672) | 静态图像理解、视觉推理或感知蒸馏；摘要中的 student rollout 是输出序列，未提供动作执行后接收新观察的交互证据。 |
| [Progressive-View On-Policy Distillation for Regional-to-Global Transfer in Multimodal LLMs](https://arxiv.org/abs/2609.32333) | 静态图像理解、视觉推理或感知蒸馏；摘要中的 student rollout 是输出序列，未提供动作执行后接收新观察的交互证据。 |
| [BAS-OPD: Budget-Aware Selective On-Policy Self-Distillation for Fine-Grained Multimodal Perception](https://arxiv.org/abs/2609.25891) | 预算控制的是训练时查询教师的监督成本；未建立部署智能体的工具/环境交互。 |
| [CA-OPD: Confidence-Aware On-Policy Distillation for Structured Visual Prediction](https://arxiv.org/abs/2609.02401) | GUI grounding 与 OCR 的结构化输出蒸馏；坐标/文本预测未建立软件执行反馈闭环。 |
| [Self-Supervised Visual On-Policy Distillation](https://arxiv.org/abs/2608.14144) | 静态图像理解、视觉推理或感知蒸馏；摘要中的 student rollout 是输出序列，未提供动作执行后接收新观察的交互证据。 |
| [SkillLens: Visual Skill Cards for Retrieval-Augmented GUI Action Prediction and On-Policy Distillation](https://arxiv.org/html/2608.10775v1) | SkillLens/CardDistill：正文评测为 Mind2Web 离线动作预测、WebLINX-BG 逐步动作匹配及 OSWorld-G 定位；未报告学生完成闭环任务的证据。 |
| [ADOPD: Reference-Privileged On-Policy Distillation for MLLM-Based Industrial Anomaly Detection](https://arxiv.org/abs/2608.09789) | 工业图像异常检测，教师参考图像为训练特权信息；未建立外部交互任务。 |
| [OPD-V: Visual On-Policy Self-Distillation with Modality Balance](https://arxiv.org/abs/2608.05131) | 静态图像理解、视觉推理或感知蒸馏；摘要中的 student rollout 是输出序列，未提供动作执行后接收新观察的交互证据。 |
| [VAD: Attributing Visual Evidence for Target Reconstruction in Multimodal On-Policy Distillation](https://arxiv.org/abs/2607.28590) | 静态图像理解、视觉推理或感知蒸馏；摘要中的 student rollout 是输出序列，未提供动作执行后接收新观察的交互证据。 |
| [OPLD: On-Policy Latent Distillation for Multimodal Reasoning](https://arxiv.org/abs/2607.28154) | 静态图像理解、视觉推理或感知蒸馏；摘要中的 student rollout 是输出序列，未提供动作执行后接收新观察的交互证据。 |
| [RP-OPSD: Resolution-Privileged On-Policy Self-Distillation for Multimodal Large Language Models](https://arxiv.org/abs/2607.24447) | 静态图像理解、视觉推理或感知蒸馏；摘要中的 student rollout 是输出序列，未提供动作执行后接收新观察的交互证据。 |
| [Med-OPD: Improving Medical Vision-Language Models via Evidence-Aware On-Policy Distillation](https://arxiv.org/abs/2607.16303) | 医学图像推理与证据加权；未建立工具执行或临床环境交互闭环。 |
| [H-OPD: Confidence Aware Heterogeneous Multi-Teacher Multimodal On-policy Distillation](https://arxiv.org/abs/2607.02592) | 静态图像理解、视觉推理或感知蒸馏；摘要中的 student rollout 是输出序列，未提供动作执行后接收新观察的交互证据。 |
| [V-Zero: Answer-Label-Free On-Policy Distillation with Contrastive Evidence Gating for Fine-Grained Visual Reasoning](https://arxiv.org/abs/2606.25319) | 静态图像理解、视觉推理或感知蒸馏；摘要中的 student rollout 是输出序列，未提供动作执行后接收新观察的交互证据。 |
| [Seeing Before Reasoning: Decoupling Perception and Reasoning for Shortcut-Resilient Multimodal On-Policy Self-Distillation](https://arxiv.org/abs/2606.19120) | 静态图像理解、视觉推理或感知蒸馏；摘要中的 student rollout 是输出序列，未提供动作执行后接收新观察的交互证据。 |
| [Visual-OPSD: Cross-Modal On-Policy Self-Distillation for Efficient Unified Multimodal Reasoning](https://arxiv.org/abs/2606.18974) | 视觉辅助教师向文本学生迁移推理；未建立生成工具执行反馈闭环。 |
| [Thinking Without Images: Internalizing Visual Manipulation with On-Policy Self-Distillation](https://arxiv.org/abs/2606.08719) | Imagine-OPD 将视觉操作收益内化到文本想象；未证明学生执行图像工具并接收新观察。 |
| [Teaching the Way, Not the Answer: Privileged Tutoring Distillation for Multimodal Policy Optimization](https://arxiv.org/abs/2606.07000) | 静态图像理解、视觉推理或感知蒸馏；摘要中的 student rollout 是输出序列，未提供动作执行后接收新观察的交互证据。 |
| [ViCuR: Visual Cues as Recoverable Privilege for Multimodal On-Policy Distillation](https://arxiv.org/abs/2606.05718) | 静态图像理解、视觉推理或感知蒸馏；摘要中的 student rollout 是输出序列，未提供动作执行后接收新观察的交互证据。 |
| [Decomposed On-Policy Distillation for Vision-Language Reasoning: Steering Gradients for Visual Grounding](https://arxiv.org/abs/2606.00564) | 静态图像理解、视觉推理或感知蒸馏；摘要中的 student rollout 是输出序列，未提供动作执行后接收新观察的交互证据。 |
| [Visual-Advantage On-Policy Distillation for Vision-Language Models](https://arxiv.org/abs/2605.21924) | 静态图像理解、视觉推理或感知蒸馏；摘要中的 student rollout 是输出序列，未提供动作执行后接收新观察的交互证据。 |
| [Vision-OPD: Learning to See Fine Details for Multimodal LLMs via On-Policy Self-Distillation](https://arxiv.org/abs/2605.18740) | Vision-OPD 用裁剪视图构造教师，推理时不使用视觉工具；不属于主动工具交互。 |
| [OPD-Aha: From Linguistic Momentum to Visual Reflection in Multimodal On-Policy Distillation](https://arxiv.org/abs/2609.16459) | 静态图像理解、视觉推理或感知蒸馏；摘要中的 student rollout 是输出序列，未提供动作执行后接收新观察的交互证据。 |
| [Trust the Right Teacher: Quality-Aware Self-Distillation for GUI Grounding](https://arxiv.org/abs/2606.18101) | Quality-Aware GUI Grounding：基于教师可靠性蒸馏定位坐标，评测为静态 GUI grounding。 |
| [Skill-Guided Continuation Distillation for GUI Agents](https://arxiv.org/html/2606.18890v1) | SGCD 有真实 GUI 交互，但 §4.5 对教师接管后的成功 continuation 做 SFT，学生前缀从动作损失中屏蔽。按本目录的 OPD 目标口径移出，不能仅因采集了学生状态就标为标准 OPD。 |
| [CV-OPD: Contrastive Vision On-policy Distillation](https://arxiv.org/abs/2610.13264) | 静态图像理解、视觉推理或感知蒸馏；摘要中的 student rollout 是输出序列，未提供动作执行后接收新观察的交互证据。 |
| [Where-OPD: Spatially Guided On-Policy Self-Distillation of MLLMs with Synthetic Scenes](https://arxiv.org/abs/2610.02117) | 静态图像理解、视觉推理或感知蒸馏；摘要中的 student rollout 是输出序列，未提供动作执行后接收新观察的交互证据。 |
| [SCOPD: Sparse-Context On-Policy Self-Distillation for Efficient Vision-Language Models](https://arxiv.org/abs/2609.34044) | 视觉 token 压缩与稀疏上下文蒸馏；没有外部动作反馈闭环。 |
| [Distill What the Student Can See: Fisher-Projected On-Policy Distillation for Vision-Language Models](https://arxiv.org/abs/2608.01263) | 静态图像理解、视觉推理或感知蒸馏；摘要中的 student rollout 是输出序列，未提供动作执行后接收新观察的交互证据。 |
| [MOPDA: Mixed-Trajectory On-Policy Distillation for Language-Guided Industrial Anomaly Detection](https://arxiv.org/abs/2607.18850) | 工业异常检测、定位与判断；混合输出轨迹不等于环境交互轨迹。 |
| [Fewer Tokens, More Self-Teaching: On-Policy Self-Distillation for Extreme Visual Token Reduction](https://arxiv.org/abs/2609.32353) | 视觉 token 极端压缩；完整视图教师监督固定输入上的学生回答。 |
| [Visual Contrastive Self-Distillation](https://arxiv.org/abs/2607.21556) | 静态图像理解、视觉推理或感知蒸馏；摘要中的 student rollout 是输出序列，未提供动作执行后接收新观察的交互证据。 |
| [Stabilizing On-Policy Distillation for MLLM Reasoning with Global Normalization](https://arxiv.org/abs/2606.09091) | 静态图像理解、视觉推理或感知蒸馏；摘要中的 student rollout 是输出序列，未提供动作执行后接收新观察的交互证据。 |
| [Beyond SFT-to-RL: Pre-alignment via Black-Box On-Policy Distillation for Multimodal RL](https://arxiv.org/abs/2604.28123) | 静态图像理解、视觉推理或感知蒸馏；摘要中的 student rollout 是输出序列，未提供动作执行后接收新观察的交互证据。 |

### Embodied：移出 3 篇

| 论文 / 主来源 | 范围判定 |
| :-- | :-- |
| [SOPD-SocialNav: Selective On-Policy Distillation for Vision-Language Social Navigation](https://arxiv.org/html/2607.19850v1) | SOPD-SocialNav 有 OPD，也报告 Scout Mini 部署；但 §IV-E 展示同一观察下的动作文本预测与延迟，尚不足以核实动作执行—新观察—再决策闭环。按证据不足移出，可在补充闭环证据后复核。 |
| [On-Policy Distillation of Language Models for Autonomous Vehicle Motion Planning](https://arxiv.org/abs/2604.07944) | GPT-Driver/nuScenes 固定场景上的 waypoint 预测与 GKD；未提供执行规划后接收新环境观察的闭环评测。 |
| [SnapFlow: One-Step Action Generation for Flow-Matching VLAs via Progressive Self-Distillation](https://arxiv.org/html/2604.05656v2) | SnapFlow 有机器人执行，但方法是离线 flow-matching 加两步 Euler shortcut 一致性自蒸馏；未建立本目录要求的学生策略分布上的 OPD 对齐目标。 |

### Video：移出 10 篇

| 论文 / 主来源 | 范围判定 |
| :-- | :-- |
| [OWLET: On-Policy Weighted Learning via Evidence Transfer for Video Large Language Model Post-Training](https://arxiv.org/abs/2610.13272) | 视频 QA、理解、推理或时间定位；学生对给定视频生成回答/时间戳，教师侧证据帧不等于学生执行视频工具。 |
| [Video-OPSD: Exploiting Privileged Visual Evidence for On-Policy Self-Distillation in Video Large Language Models](https://arxiv.org/abs/2608.27065) | 视频 QA、理解、推理或时间定位；学生对给定视频生成回答/时间戳，教师侧证据帧不等于学生执行视频工具。 |
| [Video-MOPD: Multi-Teacher On-Policy Distillation for Video Understanding](https://arxiv.org/abs/2609.09300) | 视频 QA、理解、推理或时间定位；学生对给定视频生成回答/时间戳，教师侧证据帧不等于学生执行视频工具。 |
| [Where to Look Matters: On-Policy Self-Distillation for Long-Video Understanding](https://arxiv.org/html/2608.25356v2) | Clue-OPSD 使用标注线索片段作为教师特权输入；学生并未主动调用工具选择片段并接收反馈。 |
| [StreamOPD: A Post-Training Recipe with Spatio-Temporal Cue Gating for Streaming Video Understanding](https://arxiv.org/html/2608.16320v1) | StreamOPD 按时间接收预定视频前缀并回答问题；流式输入本身没有学生动作驱动的工具或环境反馈。 |
| [Video-OPD: Efficient Post-Training of Multimodal Large Language Models for Temporal Video Grounding via On-Policy Distillation](https://arxiv.org/abs/2602.02994) | 视频 QA、理解、推理或时间定位；学生对给定视频生成回答/时间戳，教师侧证据帧不等于学生执行视频工具。 |
| [Counterfactual Attention Policy Distillation for Temporal Video Grounding](https://arxiv.org/abs/2609.34581) | 视频 QA、理解、推理或时间定位；学生对给定视频生成回答/时间戳，教师侧证据帧不等于学生执行视频工具。 |
| [MeSD: Multi-Evidence Self-Distillation for VideoLLM](https://arxiv.org/abs/2610.06342) | 视频 QA、理解、推理或时间定位；学生对给定视频生成回答/时间戳，教师侧证据帧不等于学生执行视频工具。 |
| [Deep Thought Alignment: Trajectory-Level Latent Distillation for Video Reasoning](https://arxiv.org/abs/2608.16316) | 视频 QA、理解、推理或时间定位；学生对给定视频生成回答/时间戳，教师侧证据帧不等于学生执行视频工具。 |
| [Frame Differential On-Policy Self-Distillation for Video Reasoning](https://arxiv.org/abs/2609.39021) | 视频 QA、理解、推理或时间定位；学生对给定视频生成回答/时间戳，教师侧证据帧不等于学生执行视频工具。 |

### Audio：移出 8 篇

| 论文 / 主来源 | 范围判定 |
| :-- | :-- |
| [OPOD: On-Policy Omni Distillation](https://arxiv.org/abs/2607.20918) | 给定音频/语音上的 QA、识别、情感或跨模态推理；没有已核实的多轮外部交互任务。 |
| [X$^3$-OPD: Distilling Reasoning into Large Audio-Language Models via On-Policy Alignment](https://arxiv.org/abs/2607.21550) | X³-OPD 的 spoken-dialogue reasoning 指语音对话材料上的推理；未建立学生与用户/工具持续交互的评测。 |
| [Reward-Tilted On-Policy Distillation for Acoustic Grounding in Audio-Language Models](https://arxiv.org/abs/2609.28778) | 给定音频/语音上的 QA、识别、情感或跨模态推理；没有已核实的多轮外部交互任务。 |
| [TS-OPD: Reconciling ASR and QA in Speech Language Models via Task-Specific On-Policy Distillation](https://arxiv.org/abs/2609.29464) | 给定音频/语音上的 QA、识别、情感或跨模态推理；没有已核实的多轮外部交互任务。 |
| [X-OPD: Cross-Modal On-Policy Distillation for Capability Alignment in Speech LLMs](https://arxiv.org/abs/2603.24596) | 给定音频/语音上的 QA、识别、情感或跨模态推理；没有已核实的多轮外部交互任务。 |
| [CORD: Bridging the Audio-Text Reasoning Gap via Weighted On-policy Cross-modal Distillation](https://arxiv.org/abs/2601.16547) | 给定音频/语音上的 QA、识别、情感或跨模态推理；没有已核实的多轮外部交互任务。 |
| [OmniOPSD: Rationale-Privileged On-Policy Self-Distillation for Affective Computing](https://arxiv.org/abs/2606.15920) | 给定音频/语音上的 QA、识别、情感或跨模态推理；没有已核实的多轮外部交互任务。 |
| [OP-CAD: On-Policy Clean-Audio Distillation for Robust Audio-Visual Reasoning](https://arxiv.org/abs/2609.39150) | 给定音频/语音上的 QA、识别、情感或跨模态推理；没有已核实的多轮外部交互任务。 |

## 保留：其他分类

| 分类 | 论文 / 主来源 | 交互与蒸馏证据 |
| :-- | :-- | :-- |
| LLM | [Capable Teacher, Myopic Scorer: Reward-Free Teacher Repair for Agentic On-Policy Distillation](https://arxiv.org/abs/2610.28586) | 多轮智能体学生状态上的教师评分与接管诊断；reward-free teacher repair 用于 OPD。 |
| LLM | [ToolOPD: Credit-Aware On-Policy Distillation for Tool-Use Agents](https://arxiv.org/abs/2610.25693) | 工具执行轨迹及其结果反馈；hindsight skills 调整 OPD 与 RL 的动作信用。 |
| LLM | [MultiAgent-OPD: End-to-End Training of Hierarchical Multi-Agent Systems with On-Policy Distillation](https://arxiv.org/abs/2610.23234) | Leader/Searcher/Answerer 团队执行检索；冻结教师对学生搜索及总结 token 评分。 |
| LLM | [ActionOPD: Distilling Decisions, Not Tokens](https://arxiv.org/abs/2610.19820) | 工具交互中的学生访问状态；以教师采样动作提供语义动作级对齐。 |
| LLM | [State-OPD: State-Grounded On-Policy Distillation for Multi-Turn Agents](https://arxiv.org/abs/2610.13238) | ALFWorld、ScienceWorld、WebShop 的状态变化与后续动作；状态条件 OPD。 |
| LLM | [Stochastic Teacher Intervention for Agentic On-Policy Distillation](https://arxiv.org/abs/2610.10878) | 工具集成推理和长程交互；教师随机介入，并对混合轨迹作重要性加权 reverse-KL。 |
| LLM | [GraphOPD: Graph-Augmented On-Policy Distillation for LLM Agents](https://arxiv.org/abs/2610.08959) | ALFWorld、WebShop、SearchQA 的执行状态变化；依赖图与分布分歧加权 OPD。 |
| LLM | [SCAD: Structured Credit Assignment and Distillation for Long-Horizon Agents](https://arxiv.org/abs/2610.03372) | 长程任务中的规划—子任务执行；执行蒸馏及跨轨迹规划信用。 |
| LLM | [Harness-Aware Distillation for Small Language Model Agents](https://arxiv.org/abs/2610.02858) | 智能体 harness 支持的长程执行；学生推理之后进行 harness 条件教师动作对齐。 |
| LLM | [Beyond the Teacher: Understanding and Preserving Distillation Overshoot in Agentic On-Policy Distillation](https://arxiv.org/abs/2610.25034) | 交互任务中的 distillation overshoot 分析及学生成功决策保护。 |
| LLM | [PivotOPD: Learning to Recover from Pivotal Mistakes in Multi-Turn Agents](https://arxiv.org/abs/2609.40285) | 多轮环境中定位改变后续状态的关键错误；在学生轨迹上结合预防性蒸馏与错误后的恢复蒸馏。 |
| LLM | [Teacher–Student Gaps Are Not Enough: Outcome-Guided On-Policy Distillation for Multi-Turn Autonomous Agents](https://arxiv.org/abs/2609.35319) | 环境中的配对 continuation 结果；按结果收益而非仅局部分布差异调整 OPD。 |
| LLM | [Act First, Reason Later: Accelerating On-Policy Distillation for Multi-Turn Agents via Reference-Conditioned Inverse Dynamics](https://arxiv.org/abs/2609.36608) | ALFWorld、WebShop、ScienceWorld 的动作执行；快速动作与异步教师评分分离。 |
| LLM | [DivOPD: Spread Wide, Look Close for Asynchronous On-Policy Distillation of Multi-turn Agents](https://arxiv.org/abs/2609.34838) | 多轮环境中分配 student rollout/turn 预算；教师分歧加权及可选介入。 |
| Embodied | [Multi-Teacher On-Policy Distillation for Flow-Based Vision-Language-Action Models](https://arxiv.org/abs/2610.21522) | 学生新收集环境交互，同时生成动作 flow；领域教师对学生 flow 状态提供速度监督。 |
| Embodied | [JoyInside-VLM-Agent: Product-Conditioned Multimodal Policy Learning for Embodied Agents](https://arxiv.org/abs/2610.12957) | 机器人/智能硬件执行工具并反馈结果，包含目标修订和失败恢复；multi-teacher OPD 与 DPER。 |
| Embodied | [FastOPD: On-Policy Distillation for Lightweight VLA Deployment](https://arxiv.org/abs/2610.02832) | FastOPD §3 明确在学生生成的动作 flow 状态匹配教师速度；机器人闭环评测。on-policy 指动作生成状态，不能声称训练时持续收集新环境轨迹。 |
| Embodied | [WAM-OPD: Sharpening World Action Models via On-Policy Distillation](https://arxiv.org/abs/2609.34250) | WAM-OPD 使用主要由初始学生收集的固定交互池，回放历史并刷新动作去噪路径；PWTR 近似修正环境历史分布偏移。 |
| Embodied | [VLA-OPD: Bridging Offline SFT and Online RL for Vision-Language-Action Models via On-Policy Distillation](https://arxiv.org/abs/2603.26666) | LIBERO/RoboTwin 机器人动作执行；在学生生成的动作轨迹上用教师 reverse-KL 提供监督。 |
| Embodied | [Refined Policy Distillation: From VLA Generalists to RL Experts](https://arxiv.org/abs/2503.05833) | RPD §III：PPO 学生与环境交互，在学生状态下匹配 VLA 教师动作；属于动作策略蒸馏结合 on-policy RL。迁移方向是 VLA generalist → RL expert。 |
| AGS | [GenEvolve: Self-Evolving Image Generation Agents via Tool-Orchestrated Visual Experience Distillation](https://arxiv.org/abs/2605.21605) | GenEvolve 执行搜索、参考选择和图像生成工具；比较交互轨迹后由特权经验教师提供 token-level 蒸馏。 |
| Embodied | [DriftOPD: Sequence-Level Reverse-KL Distillation for One-Step VLA Policies](https://arxiv.org/abs/2610.00317) | DriftOPD §4.2–4.4：从当前 VLA 采样动作，对示范定义的目标分布做 reverse-KL 近似并用离线 critic 近似未来项；有闭环机器人评测，训练无新环境 rollout/独立教师。 |
| Embodied | [Reflect-VLA: Internalizing Reflective Guidance via Dual-Path On-Policy Self-Distillation for Autonomous Driving](https://arxiv.org/abs/2610.13453) | 驾驶策略同时报告 NAVSIM 与 Bench2Drive；风险学生轨迹上蒸馏反思教师分布，保留可靠轨迹。 |
| Embodied | [RE-0: Verified Recursive Improvement of Embodied Code-as-Policy Agents through Local On-Policy Distillation](https://arxiv.org/abs/2609.32416) | 具身代码实际执行并在环境中验证局部教师干预；只将有益纠正转为 RE-OPD 分布监督。 |
| Embodied | [WAM-OPD: Joint Video-Action Supervision for World Action Model Post-Training with On-Policy Distillation](https://arxiv.org/abs/2608.22364) | 收集学生机器人执行历史，教师提供配对视频和动作目标；仿真及真实机器人任务成功评测。 |
| Embodied | [ROAD-VLA: Robust Online Adaptation via Self-Distillation for Vision-Language-Action Models](https://arxiv.org/abs/2606.25800) | 在线机器人适应；优势校准的动作空间 proximal teacher 提供密集自蒸馏。 |
| Embodied | [FORCE: Efficient VLA Reinforcement Fine-Tuning via Value-Calibrated Warm-up and Self-Distillation](https://arxiv.org/abs/2606.26006) | FORCE §3.3：在线交互状态中对当前策略动作采样，构造 Q 加权目标分布并投影回策略；明确标为 value-guided policy self-distillation。 |
| LLM | [SD-Search: On-Policy Hindsight Self-Distillation for Search-Augmented Reasoning](https://arxiv.org/abs/2605.18299) | 实际搜索与检索结果；hindsight 条件自教师监督学生查询。 |
| LLM | [OPD-Evolver: Cultivating Holistic Agent Evolver via On-Policy Distillation](https://arxiv.org/abs/2606.17628) | 记忆系统的读取、使用、写入和维护操作；结果归因及特权 hindsight 蒸馏。 |

## 一致性修正与核验边界

- 将 RPD 的迁移方向更正为 VLA generalist → compact RL expert；原速览中“RL-induced changes back to generalist”与原文相反。
- 对 GHD、FastOPD、DriftOPD、固定池 WAM-OPD 和 FORCE 补充方法标签及限制，避免将离线上下文、动作 flow 或 value-guided 投影写成实时环境 rollout。
- arXiv 标识符与返回标题未发现实质不匹配；此次没有刷新 stars、citations 或文献日期，也未做作者单位/代码可用性的完整审计。
- 严重程度：原清单存在系统性的范围扩张；本次已同步修正数据源、统计缓存及两个生成页面。
- No-invention：范围判断依据作者摘要及上述正文段落；SOPD-SocialNav 明确记录为闭环证据不足，不将缺失证据写成“已证伪”。
- 后续新增论文须同时说明实际交互接口、返回观察/反馈和 OPD 对齐目标；没有证据的条目不因标题关键词重新加入。无需其他 CCFA 阶段即可完成本次范围清理。
