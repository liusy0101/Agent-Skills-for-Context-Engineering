# Agent 上下文工程学习路径

## 学习路径图

```
 ╔══════════════════════════════════════════════════════════════════════════════╗
 ║                                                                            ║
 ║   阶段一：理解核心概念 ★ 打地基                                              ║
 ║                                                                            ║
 ║   ┌─────────────────────────┐     ┌─────────────────────────┐              ║
 ║   │  ① context-fundamentals │────▶│  ② context-degradation  │              ║
 ║   │     上下文基础           │     │     上下文退化模式       │              ║
 ║   └─────────────────────────┘     └────────────┬────────────┘              ║
 ║                                                │                           ║
 ╠════════════════════════════════════════════════╪═══════════════════════════╣
 ║                                                │                           ║
 ║   阶段二：学习架构模式 ★ 搭骨架                  ▼                           ║
 ║                                                                            ║
 ║   ┌─────────────────────────┐     ┌─────────────────────────┐              ║
 ║   │  ③ multi-agent-patterns │────▶│  ④ tool-design          │              ║
 ║   │     多 Agent 协作        │     │     工具设计             │              ║
 ║   └─────────────────────────┘     └────────────┬────────────┘              ║
 ║                                                │                           ║
 ║                                                ▼                           ║
 ║   ┌─────────────────────────┐     ┌─────────────────────────┐              ║
 ║   │  ⑥ filesystem-context   │◀────│  ⑤ memory-systems       │              ║
 ║   │     文件系统上下文       │     │     记忆系统             │              ║
 ║   └────────────┬────────────┘     └─────────────────────────┘              ║
 ║                │                                                           ║
 ╠════════════════╪═══════════════════════════════════════════════════════════╣
 ║                │                                                           ║
 ║   阶段三：运维优化 ★ 精细调优                                               ║
 ║                ▼                                                           ║
 ║   ┌─────────────────────────┐     ┌─────────────────────────┐              ║
 ║   │  ⑦ context-compression  │────▶│  ⑧ context-optimization │              ║
 ║   │     上下文压缩           │     │     上下文优化           │              ║
 ║   └─────────────────────────┘     └────────────┬────────────┘              ║
 ║                                                │                           ║
 ╠════════════════════════════════════════════════╪═══════════════════════════╣
 ║                                                │                           ║
 ║   阶段四：评估体系 ★ 闭环验证                    ▼                           ║
 ║                                                                            ║
 ║   ┌─────────────────────────┐     ┌─────────────────────────┐              ║
 ║   │  ⑨ evaluation           │────▶│  ⑩ advanced-evaluation  │              ║
 ║   │     评估基础             │     │     高级评估             │              ║
 ║   └─────────────────────────┘     └────────────┬────────────┘              ║
 ║                                                │                           ║
 ╠════════════════════════════════════════════════╪═══════════════════════════╣
 ║                                                │                           ║
 ║   阶段五：综合实战 ★ 融会贯通                    ▼                           ║
 ║                                                                            ║
 ║   ┌─────────────────────────┐                                              ║
 ║   │  ⑪ project-development  │                                              ║
 ║   │     项目开发方法论       │                                              ║
 ║   └──┬──────┬──────┬──────┬─┘                                              ║
 ║      │      │      │      │                                                ║
 ║      ▼      ▼      ▼      ▼                                               ║
 ║   ┌──────┐┌──────┐┌──────┐┌──────┐                                        ║
 ║   │数字  ││LLM   ││Book  ││X-to- │                                        ║
 ║   │大脑  ││评审  ││SFT   ││Book  │                                        ║
 ║   │项目  ││项目  ││管道  ││系统  │                                        ║
 ║   └──┬───┘└──────┘└──────┘└──────┘                                        ║
 ║      │                                                                     ║
 ╠══════╪═════════════════════════════════════════════════════════════════════╣
 ║      │                                                                     ║
 ║   阶段六：扩展选修（可选）                                                   ║
 ║      │                                                                     ║
 ║      ├────▶┌─────────────────────────┐                                     ║
 ║      │     │  ⑬ hosted-agents        │                                     ║
 ║      │     │     托管 Agent 基础设施   │                                     ║
 ║      │     └─────────────────────────┘                                     ║
 ║      │                                                                     ║
 ║      └────▶┌─────────────────────────┐                                     ║
 ║            │  ⑭ bdi-mental-states    │                                     ║
 ║            │     BDI 认知架构         │                                     ║
 ║            └─────────────────────────┘                                     ║
 ║                                                                            ║
 ╚══════════════════════════════════════════════════════════════════════════════╝
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

## 实操指南

> 本项目定位是**知识库/参考手册**（被北大论文引用），概念梳理质量很高，但实操代码偏少。
> 以下内容帮你补齐动手环节，避免"学完一堆概念但不会写代码"。

### 项目内实操内容评估

| 项目 | 类型 | 能否直接跑 | 说明 |
|------|------|-----------|------|
| `examples/llm-as-judge-skills` | TypeScript | **能跑**，19 个测试 | 最接近生产代码的评估框架实现 |
| `examples/interleaved-thinking` | Python 包 | **能跑**，pytest + CLI | 完整的推理优化工具 |
| `examples/digital-brain-skill` | Node + Python | **能跑**，脚手架 | 生成模板文件夹，需自己填入数据 |
| `examples/book-sft-pipeline` | Python | 不能直接跑 | 核心函数是空壳，无入口 |
| `examples/x-to-book-system` | Markdown | 不能跑 | 纯设计文档（PRD），零代码 |
| `skills/*/scripts/*.py`（12 个） | Python | 能跑 | 用 mock 数据演示概念，非真实 LLM 调用 |

### 立即可以动手的项目

**1. LLM 评估框架（TypeScript，最推荐优先跑）**

```bash
cd examples/llm-as-judge-skills
npm install
npm test                    # 跑通 19 个测试，读懂代码
npm run example:basic       # 配置 API Key 后跑真实评估
```

**2. 推理优化工具（Python）**

```bash
cd examples/interleaved-thinking
pip install -e ".[dev]"
pytest                      # 跑测试
rto --help                  # 体验 CLI 工具
```

**3. 数字大脑模板（Node + Python）**

```bash
cd examples/digital-brain-skill
npm run setup               # 生成文件夹结构
npm run weekly-review       # 运行周回顾脚本
npm run content-ideas       # 生成内容创意
npm run stale-contacts      # 检查过期联系人
```

### 每阶段配套实操练习

学完概念后，**务必**做以下对应练习来巩固：

#### 阶段一练习：亲眼验证 Lost-in-Middle

> 目标：用真实 API 调用验证"信息放在上下文中间会被忽略"这一现象。

```python
# 实验：同一个问题，关键信息分别放在开头、中间、结尾
import openai  # 或 anthropic

context_parts = [f"无关段落 {i}：这是一段填充文本..." for i in range(20)]
key_info = "关键事实：项目预算上限为 500 万元。"

# 实验 A：关键信息放开头
prompt_a = key_info + "\n".join(context_parts) + "\n问题：项目预算上限是多少？"

# 实验 B：关键信息放中间
prompt_b = "\n".join(context_parts[:10]) + key_info + "\n".join(context_parts[10:]) + "\n问题：项目预算上限是多少？"

# 实验 C：关键信息放结尾
prompt_c = "\n".join(context_parts) + key_info + "\n问题：项目预算上限是多少？"

# 对比三次回答的准确率和置信度
```

#### 阶段二练习 A：搭建多 Agent 协作系统

> 目标：用 LangGraph 或 CrewAI 搭一个 2-3 个 Agent 协作的小系统，体会上下文隔离的价值。

推荐场景："研究员 + 写手 + 审稿人"三角协作：
1. 研究员 Agent：接收主题，搜索资料，输出结构化摘要
2. 写手 Agent：基于摘要撰写文章（**注意：它不应该看到原始搜索结果**）
3. 审稿人 Agent：评审文章质量，给出修改建议

重点观察：如果把所有上下文都塞给每个 Agent，vs 每个 Agent 只拿到自己需要的信息，效果差异有多大。

#### 阶段二练习 B：对比工具设计策略

> 目标：给 Agent 设计工具，验证"合并原则"。

实验对比：
- 方案 A：一个大而全的 `do_everything(action, params)` 工具
- 方案 B：三个精确的小工具 `search_docs(query)`、`write_file(path, content)`、`run_test(file)`

让 Agent 完成同一个任务，对比：调用成功率、参数填错率、完成任务的步数。

#### 阶段三练习：实现对话压缩

> 目标：做一个长对话 Agent，实现历史消息的自动摘要压缩。

```python
# 核心逻辑伪代码
def compress_history(messages, max_tokens=2000):
    """当对话历史超过阈值时，保留最近 N 条 + 压缩摘要"""
    if count_tokens(messages) <= max_tokens:
        return messages

    recent = messages[-5:]  # 保留最近 5 条原文
    older = messages[:-5]

    summary = llm_call(
        f"请将以下对话摘要为结构化笔记，保留：\n"
        f"1. 用户的核心意图\n"
        f"2. 已做出的关键决策\n"
        f"3. 待完成的任务\n\n"
        f"对话内容：{older}"
    )

    return [{"role": "system", "content": f"历史摘要：{summary}"}] + recent
```

对比指标：压缩前后的回答质量、token 消耗、任务完成率。

#### 阶段四练习：搭建评估流水线

> 目标：在 `llm-as-judge-skills` 基础上，为你自己的 Agent 写一套评估量表。

1. 定义 3-5 个评估维度（如：准确性、完整性、格式规范、响应时间）
2. 为每个维度写 1-5 分的评分标准
3. 收集 10-20 个测试用例
4. 用 LLM-as-Judge 自动评分，再抽样人工复核
5. 计算 LLM 评分与人工评分的一致率

### 推荐配合的外部 GitHub 项目

> 本项目（Agent Skills for Context Engineering）定位是知识库/参考手册，概念梳理质量高但实操代码偏少。
> 以下精选的 GitHub 开源项目可以**补齐动手环节**，按理论+实操的综合匹配度排序。

#### 第一梯队：理论与实操兼备（强烈推荐）

**1. `langchain-ai/context_engineering` — LangChain 官方出品**

- **GitHub**：[langchain-ai/context_engineering](https://github.com/langchain-ai/context_engineering)
- **理论**：围绕四大核心策略展开——Write（写入）、Select（选择）、Compress（压缩）、Isolate（隔离）
- **实操**：4 个 Jupyter Notebook，基于 LangGraph 实现，每个策略对应一个可运行的 notebook
- **技术栈**：Python + LangGraph + OpenAI/Anthropic API
- **推荐理由**：最直接对应 Context Engineering 核心概念的实操项目。每个 notebook 都包含 scratchpad、记忆检索、对话摘要、多 Agent 隔离等核心模式的完整实现
- **快速上手**：

```bash
git clone https://github.com/langchain-ai/context_engineering.git
cd context_engineering
uv venv && source .venv/bin/activate
uv pip install -r requirements.txt
# 设置 OPENAI_API_KEY 或 ANTHROPIC_API_KEY 后打开 notebook
jupyter notebook context_engineering/
```

- **与本项目的对应关系**：

| 本项目 Skill | 对应 Notebook |
|-------------|---------------|
| context-fundamentals、filesystem-context | Write Context（scratchpad、状态管理） |
| memory-systems | Select Context（记忆检索、RAG 工具检索） |
| context-compression、context-optimization | Compress Context（对话摘要、工具输出压缩） |
| multi-agent-patterns | Isolate Context（Supervisor 架构、沙箱隔离） |

**2. `bonigarcia/context-engineering` — Manning 新书配套仓库**

- **GitHub**：[bonigarcia/context-engineering](https://github.com/bonigarcia/context-engineering)
- **理论**：配套 Manning 著作《Context Engineering: the art and science of shaping context-aware AI systems》（2026 出版），体系非常完整，覆盖 10 个章节：
  1. 上下文工程导论
  2. 系统指令与用户提示
  3. 外部知识与检索
  4. AI 代理的工具与记忆
  5. 代理系统中的状态与编排
  6. 上下文管理与评估
  7. AI 框架中的上下文
  8. 真实环境中的上下文工程
  9. 软件开发生命周期中的上下文工程
  10. 上下文工程的前沿技术
- **实操**：每章都有配套代码示例 + 在线 Context-aware prompt builder 工具
- **推荐理由**：**理论深度最强**。书籍体系化的章节结构让学习路径非常清晰，适合系统性学习

**3. `NirDiamant/agents-towards-production` — 从原型到生产的全流程**

- **GitHub**：[NirDiamant/agents-towards-production](https://github.com/NirDiamant/agents-towards-production)
- **理论**：覆盖 RAG、记忆系统、多 Agent 协调、安全性、追踪调试、评估等生产级话题
- **实操**：每个主题都是独立的代码优先教程，包含 Jupyter Notebook + 可运行的 Python 脚本
  - 双重记忆（短期+长期）+ Mem0 自进化记忆
  - Cognee 知识图谱构建
  - LangGraph 状态化工作流
  - Docker 容器化部署
  - LlamaFirewall 安全防护
  - LangSmith 追踪调试
- **推荐理由**：**最贴近生产实战**。如果不只想学概念，还想知道怎么把 Agent 部署到真实环境中，这个项目是最佳选择
- **注意**：采用非商业许可协议，仅供教育和学习使用

#### 第二梯队：侧重某一方面的优质资源

**4. `FareedKhan-dev/contextual-engineering-guide` — 端到端实操指南**

- **GitHub**：[FareedKhan-dev/contextual-engineering-guide](https://github.com/FareedKhan-dev/contextual-engineering-guide)
- **特点**：一个大型 Jupyter Notebook，从 StateGraph 创建到长期记忆管理，完整演示上下文工程流水线
- **适合**：想要一个一站式快速上手的实操项目，2-3 小时跑完全流程

**5. `dair-ai/Prompt-Engineering-Guide` — 最全面的提示工程百科（70k+ stars）**

- **GitHub**：[dair-ai/Prompt-Engineering-Guide](https://github.com/dair-ai/Prompt-Engineering-Guide)
- **特点**：从 Prompt Engineering 延伸到 Context Engineering，覆盖 RAG、ReAct、CoT、ToT 等高级技术，配有论文、Notebook 和多语言翻译
- **Web 版**：[promptingguide.ai](https://www.promptingguide.ai/zh)
- **适合**：需要从 Prompt Engineering 过渡到 Context Engineering 的学习者，理论广度最大

**6. `anthropics/claude-cookbooks` — Anthropic 官方实操手册**

- **GitHub**：[anthropics/claude-cookbooks](https://github.com/anthropics/claude-cookbooks)
- **特点**：官方出品的实操 Notebook，涵盖 tool use、RAG、prompt caching、sub-agents、多模态等核心模式
- **适合**：使用 Claude API 的开发者，想要直接上手 Claude 生态的实操

#### 第三梯队：中文学习指南

**7. `WakeUp-Jin/Practical-Guide-to-Context-Engineering` — 中文实践指南**

- **GitHub**：[WakeUp-Jin/Practical-Guide-to-Context-Engineering](https://github.com/WakeUp-Jin/Practical-Guide-to-Context-Engineering)
- **特点**：中文编写，系统梳理了上下文工程的定义、方法论和实践
- **适合**：偏好中文阅读、需要快速建立概念框架的学习者

### 外部项目与学习阶段的对照方案

> 每个阶段读完本项目的 Skill 概念后，到对应的外部项目中动手实操。

| 学习阶段 | 本项目读什么 | 外部项目做什么 | 预计用时 |
|---------|------------|---------------|---------|
| 建立概念框架 | `path.md` + `SKILL.md` 总览 | `bonigarcia/context-engineering` 第 1-2 章 | 1 天 |
| 阶段一：核心概念 | context-fundamentals、context-degradation | `langchain-ai/context_engineering` 的 Write Context notebook | 2 天 |
| 阶段二：架构模式 | multi-agent-patterns、tool-design、memory-systems | `langchain-ai/context_engineering` 的 Select + Isolate notebook | 3 天 |
| 阶段三：运维优化 | context-compression、context-optimization | `langchain-ai/context_engineering` 的 Compress Context notebook | 2 天 |
| 阶段四：评估体系 | evaluation、advanced-evaluation | `NirDiamant/agents-towards-production` 的评估教程 | 2 天 |
| 阶段五：综合实战 | project-development + 4 个示例项目 | `FareedKhan-dev/contextual-engineering-guide` 端到端流水线 | 3 天 |
| 走向生产 | hosted-agents | `NirDiamant/agents-towards-production` 的部署+安全教程 | 2 天 |

### 其他外部学习资源

| 资源 | 内容 | 链接 |
|------|------|------|
| OpenAI Cookbook | Function calling、Embeddings 实操 | [github.com/openai/openai-cookbook](https://github.com/openai/openai-cookbook) |
| LangGraph 官方教程 | 多 Agent 编排、状态管理 notebook | [langchain-ai.github.io/langgraph](https://langchain-ai.github.io/langgraph) |
| CrewAI 文档 | 快速搭建多 Agent 系统 | [docs.crewai.com](https://docs.crewai.com) |
| DeepLearning.AI 短课 | Andrew Ng 的 Agent 系列免费课 | [deeplearning.ai/short-courses](https://www.deeplearning.ai/short-courses) |
| 知乎专栏 | Context Engineering 中文深度解析 | [知乎 - Context Engineering](https://zhuanlan.zhihu.com/p/1938967453951571269) |

---

## 学习建议

1. **三七原则**：每个阶段 30% 时间读概念，70% 时间做上面的练习
2. **做笔记映射**：像 `HOW-SKILLS-BUILT-THIS.md` 那样，把你自己项目中的决策映射到学到的原则
3. **从小到大**：先用单 Agent + 文件系统上下文解决问题，只在证明有必要时才引入多 Agent 架构
4. **建立检查清单**：每个 Skill 的 Gotchas 部分是最高价值内容，汇总成你自己的 checklist
5. **记住核心公式**：上下文工程 = 在有限的注意力预算内，找到信噪比最高的最小 token 集合
6. **内外结合**：本项目的 Skill 提供概念框架，外部 GitHub 项目提供可运行代码——两者配合使用效果最佳
7. **如果时间有限只能选一个外部项目**：优先跑 `langchain-ai/context_engineering`，4 个 Notebook 精准覆盖四大核心策略

---

*基于 [Agent Skills for Context Engineering](https://github.com/muratcankoylan/Agent-Skills-for-Context-Engineering) 项目整理*
