# Agent 上下文工程学习路径

## 学习路径图

```mermaid
graph TD
    subgraph 阶段一：理解核心概念
        A1[context-fundamentals<br/>上下文基础] --> A2[context-degradation<br/>上下文退化模式]
    end

    subgraph 阶段二：学习架构模式
        B1[multi-agent-patterns<br/>多 Agent 协作] --> B2[tool-design<br/>工具设计]
        B2 --> B3[memory-systems<br/>记忆系统]
        B3 --> B4[filesystem-context<br/>文件系统上下文]
    end

    subgraph 阶段三：运维优化
        C1[context-compression<br/>上下文压缩] --> C2[context-optimization<br/>上下文优化]
    end

    subgraph 阶段四：评估体系
        D1[evaluation<br/>评估基础] --> D2[advanced-evaluation<br/>高级评估]
    end

    subgraph 阶段五：综合实战
        E1[project-development<br/>项目开发方法论]
        E2[digital-brain-skill<br/>数字大脑项目]
        E3[llm-as-judge-skills<br/>LLM 评审项目]
        E4[book-sft-pipeline<br/>SFT 管道项目]
        E5[x-to-book-system<br/>X 转书系统]
        E1 --> E2
        E1 --> E3
        E1 --> E4
        E1 --> E5
    end

    subgraph 阶段六：扩展选修
        F1[hosted-agents<br/>托管 Agent 基础设施]
        F2[bdi-mental-states<br/>BDI 认知架构]
    end

    A2 --> B1
    B4 --> C1
    C2 --> D1
    D2 --> E1
    E2 --> F1
    E2 --> F2

    style A1 fill:#4CAF50,stroke:#388E3C,color:#fff
    style A2 fill:#4CAF50,stroke:#388E3C,color:#fff
    style B1 fill:#2196F3,stroke:#1565C0,color:#fff
    style B2 fill:#2196F3,stroke:#1565C0,color:#fff
    style B3 fill:#2196F3,stroke:#1565C0,color:#fff
    style B4 fill:#2196F3,stroke:#1565C0,color:#fff
    style C1 fill:#FF9800,stroke:#E65100,color:#fff
    style C2 fill:#FF9800,stroke:#E65100,color:#fff
    style D1 fill:#9C27B0,stroke:#6A1B9A,color:#fff
    style D2 fill:#9C27B0,stroke:#6A1B9A,color:#fff
    style E1 fill:#F44336,stroke:#C62828,color:#fff
    style E2 fill:#F44336,stroke:#C62828,color:#fff
    style E3 fill:#F44336,stroke:#C62828,color:#fff
    style E4 fill:#F44336,stroke:#C62828,color:#fff
    style E5 fill:#F44336,stroke:#C62828,color:#fff
    style F1 fill:#607D8B,stroke:#37474F,color:#fff
    style F2 fill:#607D8B,stroke:#37474F,color:#fff
```

## 总览

| 阶段 | 主题 | 技能数 | 预计用时 |
|------|------|--------|----------|
| 一 | 理解核心概念 | 2 | 2-3 天 |
| 二 | 学习架构模式 | 4 | 4-5 天 |
| 三 | 运维优化 | 2 | 2-3 天 |
| 四 | 评估体系 | 2 | 2-3 天 |
| 五 | 综合实战 | 1 + 4 个项目 | 3-5 天 |
| 六 | 扩展选修 | 2 | 2 天 |

**核心公式**：上下文工程 = 在有限的注意力预算内，找到信噪比最高的最小 token 集合。

---

## 阶段一：理解核心概念（打地基）

> 学完本阶段你应该能回答："为什么更多的上下文不等于更好的结果？"

### 第 1 步：上下文基础

- **技能文件**：[`skills/context-fundamentals/SKILL.md`](skills/context-fundamentals/SKILL.md)
- **核心要点**：
  - 上下文不是"存储"，而是"注意力预算"
  - 四大原则 — 信息量 vs 穷举性、位置感知放置（lost-in-middle 现象）、渐进式披露、迭代筛选
- **配套材料**：
  - 脚本：`skills/context-fundamentals/scripts/context_manager.py`
  - 参考：`skills/context-fundamentals/references/context-components.md`

### 第 2 步：上下文退化模式

- **技能文件**：[`skills/context-degradation/SKILL.md`](skills/context-degradation/SKILL.md)
- **核心要点**：
  - 五种退化模式 — lost-in-middle、上下文中毒、上下文干扰、注意力 U 曲线、上下文冲突
  - 在加载前过滤、用任务隔离来防止退化
- **配套材料**：
  - 脚本：`skills/context-degradation/scripts/degradation_detector.py`
  - 参考：`skills/context-degradation/references/patterns.md`

---

## 阶段二：学习架构模式（搭骨架）

> 学完本阶段你应该能设计一个多 Agent 系统的架构蓝图。

### 第 3 步：多 Agent 协作模式

- **技能文件**：[`skills/multi-agent-patterns/SKILL.md`](skills/multi-agent-patterns/SKILL.md)
- **核心要点**：
  - 三种主流架构 — Supervisor/Orchestrator（集中控制）、Peer-to-Peer/Swarm（灵活交接）、Hierarchical（层级分解）
  - **关键洞察：子 Agent 存在的核心目的是隔离上下文，而非模拟组织角色**
- **配套材料**：
  - 脚本：`skills/multi-agent-patterns/scripts/coordination.py`
  - 参考：`skills/multi-agent-patterns/references/frameworks.md`

### 第 4 步：工具设计

- **技能文件**：[`skills/tool-design/SKILL.md`](skills/tool-design/SKILL.md)
- **核心要点**：
  - 工具是确定性系统与非确定性 Agent 之间的"合同"
  - 合并原则：一个工具做一件明确的事
  - 在错误中返回上下文信息
  - 工具描述即 prompt 工程
- **配套材料**：
  - 脚本：`skills/tool-design/scripts/description_generator.py`
  - 参考：`skills/tool-design/references/best_practices.md`、`skills/tool-design/references/architectural_reduction.md`

### 第 5 步：记忆系统设计

- **技能文件**：[`skills/memory-systems/SKILL.md`](skills/memory-systems/SKILL.md)
- **核心要点**：
  - 从简单 scratchpad 到时序知识图谱的记忆架构光谱
  - 对比主流框架：Mem0、Zep/Graphiti、Letta、LangMem、Cognee
  - **关键发现：简单检索往往优于复杂工具**
- **配套材料**：
  - 脚本：`skills/memory-systems/scripts/memory_store.py`
  - 参考：`skills/memory-systems/references/implementation.md`

### 第 6 步：文件系统上下文

- **技能文件**：[`skills/filesystem-context/SKILL.md`](skills/filesystem-context/SKILL.md)
- **核心要点**：
  - 文件系统作为上下文溢出层
  - 动态 vs 静态加载
  - scratch pad 模式
  - 四种失败模式（缺失、检索不足、检索过度、被埋没）及修复方法
- **配套材料**：
  - 脚本：`skills/filesystem-context/scripts/filesystem_context.py`
  - 参考：`skills/filesystem-context/references/implementation-patterns.md`

---

## 阶段三：运维优化（精细调优）

> 学完本阶段你应该能把一个 Agent 系统的 token 成本降低 50% 以上。

### 第 7 步：上下文压缩

- **技能文件**：[`skills/context-compression/SKILL.md`](skills/context-compression/SKILL.md)
- **核心要点**：
  - 优化目标是 **tokens-per-task**（每任务 token 数），而非每请求 token 数
  - 三种压缩策略 — 锚定式迭代摘要、不透明压缩、全量再生摘要
- **配套材料**：
  - 脚本：`skills/context-compression/scripts/compression_evaluator.py`
  - 参考：`skills/context-compression/references/evaluation-framework.md`

### 第 8 步：上下文优化

- **技能文件**：[`skills/context-optimization/SKILL.md`](skills/context-optimization/SKILL.md)
- **核心要点**：
  - 四大优化策略（按优先级排列）：
    1. KV-cache 优化
    2. 观测遮蔽（用引用替代冗长工具输出）
    3. 压缩整理
    4. 上下文分区（子 Agent 隔离上下文）
- **配套材料**：
  - 脚本：`skills/context-optimization/scripts/compaction.py`
  - 参考：`skills/context-optimization/references/optimization_techniques.md`

---

## 阶段四：评估体系（闭环验证）

> 没有评估就无法持续改进。学完本阶段你应该能为 Agent 系统搭建完整的评估流水线。

### 第 9 步：评估基础

- **技能文件**：[`skills/evaluation/SKILL.md`](skills/evaluation/SKILL.md)
- **核心要点**：
  - 结果导向评估
  - 多维评分量表
  - LLM-as-Judge + 人工评审结合
- **配套材料**：
  - 脚本：`skills/evaluation/scripts/evaluator.py`
  - 参考：`skills/evaluation/references/metrics.md`

### 第 10 步：高级评估

- **技能文件**：[`skills/advanced-evaluation/SKILL.md`](skills/advanced-evaluation/SKILL.md)
- **核心要点**：
  - 直接评分 vs 配对比较
  - prompt 构建框架（任务/标准/输出格式）
  - 偏差缓解策略
- **配套材料**：
  - 脚本：`skills/advanced-evaluation/scripts/evaluation_example.py`
  - 参考：`skills/advanced-evaluation/references/bias-mitigation.md`、`skills/advanced-evaluation/references/metrics-guide.md`
- **实战项目**：[`examples/llm-as-judge-skills/`](examples/llm-as-judge-skills/) — 完整 TypeScript 实现，包含 19 个通过测试

---

## 阶段五：综合实战（融会贯通）

> 通过完整项目把所有知识串联起来。

### 第 11 步：项目开发方法论

- **技能文件**：[`skills/project-development/SKILL.md`](skills/project-development/SKILL.md)
- **核心要点**：
  - 先做 task-model fit 分析再写代码
  - 分阶段幂等架构：获取 → 准备 → 处理 → 解析 → 渲染
- **配套材料**：
  - 脚本：`skills/project-development/scripts/pipeline_template.py`
  - 参考：`skills/project-development/references/case-studies.md`、`skills/project-development/references/pipeline-patterns.md`

### 第 12 步：研读实战项目

按推荐顺序阅读，注意对照每个项目应用了哪些 Skill 的原则。

#### 1. Digital Brain — 数字大脑项目

- **路径**：[`examples/digital-brain-skill/`](examples/digital-brain-skill/)
- **涵盖技能**：context-fundamentals、context-optimization、memory-systems、tool-design、multi-agent-patterns、evaluation、project-development（共 7 个）
- **学习重点**：渐进式披露（3 级加载）、模块隔离（6 个独立模块）、Append-Only 记忆（JSONL 格式）
- **必读**：[`HOW-SKILLS-BUILT-THIS.md`](examples/digital-brain-skill/HOW-SKILLS-BUILT-THIS.md) — 详细记录每个架构决策到 Skill 原则的映射

#### 2. LLM-as-Judge — LLM 评审项目

- **路径**：[`examples/llm-as-judge-skills/`](examples/llm-as-judge-skills/)
- **涵盖技能**：advanced-evaluation、tool-design、context-fundamentals、evaluation（共 4 个）
- **学习重点**：完整 TypeScript 实现，可运行 `npm test` 验证
- **上手命令**：`cd examples/llm-as-judge-skills && npm install && npm test`

#### 3. Book SFT Pipeline — 风格迁移训练管道

- **路径**：[`examples/book-sft-pipeline/`](examples/book-sft-pipeline/)
- **涵盖技能**：project-development、context-compression、multi-agent-patterns、evaluation（共 4 个）
- **学习重点**：端到端训练管道、$2 总成本、两层分块 + prompt 多样性策略

#### 4. X-to-Book System — 多 Agent 内容系统

- **路径**：[`examples/x-to-book-system/`](examples/x-to-book-system/)
- **涵盖技能**：multi-agent-patterns、memory-systems、context-optimization、tool-design、evaluation（共 5 个）
- **学习重点**：多 Agent 系统的完整设计文档（PRD）

---

## 阶段六：扩展选修

> 根据你的具体需求选择性学习。

### 第 13 步（可选）：托管 Agent 基础设施

- **技能文件**：[`skills/hosted-agents/SKILL.md`](skills/hosted-agents/SKILL.md)
- **适用场景**：需要构建远程沙盒执行环境、多人协作 Agent 系统
- **核心要点**：远程沙盒 vs 本地限制、三层架构（沙盒层、API 层、客户端层）、自生成 Agent
- **配套材料**：
  - 脚本：`skills/hosted-agents/scripts/sandbox_manager.py`
  - 参考：`skills/hosted-agents/references/infrastructure-patterns.md`

### 第 14 步（可选）：BDI 认知架构

- **技能文件**：[`skills/bdi-mental-states/SKILL.md`](skills/bdi-mental-states/SKILL.md)
- **适用场景**：对形式化推理、RDF 本体论、可解释 Agent 感兴趣
- **核心要点**：信念-愿望-意图（BDI）模型、RDF 到心理状态的转换、T2B2T 范式
- **配套材料**：
  - 参考：`skills/bdi-mental-states/references/bdi-ontology-core.md`、`skills/bdi-mental-states/references/rdf-examples.md`

---

## 学习建议

1. **边学边练**：每学完一个 Skill，运行对应的 `scripts/` 脚本，动手修改参数观察效果
2. **做笔记映射**：像 `HOW-SKILLS-BUILT-THIS.md` 那样，把你自己项目中的决策映射到学到的原则
3. **从小到大**：先用单 Agent + 文件系统上下文解决问题，只在证明有必要时才引入多 Agent 架构
4. **建立检查清单**：每个 Skill 的 Gotchas 部分是最高价值内容，汇总成你自己的 checklist
5. **实战驱动**：阶段五的项目不只是"看"，尝试 fork 后修改，验证你对原则的理解

---

*基于 [Agent Skills for Context Engineering](https://github.com/muratcankoylan/Agent-Skills-for-Context-Engineering) 项目整理*
