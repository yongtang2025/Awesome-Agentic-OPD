# Agentic OPD 收录范围核验

## LLM 补检：SDAR 与引用追踪（2026-10-22）

**当前结果：LLM Agentic OPD 16 → 78 篇，新增 62 篇；全目录 38 → 100 篇。** 其他分类维持 Multimodal 9、Embodied 12、Video 0、Audio 0、AGS 1。新增数按独立 arXiv ID 计数，其中含 1 篇专项比较评测研究，不将其写成新算法。

种子来源：[SDAR 仓库](https://github.com/ZJU-REAL/SDAR)。其 “Awesome Work Powered by SDAR” 有 21 个不同论文 ID，加上 SDAR 本身共 22 篇，与补检前的 16 篇 LLM 条目没有重合；本轮全部纳入。另外通过已有索引及引用追踪核实 40 篇。GitHub 直连失败后，使用 [master 分支的 README 镜像](https://cdn.jsdelivr.net/gh/ZJU-REAL/SDAR@master/README.md) 读取清单，并逐篇回到 arXiv 主来源核验。

覆盖：筛查 110 个未在原目录中的候选，逐条读取 arXiv 摘要；对 34 篇取得正文并重点检查相关方法/评测段落。扩展入口使用同日已有 OpenAlex 检索结果及论文引用；本轮新增 OpenAlex 请求返回 429，因此不声称穷尽全部文献。这里记录的是收录范围判断，不是全文科学审稿或实验复现。

筛选同时要求任务交互与 on-policy 蒸馏证据。交互可来自环境、工具、数据库、代码执行、用户模拟器，或独立智能体之间影响下一轮决策的消息；单模型内部推理或教师侧讨论本身不足以确立 Agent 任务。OPD 可以表现为分布/表示/动作对齐、教师在学生访问状态上的纠正，或基于学生 rollout 重评分的密集信用信号；相应实现类型在网页中分别标注。

边界处理：MAS-OPD 属于独立角色策略间的通信闭环；ReOPD/OEL/ReSAIL 区分固定环境历史与新采样的学生回答；WebKD 区分固定学生访问状态上的逐状态纠正与教师接管后产生新状态的 continuation SFT；OVD 明确标注仍使用推理期教师反馈的设置。SDAR 中的 credit-shaping 方法不统一描述为独立 reverse-KL 损失。

元数据：题名、arXiv ID 和日期由主来源确认；代码链接来自论文或 SDAR 的明确链接。未核实的单位填 `—`；新增 stars/citations 填空值，不以 0 代替未知。

### SDAR 入口：22 篇全部覆盖

| 论文 / 主来源 | 方法类型 | 交互与蒸馏依据 |
| :-- | :-- | :-- |
| [Self-Distilled Agentic Reinforcement Learning](https://arxiv.org/abs/2605.15155) | OPSD+RL | 环境动作和反馈构成多轮轨迹；技能条件自教师重评分学生 token，门控蒸馏与 RL 联合优化。 |
| [Beyond Timestamps: Decision-Aligned On-Policy Distillation for Long-Horizon Agents](https://arxiv.org/abs/2609.33391) | OPSD-guided RL: decision credit | 真实交互轨迹中按功能决策对齐同胞 rollout；学生动作的特权重评分用于分层信用分配。 |
| [PR-OPD: Privileged Representation On-policy Self-Distillation for Agentic Reinforcement Learning](https://arxiv.org/abs/2609.36642) | representation OPSD+RL | ALFWorld/WebShop 交互；同一学生回答上的隐藏表示蒸馏，不能因没有 token-logit loss 而遗漏。 |
| [UniOPSD: Unifying Outcome and Hindsight Feedback for Agentic Reinforcement Learning](https://arxiv.org/abs/2609.34810) | OPSD-guided RL: credit arbitration | 环境回报与学生交互锚点上的 hindsight 自蒸馏共同构造决策信用。 |
| [RetireOPD: Self-Retiring On-Policy Distillation for Agentic Reinforcement Learning](https://arxiv.org/abs/2609.20784) | OPD+RL | 环境中先训练技能教师，再在学生交互轨迹上联合 OPD/RL，并自适应停止蒸馏。 |
| [Reconciling Process Supervision with Outcome-Based Credit in Agentic Policy Optimization](https://arxiv.org/abs/2608.31077) | OPSD-guided RL: action credit | 可执行动作上的特权似然差用于重分配 RL 信用；属于交互式 OPSD 信号引导的训练。 |
| [AHEAD: Adaptive Hindsight with Environment-Augmented Distillation for Agentic RL](https://arxiv.org/abs/2608.24114) | OPSD+RL | 学生执行动作并接收环境反馈；错误步骤另加教师纠正提示进行自蒸馏。 |
| [Trust Is Not Enough: Influence Calibration for On-Policy Self-Distillation in Agentic RL](https://arxiv.org/abs/2608.14945) | OPSD+RL | 学生交互轨迹上的特权教师监督，用 RL 目标的局部影响校准 token 蒸馏权重。 |
| [Bidirectional Context Self-Distillation for Reinforcement Learning of Skill-Based LLM Agents](https://arxiv.org/abs/2608.09555) | OPSD-guided RL: context contrast | 在实际环境轨迹上用两种技能上下文重评分，并将自蒸馏信号并入 RL。 |
| [AgentOPSD: Recursive Self-Distillation for Agentic Reinforcement Learning](https://arxiv.org/abs/2608.05987) | OPSD-guided RL: recursive credit | 学生动作—观察轨迹上聚合教师差值，并递归更新 turn-level 信用。 |
| [Agentic Reinforcement Learning with Observation-Calibrated Self-Distillation](https://arxiv.org/abs/2608.04788) | OPSD-guided RL: observation residual | 真实环境未来观察用于训练期反事实重评分；学生 token 上的自蒸馏残差信号指导 RL。 |
| [Agentic Reinforcement Learning with Self-Distilled Reward Shaping](https://arxiv.org/abs/2608.03223) | OPSD-guided RL: reward shaping | 无技能学生交互轨迹上重评分固定动作 token，以回报相关性门控并形成密集信用。 |
| [PCSD: Persistent Consistency for Self-Distillation in Agentic Reinforcement Learning](https://arxiv.org/abs/2608.01837) | OPSD+RL | 多轮环境轨迹上以持续一致的教师信号加权 on-policy 自蒸馏。 |
| [Group-Reflective Self-Distillation for Agentic Reinforcement Learning](https://arxiv.org/abs/2607.28076) | OPSD-guided RL: group reflection | 当前策略的成功/失败交互组形成特权反思，由自教师重评分并校准 turn 信用。 |
| [From Scoring to Acting: Outcome-Verified Comparative Self-Distillation for LLM Agents](https://arxiv.org/abs/2607.27937) | outcome-verified self-distillation+RL | 教师从学生访问状态实际执行并验证结果；局部比较学习加后缀蒸馏，非仅筛选整条成功轨迹。 |
| [From Proprietary to Open-Source: Bridging the Distribution Gap via Multi-Agent Protocol Distillation in Agentic Search](https://arxiv.org/abs/2607.24280) | OPSD+RL | 学生交替推理与检索；协议条件自教师提供学生轨迹上的 token 分布监督。 |
| [SEED: Self-Evolving On-Policy Distillation for Agentic Reinforcement Learning](https://arxiv.org/abs/2607.14777) | OPSD+RL | 当前智能体产生交互轨迹并提炼技能；其概率变化形成 on-policy 密集蒸馏信号。 |
| [UCOB: Learning to Utilize and Evolve Agentic Skills via Credit-Aware On-Policy Bidirectional Self-Distillation](https://arxiv.org/abs/2606.29502) | bidirectional OPSD+RL | 同一任务/状态下执行双上下文策略，以环境回报确定局部蒸馏方向。 |
| [CRAFT: Counterfactual Credit Assignment from Free Sibling Rollouts for Self-Distilled Agentic Reinforcement Learning](https://arxiv.org/abs/2606.29476) | OPSD+RL | 交互式学生同胞 rollout 的结果提供反事实信用，并调节特权自蒸馏。 |
| [ATOD: Annealed Turn-Aware On-Policy Distillation for Multi-Turn Agentic Tasks](https://arxiv.org/abs/2606.27814) | OPD+RL | 实际环境中的多轮学生轨迹，采用 OPD/RL 退火和 turn-level 蒸馏重加权。 |
| [OPID: On-Policy Skill Distillation for Agentic Reinforcement Learning](https://arxiv.org/abs/2606.26790) | OPSD+RL | 来自当前交互轨迹的分层技能指导同一学生动作 token 的 on-policy 重评分。 |
| [StepOPSD: Step-Aware Online Preference Self-Distillation for Agent Reinforcement Learning](https://arxiv.org/abs/2605.27140) | OPSD-guided RL: step credit | 以环境动作步骤分解学生交互轨迹，将 hindsight 蒸馏信号转为 step-level 信用。 |

### 扩展检索：新增 40 篇

| 论文 / 主来源 | 方法类型 | 交互与蒸馏依据 |
| :-- | :-- | :-- |
| [Know When to Stop, Where to Restart: Accelerating Multi-Turn Agentic On-Policy Distillation](https://arxiv.org/abs/2609.14636) | OPD | tau2-bench 用户/工具交互，按教师支持度停止并从交互前缀重启 OPD。 |
| [Look Ahead Before You Distill: Future Trajectory Validation of Teacher Guidance for Agentic On-Policy Distillation](https://arxiv.org/abs/2608.01953) | OPD | 教师桥接与学生续行均在环境中执行，以未来轨迹验证 OPD 指导。 |
| [UOPD: Uncertainty-Aware Intervention for On-Policy Distillation of Multi-Turn Agents](https://arxiv.org/abs/2609.34036) | OPD with teacher intervention | 学生及教师动作实际改变环境；保留学生 turn 的 OPD，并在不确定步骤执行纠正。 |
| [SOD: Step-wise On-policy Distillation for Small Language Model Agents](https://arxiv.org/abs/2605.07725) | OPD | TIR 学生实际调用工具并接收结果；逐交互步骤调整 on-policy 蒸馏强度。 |
| [On-Policy Distillation with Curriculum Turn-level Guidance for Multi-turn Agents](https://arxiv.org/abs/2606.15912) | OPD with curriculum intervention | 环境中混合执行教师/学生 turn，并按课程退火到学生自身交互。 |
| [MAD-OPD: Breaking the Ceiling in On-Policy Distillation via Multi-Agent Debate](https://arxiv.org/html/2605.01347v1) | multi-teacher OPD | 正文 §4/App.B 记录用户模拟器及最多 300 个环境步；学生工具交互上的多教师 OPD。 |
| [TCOD: Exploring Temporal Curriculum in On-Policy Distillation for Multi-turn Autonomous Agents](https://arxiv.org/abs/2604.24005) | OPD | 在三类环境中采样学生动作—观察轨迹，按交互深度实施 OPD 课程。 |
| [SAGE-OPD: Selective Agent-Guided Intervention for Multi-Turn On-Policy Distillation](https://arxiv.org/abs/2606.19659) | OPD | 先观察动作执行反馈，再决定哪些学生 turn 接受置信度加权蒸馏。 |
| [MemOPD: On-Policy Distillation through Memory State Alignment for Long-Horizon Agents](https://arxiv.org/html/2608.07068v1) | OPD+RL | 多轮智能体的记忆改写与外部交互；在每次真实调用的学生动作位置上作状态对齐蒸馏。 |
| [TurnOPD: Making On-Policy Distillation Turn-Aware for Efficient Long-Horizon Agent Training](https://arxiv.org/abs/2607.05804) | OPD | 真实环境交互上联合控制 rollout 深度与按 turn 分配的 OPD 损失。 |
| [OPRD: On-Policy Reminder Distillation for Long-Horizon Coding Agents](https://arxiv.org/abs/2610.21496) | OPSD | 代码智能体使用仓库工具及测试反馈；失败学生轨迹上实施 reminder-conditioned reverse-KL。 |
| [Graph-Conditioned On-Policy Agent Distillation from Off-the-Shelf Teachers](https://arxiv.org/abs/2609.37522) | OPD | 执行图中的环境历史增强教师上下文，监督学生自身交互中的 thought/action token。 |
| [GAPD: Gold-Action Policy Distillation for Agentic Reinforcement Learning in Knowledge Base Question Answering](https://arxiv.org/abs/2605.29584) | OPSD+RL | 学生执行知识库查询并观察实体反馈；状态锚点对齐后进行动作 token 自蒸馏。 |
| [Keep Policy Gradient in Charge: Sibling-Guided Credit Distillation for Long-Horizon Tool-Use Agents](https://arxiv.org/abs/2606.12634) | OPSD-guided RL: credit weighting | AppWorld/tau3 的工具反馈闭环；学生同胞轨迹上的教师分歧构造有界 RL 信用。 |
| [The Physics of Multi-Turn Long-Horizon Planning: From Pre-training to Post-training via Single- and Multi-Teacher On-Policy Agentic Distillation](https://arxiv.org/html/2607.24720v1) | analysis+multi-teacher OPD | 正文 §2–3 的库存状态随合成动作更新；OPAD 在学生自探索交互轨迹上优化。 |
| [Branching On-Policy Distillation](https://arxiv.org/abs/2610.13481) | OPD | ALFWorld/WebShop 的 turn 内决策分支与后续环境行为；对学生分支施加 OPD。 |
| [Step-Level On-Policy Distillation: Interpolating Between On-Policy Distillation and Supervised Fine-Tuning](https://arxiv.org/html/2608.16333v1) | step-level OPD | 包含真实 ALFWorld 交互评测，以学生轨迹条件构造 step-level 蒸馏。 |
| [Multi-Turn On-Policy Distillation with Prefix Replay](https://arxiv.org/abs/2607.04763) | OPD on replayed interaction prefixes | 学生在回放的工具历史上重新采样回答并接受教师监督；交互任务闭环评测，训练不新执行工具。 |
| [Building Multi-Task Agentic LLMs via Two-Phase Distillation](https://arxiv.org/html/2606.30044v1) | off-policy initialization + OPD | 对话与文本游戏智能体的多任务整合；明确包含后续 on-policy 策略蒸馏阶段。 |
| [SecOPD: Mitigating Adaptive Prompt Injections by On-Policy Distillation](https://arxiv.org/html/2608.21500v1) | OPD with agentic transfer evaluation | 正文 App.H 采用 AgentDojo v1.2.1 的实际工具任务与执行成功指标；不能仅因训练输入离线而排除。 |
| [RISE: Recursive Improvement via Self-Extrapolating Policy Distillation](https://arxiv.org/html/2609.05295v1) | self-extrapolating OPD+RL | 正文 agentic 设置为 ALFWorld/WebShop；当前学生 rollout 上匹配自外推教师。 |
| [Dense Is Not Enough: Hierarchical Supervision Allocation for Long-Horizon On-Policy Distillation](https://arxiv.org/html/2609.33409v1) | OPD | 教师干预收益由环境中的后续学生行为验证，再实施分层 OPD。 |
| [DTDD: Divergence-Triggered Dynamic Distillation for Reliable On-Policy Supervision](https://arxiv.org/abs/2610.19302) | OPD with teacher recovery | ALFWorld/代码智能体中执行教师恢复；保留学生前缀 OPD，教师段另用行为克隆。 |
| [Revisiting On-Policy Distillation: Empirical Failure Modes and Simple Fixes](https://arxiv.org/html/2603.25562v2) | analysis+OPD | 正文 §4.3 与 App.G.1 明确在 ALFWorld/WebShop 训练和评测学生策略。 |
| [On-Policy Context Distillation for Language Models](https://arxiv.org/html/2602.12275v2) | on-policy context distillation | 正文训练与评测包含 TextArena 的 Frozen Lake/Sokoban 动作反馈闭环。 |
| [TIDE: Teacher-Student Transition via Informative Distillation and Exploration for Agentic RL](https://arxiv.org/abs/2609.35058) | OPD+RL | 交互式多轮任务中协调 OPD 与 RL，按动作价值和分歧分配 turn 监督。 |
| [f-OPD: Stabilizing Long-Horizon On-Policy Distillation with Freshness-Aware Control](https://arxiv.org/abs/2605.17862) | asynchronous OPD | 工具与代码智能体的长交互轨迹上研究异步 OPD；控制 rollout/context 的陈旧偏移。 |
| [Latent On-Policy Self-Distillation](https://arxiv.org/html/2608.13040v1) | latent-context OPSD | 以任务与交互历史采样学生轨迹，latent-context 自教师提供逐前缀监督。 |
| [When Privileged Guidance Misaligns: State-Matched Routing and Contextualized Self-Distillation for Multi-Turn Agents](https://arxiv.org/abs/2608.05219) | OPSD+RL | 根据学生实际到达的环境状态匹配参考，再对当前学生回答进行自蒸馏。 |
| [ReSAIL: Mitigating Collapse in Iterative Agent Self-Distillation](https://arxiv.org/html/2609.39306v1) | OPSD on offline interaction histories | 正文 §3.1 明确 OEL 集成每次更新重新采样学生回答；保留该 on-policy 分支并注明回放历史。 |
| [More Methods, Better Agents? A Reality Check on Self-Distillation in Agentic Reinforcement Learning](https://arxiv.org/abs/2610.19789) | benchmark / comparative study | 纯比较/基准论文，直接复评交互式 Agentic OPSD；计为论文，不能计作新算法。 |
| [RISED: RubrIcs for agentic multi-environment Selection and sElf-Distillation](https://arxiv.org/html/2610.00979v1) | OPSD+RL | 跨交互环境采样学生 rollout，以正向 rubric 条件自教师提供 token-level OPSD。 |
| [Skill-SD: Skill-Conditioned Self-Distillation for Multi-turn LLM Agents](https://arxiv.org/html/2604.10674v1) | OPSD+RL | AppWorld/Sokoban 实际交互；学生轨迹上技能条件教师的 importance-weighted reverse-KL。 |
| [SERL-SQL: Selective Hindsight Distillation for Text-to-SQL Reinforcement Agentic Learning](https://arxiv.org/html/2608.00485v4) | OPSD-guided RL: execution credit | 正文定义数据库 action-observation 多轮轨迹，执行反馈用于学生 SQL/tool token 的自蒸馏信用。 |
| [MAS-OPD: On-Policy Distillation for Multi-agent Systems](https://arxiv.org/html/2609.34234v1) | joint multi-agent OPD | 正文 §2.1 为独立学生策略之间的多轮通信反馈闭环；联合轨迹上的 OPD，不是单模型内部 CoT。 |
| [OVD: On-policy Verbal Distillation](https://arxiv.org/html/2601.21968v2) | verbal mixed-policy distillation+RL | 正文 App.A.10 明确训练期搜索模拟器与测试期 Serper 搜索交互；需区分推理时仍有教师的配置。 |
| [Online Experiential Learning for Language Models](https://arxiv.org/html/2603.16856) | on-policy context distillation from deployment | 部署交互轨迹提炼经验，当前学生采样的回答接受 OPCD；正文评测 Frozen Lake/Sokoban。 |
| [DASH-OPD: Discrepancy-Aware Switching with Hysteresis for On-Policy Distillation](https://arxiv.org/abs/2607.29078) | OPD with bidirectional intervention | 学生/教师在环境交互中双向切换执行，按连续 turn 的分歧证据进行 on-policy 蒸馏。 |
| [From Imitation to Reward Discovery: On-Policy Warmup for Agentic RL](https://arxiv.org/abs/2609.39436) | OPD warmup + RL | 先在学生自己访问的交互状态上进行 reverse-KL 蒸馏，再切换到 Agentic RL。 |
| [Teaching Agents in their Own Style: Blackbox Teacher Distillation for Web Agents](https://arxiv.org/html/2610.19834v1) | state-level distillation on collected student rollouts | 正文明确每个教师改写都对齐学生实际访问的状态，避免教师接管后的新状态；以固定学生状态池上的动作级蒸馏收录并注明。 |

### 未计入本轮 LLM 数量的 48 篇

“证据不足”表示暂缓收录；“其他分类候选”不表示其不属于 Agentic OPD。尤其不能把 REOPOLD 的视觉工具实验写成非 Agent。

| 候选 / 主来源 | 未计入原因 |
| :-- | :-- |
| [Harness Policy Distillation: Aligning Agent Policies with Runtime Semantics](https://arxiv.org/abs/2610.20261) | 有 harness 交互，但检查到的方法以参考轨迹回放和教师动作/控制语义监督为主；未核实学生采样轨迹上的 OPD 目标。 |
| [Internalizing Agent Experience into Diffusion Model Weights via On-Policy Context Distillation](https://arxiv.org/abs/2610.07250) | 蒸馏目标是图像扩散生成器，不能将外部 harness 的存在直接计作 LLM Agent 策略 OPD。 |
| [Formal Verification of Learned Multi-Agent Communication Policies via Decision Tree Distillation](https://arxiv.org/abs/2606.19632) | 多机器人通信策略的决策树抽象与形式验证；非 LLM Agentic OPD 研究。 |
| [Trust Region On-Policy Distillation](https://arxiv.org/abs/2606.01249) | 正文/摘要评测数学、代码生成与通用任务，未定位到动作执行后的反馈闭环。 |
| [Inductive Feedback for Mixed-Policy Distillation](https://arxiv.org/html/2609.35390v1) | ToolAlpaca 是静态调用预测；交互证据来自具身视觉语言规划器 EmbodiedEval，作为具身候选记录，不计入本轮 LLM 数量。 |
| [TIP: Token Importance in On-Policy Distillation](https://arxiv.org/html/2604.14084v4) | 报告 DeepPlanning，但所查段落未说明该实验实际执行工具及返回观察的配置；暂不计入，不能仅凭 agentic planning 标签认定。 |
| [Scaling Reasoning Efficiently via Relaxed On-Policy Distillation](https://arxiv.org/html/2603.11137v1) | REOPOLD 正文确有视觉工具交互（VerlTool/Pixel-Reasoner）；属于多模态 Agentic OPD 候选，本轮不计入 LLM。 |
| [A Survey of On-Policy Distillation for Large Language Models](https://arxiv.org/abs/2604.00626) | 通用 LLM OPD 综述，非专门的交互式 Agentic OPD 文献或其专项评测。 |
| [Distillation as Probability Transport: Routed On-Policy Distillation](https://arxiv.org/abs/2609.08337) | RouteOPD 的已核实实验为数学推理。 |
| [Contrastive On-Policy Distillation](https://arxiv.org/abs/2607.19046) | COPD 的已核实实验为固定输入多模态推理/理解。 |
| [On the Off-Policy Teacher in On-Policy Distillation](https://arxiv.org/abs/2609.38360) | SCOUT 摘要描述推理领域，未定位到交互式 Agent 实验；保留为待进一步核验的通用 OPD 候选。 |
| [OPRD: On-Policy Representation Distillation](https://arxiv.org/abs/2606.06021) | On-Policy Representation Distillation 的实验为数学；不同于收录的 coding-agent On-Policy Reminder Distillation。 |
| [OPOD: On-Policy Omni Distillation](https://arxiv.org/abs/2607.20918) | OPOD 是固定输入的全模态能力整合，未建立 Agent 交互闭环。 |
| [Trust Region Policy Distillation](https://arxiv.org/abs/2607.04751) | TOP-D 的已核实实验为数学推理。 |
| [On-policy Distillation with Verifiable Reward](https://arxiv.org/abs/2608.24696) | OPDVR 的已核实实验为推理基准，未提供 Agent 执行反馈证据。 |
| [Weak-to-Strong On-Policy Distillation](https://arxiv.org/abs/2607.26246) | W2S-OPD 原文主要评测数学与代码生成；不能把后续论文的 Agent 移植反算为原文证据。 |
| [Training-Free On-Policy Distillation](https://arxiv.org/abs/2610.22236) | 训练自由的专家合并，原文评测数学与单次代码生成。 |
| [Are Full Rollouts Necessary for On-Policy Distillation?](https://arxiv.org/abs/2605.31490) | POPD/TOPD 的 rollout horizon 是数学输出长度，不是已核实的环境交互深度。 |
| [Flash-OPD: Fast On-Policy Distillation](https://arxiv.org/html/2610.06105v1) | Flash-OPD 正文训练 DAPO-Math，评测数学与 GPQA；其 closed-loop controller 指训练控制，不是 Agent 环境。 |
| [Policy Alignment: New Signals for Membership Auditing in On-Policy Distillation](https://arxiv.org/abs/2610.11423) | 成员推断/隐私审计方法，未建立交互式 Agent OPD 任务。 |
| [Escaping the KL Agreement Trap in On-Policy Distillation](https://arxiv.org/abs/2606.09471) | KAT 的已核实实验为数学推理。 |
| [CV-OPD: Contrastive Vision On-policy Distillation](https://arxiv.org/abs/2610.13264) | CV-OPD 的视觉对比监督用于静态图像推理，未建立工具/环境闭环。 |
| [Scaling Properties of Same-Family On-Policy Distillation](https://arxiv.org/abs/2609.32722) | 通用同族模型 OPD 缩放研究；当前摘要证据不足以确认 Agent 交互实验。 |
| [ResOPD: Tail Residualization for Sparse On-Policy Distillation](https://arxiv.org/html/2610.04882v1) | ResOPD 正文评测数学、科学问答和单次代码生成。 |
| [Flux-OPD: On-Policy Distillation with Evolving Contexts](https://arxiv.org/html/2607.28022v2) | Flux-OPD 主要评测视频提示词优化与医学 QA；未核实被训练学生的连续行动反馈闭环。 |
| [Interactive-Policy Distillation with Bidirectional Propose-and-Verify](https://arxiv.org/abs/2609.36546) | IPD 的 interactive 指教师/学生协作生成数学推理；没有已核实的部署 Agent 交互任务。 |
| [Pass the Baton: Trajectory-Relayed On-Policy Distillation](https://arxiv.org/abs/2607.26057) | Relay-OPD 的已核实实验为八个数学基准。 |
| [Unbiased Top-$k$ Estimation for On-Policy Distillation](https://arxiv.org/html/2609.34447v2) | TT-OPD 正文评测数学与代码生成，未建立 Agent 执行反馈闭环。 |
| [OPD+: Rethinking the Advantage Design for On-Policy Distillation](https://arxiv.org/html/2606.01039v1) | OPD+ 工具实验采用 ToolAlpaca 的 68 题调用预测设置；未核实执行后返回观察的多轮协议。 |
| [Demystifying On-Policy Distillation: Roles, Pathologies, and Regulations](https://arxiv.org/html/2607.13399v1) | Demystifying OPD 正文的七个基准为数学推理。 |
| [AsyncOPD: How Stale Can On-Policy Distillation Be?](https://arxiv.org/html/2606.24143v1) | AsyncOPD 正文主要评测数学，异步 rollout 不是环境交互证据。 |
| [LiteGUI: Lightweight GUI Agents via Multi-Solution Guided Distillation and Dual-Level Reinforcement Learning](https://arxiv.org/abs/2605.07505) | LiteGUI 是多模态 GUI 候选，不计入本轮 LLM；其具体闭环评测仍需单独核查。 |
| [SAGE-32B: Agentic Reasoning via Iterative Distillation](https://arxiv.org/abs/2601.04237) | SAGE-32B 的迭代轨迹蒸馏未核实为学生采样上的 OPD 目标。 |
| [FailForge: Distilling Procedural Competence from Persistent Failures into Code Agents](https://arxiv.org/abs/2608.08570) | FailForge 通过失败恢复扩充代码训练语料；未核实独立 OPD 对齐目标。 |
| [Skill-Guided Continuation Distillation for GUI Agents](https://arxiv.org/abs/2606.18890) | GUI SGCD 对教师接管后的成功 continuation 做 SFT；沿用首轮排除结论。 |
| [MMG2Skill: Can Agents Distill In-the-Wild Guides into Self-Evolving Skills?](https://arxiv.org/abs/2606.01993) | MMG2Skill 更新外部可编辑技能并保持执行模型固定，非参数层面的 Agent OPD。 |
| [DENSE: Distilling Agent Trajectories into Evidence-Grounded Shortcut Trees for Self-Refinement](https://arxiv.org/abs/2609.21423) | DENSE 将经验编为反馈树以辅助重试，未核实 OPD 策略更新。 |
| [DART-SD: Diamond-topology Aware Retrieval and Tuning for Self-Distillation of Multi-Turn Tool-Calling Agents](https://arxiv.org/html/2608.18524v1) | DART-SD 正文 §3.3–3.4 为教师参考条件生成恢复段后的 masked SFT，非学生采样回答上的 OPD 重评分。 |
| [AliyunConsoleAgent: Training Web Agents in Real-World Cloud Environments via Distillation and Reinforcement Learning](https://arxiv.org/abs/2606.09447) | AliyunConsoleAgent 采用轨迹蒸馏与 RL；所查证据未建立 on-policy 蒸馏目标。 |
| [DeepSearch-World: Self-Distillation for Deep Search Agents in a Verifiable Environment](https://arxiv.org/abs/2607.07820) | DeepSearch-Evolve 是生成、筛选、混合和 SFT；沿用首轮排除结论。 |
| [From Verbatim to Gist: Distilling Pyramidal Multimodal Memory via Semantic Information Bottleneck for Long-Horizon Video Agents](https://arxiv.org/abs/2603.01455) | 多模态视频记忆蒸馏，非本轮 LLM Agentic OPD 范围，且未核实动作反馈闭环。 |
| [Agent Memory Distillation: Empowering Small LLM Agents with Hierarchical Teacher Memory](https://arxiv.org/abs/2608.07169) | AMD 将教师经验编为运行时记忆，未核实学生策略的 on-policy 参数蒸馏。 |
| [SKILL0: In-Context Agentic Reinforcement Learning for Skill Internalization](https://arxiv.org/abs/2604.02268) | Skill0 是技能上下文课程与 RL，不能仅以 skill internalization 视为 OPD。 |
| [Skill1: Unified Evolution of Skill-Augmented Agents via Reinforcement Learning](https://arxiv.org/html/2605.06130) | Skill1 的 skill distillation 指从轨迹生成技能文档；未建立学生-教师策略分布 OPD。 |
| [SkillRise: Agentic Reinforcement Learning for Cross-Task Skill Evolution](https://arxiv.org/abs/2607.26784) | SkillRise 是跨任务技能维护与 RL，未核实 OPD 监督。 |
| [Agent-G$^2$: Gaussian Guidance for Agentic Reinforcement Learning](https://arxiv.org/abs/2608.23318) | Agent-G2 的前缀提示与深度采样服务于 RL，未核实 OPD 目标。 |
| [Reinforcement Learning via Self-Distillation](https://arxiv.org/html/2601.20802) | SDPO 原文工具部分是静态 ToolAlpaca 调用预测；代码反馈/测试时适应不直接等于本清单的多轮 Agent 执行策略，暂不计入。 |
| [Self-Distilled RLVR](https://arxiv.org/html/2604.03128) | RLSD 原文实验为静态多模态推理；SDAR 对其做 Agent 适配不改变原文范围。 |

## 首轮范围清理记录（补检前）

以下为之前从 102 篇筛至 38 篇的历史记录；其中的 16 篇 LLM 数量不是补检后的当前数量。

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
