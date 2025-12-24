# Agent-Study 进度追踪器 (Study Tracker)

## 📊 学习进度概览

**开始日期:** 2025-12-16  
**最后更新:** 2025-12-24  
**当前阶段:** 多智能体协作深化 + 通用规则模板提炼  
**总体完成度:** 0/5 大模块  
**技能树点亮率:** 2/19 主题 (已掌握 B.1 ReAct、C.1 Handoffs，B.2/B.3/D.2 实践中)

## 🧭 领域进度摘要 (Domain Progress Summary)

| 领域 | 权重 | 已覆盖主题数 | 已掌握主题数 | 状态 | 优先级 |
| ---- | ---- | ------------ | ------------ | ---- | ------ |
| A. Foundations | 15% | 0/4 | 0 | 未开始 | 中 |
| B. Core Patterns | 30% | 3/4 | 1 | 进行中 | 高 |
| C. Multi-Agent | 25% | 2/4 | 0 | 初步接触 | 高 |
| D. Memory & State | 20% | 1/4 | 0 | 初步接触 | 中 |
| E. Ops & Eval | 10% | 0/3 | 0 | 未开始 | 低 |

---

## 🎯 知识体系清单 (Syllabus Checklist)

### A. 基础认知与 Prompt 进阶 (Foundations) - 15%

- [ ] A.1 Chain of Thought (CoT): 推理的原子单位,理解 Test-time Compute 的意义
- [ ] A.2 Few-Shot In-Context Learning: 示例的选择与排序策略
- [ ] A.3 Structured Output: JSON Mode, Function Calling, 与 Pydantic Parser 的原理
- [ ] A.4 Prompt Chaining: 线性工作流的局限性与适用场景

### B. 核心编排模式 (Core Patterns) - 30% ⭐ 最高优先级

- [x] B.1 ReAct (Reason+Act): 循环（Loop）的核心机制,Thought-Action-Observation 三元组
- [ ] B.2 Plan-and-Solve (Planner): 复杂任务的拆解、DAG 图的生成与执行
- [ ] B.3 Reflection / Self-Correction: 自我反思机制,如何让 LLM 当自己的 Reviewer
- [ ] B.4 Tool Use / Function Calling: 接口定义（OpenAPI Spec）,工具调用的容错处理

### C. 多智能体架构 (Multi-Agent Architecture) - 25%

- [ ] C.1 Handoffs (路由与移交): 像客服转接一样处理任务,状态（State）如何在 Agent 间传递
- [ ] C.2 Supervisor (监督者模式): 集中式管理,Router Agent 的设计
- [ ] C.3 Hierarchical Teams: 层级化团队结构 (CrewAI/Hierarchical Graph) 的实现
- [ ] C.4 Multi-Agent Debate: 通过多角色互斥观点提升准确率

### D. 记忆与状态管理 (Memory & State) - 20%

- [ ] D.1 Short-term vs Long-term Memory: 滑动窗口、摘要压缩与向量库检索（RAG Memory）
- [ ] D.2 State Graph: 像有限状态机（FSM）一样管理对话状态 (LangGraph 核心概念)
- [ ] D.3 Checkpointer: 持久化存储（SQLite/Postgres）,断点续传与"时光倒流"（Time Travel）
- [ ] D.4 Context Management: 在长对话中如何避免 Context Window 爆炸

### E. 评估与工程化 (Ops & Eval) - 10%

- [ ] E.1 Agent Evaluation: 怎么判断 Agent 变聪明了?(Ragas, LangSmith, DeepEval)
- [ ] E.2 Tracing: 链路追踪,如何 Debug 一个死循环的 Agent
- [ ] E.3 Cost & Latency: Token 消耗优化与响应速度平衡

---

## 🏆 已掌握主题 (Mastered Topics)

主题 | 掌握日期 | 信心水平 | 核心见解
--- | --- | --- | ---
B.1 ReAct | 2025-12-17 | 中 | 理解 Thought-Action-Observation 循环与 Router/Planner/Reflection 分工, 能设计出基于需求文档助手的 ReAct+验证架构
C.1 Handoffs - 多智能体路由与移交 | 2025-12-23 | 高 | 基于真实需求完整回放，提炼出通用四层移交协议（意图→功能→表现→文档），建立信息分层原则（通用规则+特殊约束），掌握摩擦策略（先直接用→看效果→再调整）

---

# 🔍 知识盲区 (Knowledge Gaps)

主题 | 严重程度 | 状态 | 备注
--- | --- | --- | ---
ReAct 在 LangGraph 中的 State Graph/节点建模与接口设计 | 中 | 未解决 | 还没有在具体框架中实践, 不清楚节点接口与持久化策略
ReAct+验证层落地到真实需求平台 (Jira/需求系统) 的权限/超时/错误重试设计 | 中 | 未解决 | 目前仅有概念架构, 缺少具体方案
Reflection/Critic 自我审查的审稿标准设计 | 低 | 已解决 | 2025-12-23 提炼出四类检查Checklist：逻辑闭环/MVP范围/约束冲突/目的匹配，明确审稿边界和终止信号
ReAct 循环的自动终止条件 | 低 | 已解决 | 2025-12-23 建立三格卡片标准+摩擦轮次判断+AI自检Prompt模板，从人类直觉提升为可被模型自用的结构化检查
移交（Handoff）时的信息传递策略 | 低 | 已解决 | 2025-12-23 建立四层通用移交协议，明确字段白名单/黑名单，采用信息分层原则（通用规则固化+特殊约束单传）
Supervisor 在具体框架（如 LangGraph）中的节点/边实现方式 | 中 | 未解决 | 目前只在概念和规则层面清晰，还没有在具体框架里实现过 Supervisor 节点和路由逻辑，不清楚 State 该如何建模、自检信号如何在节点间流转，以及如何与 Checkpointer/持久化存储配合
Supervisor 与现有 RAG 系统的意图分流（检索/生成/改写等）如何融合 | 中 | 未解决 | 需要把今天的路由心智模型嫁接到已有的 RAG 意图识别与分流策略上，包括顶层 Router 如何区分“查知识 vs 做事”、哪些意图只需 RAG 处理、哪些需要进入多 Agent 工作流，以及如何在不增加过多轮数的前提下控制成本和延迟

---

## 📅 学习路径规划

**推荐顺序:** B → D → C → A → E

1. **第一阶段: 核心编排模式 (B)** - 先学走路
   - 重点: ReAct, Tool Use
   - 目标: 理解 Agent 的基本运行循环

2. **第二阶段: 记忆与状态管理 (D)** - 再学记事
   - 重点: State Graph, Memory
   - 目标: 掌握状态管理与上下文控制

3. **第三阶段: 多智能体架构 (C)** - 最后组队
   - 重点: Handoffs, Supervisor
   - 目标: 设计复杂的多 Agent 协作系统

4. **第四阶段: 基础认知 (A)** - 查漏补缺
   - 目标: 夯实底层原理

5. **第五阶段: 评估与工程化 (E)** - 实战优化
   - 目标: 生产级部署能力

---

## 📝 最近更新

- **2025-12-16**: 初始化学习追踪器
- **2025-12-17**: 学习 ReAct 模式与需求文档助手架构
- **2025-12-18**: 学习 Planner/State Graph/Reflection,梳理需求评审助手与Qoder自身的Agent流程
- **2025-12-21**: 复习验证 Planner/State/Reflection 三个核心概念，实践落地真实工作流的状态图建模（Jam 1→Jam 2→画原型 AI），初步接触 C.1 Handoffs 多智能体协作
- **2025-12-22**: 基于真实音频需求拆解 Gem1/Gem2/设计AI/Gem3 多智能体流程, 建立意图→功能→表现→文档四层模型, 总结各层升级Checklist和路由/移交心智模型
- **2025-12-23**: 基于 EnergyAI 项目完整实战回放，一次性解决三个知识盲区（Reflection审稿标准/ReAct终止条件/Handoff移交协议），提炼出通用规则模板（去项目化），建立信息分层原则和摩擦策略
- **2025-12-24**: 学习 C.2 Supervisor 监督者模式，结合 Gem1/Gem2/设计AI/Gem3 工作流设计路由与纠错规则，提炼 Supervisor 路由与冲突回退心智模型
