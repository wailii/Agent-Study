# Agent-Study 进度追踪器 (Study Tracker)

## 📊 学习进度概览

**开始日期:** 2025-12-16  
**当前阶段:** 初始化  
**总体完成度:** 0/5 大模块

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

- **B.1 ReAct (Reason+Act)**: 理解了 Thought → Action → Observation → History 的循环机制,知道它适合作为高开销模式服务复杂检索/分析任务,并能用意图识别+验证层把它放进完整的 RAG/需求助手架构中

---

## 🔍 知识盲区 (Knowledge Gaps)

- [GAP] ReAct 在具体框架(如 LangChain / LangGraph)中的实现与 State Graph 结合方式
- [GAP] 需求文档助手中各类工具(需求文档检索、需求历史/差异查询等)的具体落地方案和数据建模

---

## 📝 学习路径规划

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

- **2025-12-17**: 学习 B.1 ReAct 模式,梳理 ReAct+RAG+需求文档助手的整体架构
- **2025-12-16**: 初始化学习追踪器
