---
name: low-cognitive-cost-ai-writing
description: Create or substantially restructure technical learning notes, research explanations, tutorials, and engineering references. Use when readers need to understand a mechanism, work through a technical task, compare methods, or recover understanding on a later visit. Choose Concept, Tutorial, Deep Dive, and Reference modes according to the reader's goal. Assess whether the explanation benefits from verifiable, editable diagrams.
---

# low-cognitive-cost AI writing

Adaptive Technical Knowledge Writing System for personal study, research, public technical sharing, and later review. Aim for accurate technical writing that gives a peer a clear route through the mechanism.

## 第一层 · Writing Philosophy

先决定读者需要完成什么判断，再选择材料和解释方式。用 **Knowledge Selection** 划边界，用 **Reader Modeling** 判断读者已经知道什么，用 **Explanatory Sequencing** 安排知识进入顺序，用 **Making Implicit Relations Explicit** 补上关键推理，用 **Editorial Judgment** 决定展开、压缩、收束或停止。这五种能力指导整个写作过程。遇到范围、顺序、难度和长度之间的取舍，读 [写作哲学](references/writing-philosophy.md)。

## 第二层 · Scope & Document Router

1. 用一句问题说清当前稿件的承诺，并明确读者完成后能解释、预测、操作或查阅什么。按用户要求、材料和受众推断知识起点。
2. 划定 **Knowledge Slice**。主线纳入直接支撑这个承诺的机制、案例、证据和边界。相关内容仅需被定位时，用能访问的来源承接。复用技术原稿时保留切片内的事实、限定条件和重要出处。
3. 选择主模式。Concept 让读者识别、解释或区分一个概念。Tutorial 从可复现的起点走到可验证的结果。Deep Dive 让读者推断机制和条件变化的后果。Reference 让读者找到准确条目并行动。允许同一稿件按局部读者需求混用这些模式。
4. 应用 **One-hop Prerequisites**。前置索引只收录正文直接使用且读者需要回查的知识。写名称、用途和可访问入口。本次机制的对象和新符号在正文首次使用前交代。
5. 应用 **Local Rigor**。说明公式变量、相似写法、成立条件和局部推导。深度以读者目标为限。核对版本和来源，区分事实、假设、推导与实测。

每次编写技术文档都做视觉评估。检查多阶段流程、组件数据传递、网络或系统结构、公式的多源输入、状态与时序、反馈、概念依赖、算法结构对比和长文恢复地图。算法、Deep Dive、Tutorial 和科研机制说明尤应检查。若图能显著减少读者自行拼接的关系，就实际生成并嵌入。若决定省略，记录具体理由，例如两列指标已经可以直接比较。用读者的任务和最难的一步分配篇幅。短稿可就地完成判断，复杂稿件可用简短的视觉计划记录。

## 第三层 · 四个协作引擎

由同一个 Agent 使用同一份知识模型。知识建模识别视觉候选并提供节点与边的语义。教学和视觉引擎共同安排读图顺序、讲解与插图位置。视觉引擎负责制图、验证和渲染，发现歧义时回到知识模型。知识恢复复用正文核心图，并把它们接入可定位的恢复路径。发现缺少前提或图形混义时，回到关系模型和范围。

```mermaid
flowchart LR
    S["范围与读者任务"] --> K["Knowledge Modeling"]
    K --> T["Teaching & Explanation"]
    K --> V["Visual Knowledge Engineering"]
    T <-->|共同选择表达| V
    K --> R["Knowledge Retrieval"]
    T --> R
    V --> R
    T -.->|缺少推理前提| K
    V -.->|边义不清| K
    R -.->|入口难找| T
```

| 引擎 | 路由与参考 |
| --- | --- |
| **Knowledge Modeling** | 先辨认依赖、因果、时间、数据与对照。主题互相牵连、需解释版本差异或核对证据时，读 [知识建模](references/knowledge-modeling.md)。 |
| **Teaching & Explanation** | 按读者当前的知识任务选择开头，定位最难跨的关系。设问后就地回答，完稿前对读问句标题和首段。实质改写或需要案例、计算、边界对照时，读 [教学表达](references/teaching-explanation.md)。 |
| **Visual Knowledge Engineering** | 将知识关系做成降低理解成本的图、算法图、知识地图和复习入口。有明显视觉收益时，按 [视觉知识工程](references/visual-reasoning.md) 完成计划、制作、验证与嵌入。 |
| **Knowledge Retrieval** | 标出重新进入主机制、公式和证据的路径。长文、科研笔记或明确用于复习时，读 [知识恢复](references/knowledge-retrieval.md)。Quick Recall 按需使用。 |

图的数量由读者要完成的判断决定。长文优先评估总图和必要局部图。正文用一句话说明如何读关键图，再补成立条件、推导或反例。

## 第四层 · 贯穿式质量约束

- **Local Rigor**。逐项核对角色、假设、单位、极端情形、箭头语义和证据。
- **Cognitive Load Control**。实际走一次读者路径。找到需要跳读、对照符号或补演算的地方，选择更直接的解释方式。
- **Editorial Judgment**。用删减试验确定哪些内容应展开、保留、外移或收束。读者已经能作出判断时结束支线。

使用 [严谨性与编辑审查](references/rigor-and-editorial.md) 检查质量。有图的稿件须核对技术语义、可编辑源、渲染结果、正文中的相对路径和复习入口。目标 Markdown 无法渲染 Mermaid 时，提供它能显示的 SVG 或 PNG，并保留源。绘图工具不可用时交付可编辑源，明确说明渲染尚未验证。
