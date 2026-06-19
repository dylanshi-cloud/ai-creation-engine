# AI Creation Engine · 用数字的精通，去解决物理的无能

> **Mastering bits to shape atoms.**
>
> AI can build an entire app, but can't fry an egg.
> **This project is the bridge.**

---

## 一句话

**AI不造物，AI写代码——代码造物。**

---

## 核心洞察

AI在数字世界无所不能，在物理世界无能为力。

这个裂痕的解法，不在"让AI理解物理世界"——在**代码**。

代码是数字世界和物理世界之间**唯一的精确交集**：

| | 代码的特性 | 为什么它是桥梁 |
|:---|:---|:---|
| **确定性** | 代码要么编译通过执行，要么报错 | AI不需要"猜测"物理结果，它生成代码→执行→看结果 |
| **因果链完整** | 从意图到物理结果，每一环可追踪 | AI写CadQuery脚本→生成3D模型→写FEA脚本→验证结果 |
| **高密度** | 几十行代码描述完整工程零件 | 信息密度远高于自然语言 |
| **AI精通它** | 写代码是AI最强的能力 | 不需要新能力，不需要新架构 |

**AI不造物，AI写代码。代码造物。**

CadQuery 描述几何，CalculiX 验证物理，Python 分析结果——每一层都是代码。AI精通的是代码，而代码控制着从设计到制造的一切工具。

---

## 这个项目做什么

```
AI生成代码 → 代码运行 → 代码产物进入物理世界
    ↓                                ↓
写CadQuery脚本                 生成3D模型（STEP）
写FEA输入脚本                  生成应力/形变结果
写参数优化代码                 优化后的设计参数
写G-code/CAM指令              制造执行
    ↓                                ↓
AI在精通领域工作              物理世界被改变
```

**AI不需要"感觉"物理世界。它只需要生成正确的代码。代码运行的结果，就是物理世界的变化。**

---

## 架构

```
┌──────────────────────────────────────────────────────┐
│  AI 的精通领域：代码生成                               │
│                                                        │
│  ┌──────────┐  ┌──────────┐  ┌──────────┐  ┌──────┐  │
│  │ CadQuery │  │ FEA脚本  │  │ 后处理    │  │G-code│  │
│  │ 生成     │→ │ 生成     │→ │ 分析生成  │→ │ 生成  │  │
│  └──────────┘  └──────────┘  └──────────┘  └──────┘  │
│       │             │             │             │       │
│       ▼             ▼             ▼             ▼       │
│  ┌──────────┐  ┌──────────┐  ┌──────────┐  ┌──────┐  │
│  │ 3D模型   │  │ FEA结果  │  │ 优化方案  │  │制造  │  │
│  │ STEP文件 │  │应力/形变 │  │ 参数调整  │  │指令  │  │
│  └──────────┘  └──────────┘  └──────────┘  └──────┘  │
│                                                        │
│  每一步的产物都是可执行代码和可验证结果                     │
└──────────────────────────────────────────────────────┘
```

**四层物理架构详见** [docs/architecture.md](docs/architecture.md)

---

## 当前状态

**Phase 1 进行中**——选一个窄域（注塑件支架），跑通"AI写代码 → 代码造物"的完整循环。

| 阶段 | 时间 | 目标 |
|:---|:---|:---|
| Phase 1 | 0-3个月 | 一个窄域跑通端到端，代码→物理验证 |
| Phase 2 | 3-6个月 | 数据规模化，AI从FEA结果中学会"直觉" |
| Phase 3 | 6-12个月 | 横向扩展到更多物理域 |

详见 [docs/roadmap.md](docs/roadmap.md)

---

## 核心文档（建议从这里开始读）

| 文档 | 说明 |
|:---|:---|
| **[docs/manifesto.md](docs/manifesto.md)** | 🏛️ 底层逻辑与方法论——两个理念的完整展开 |
| **[docs/philosophy.md](docs/philosophy.md)** | 📖 哲学基础——为什么代码是精确交集 |
| **[docs/architecture.md](docs/architecture.md)** | 🏗️ 以代码为中心的四层架构 |
| **[docs/roadmap.md](docs/roadmap.md)** | 🗺️ 三阶段执行路线图 |
| **[docs/book-chapter.md](docs/book-chapter.md)** | 📕 书籍章节——《两个不完美的头脑》第六章 |

## 项目结构

```
ai-creation-engine/
├── README.md              # 项目入口（你正在看这个）
├── docs/
│   ├── manifesto.md       # 🏛️ 底层逻辑与方法论（先读这个）
│   ├── philosophy.md      # 完整的哲学体系
│   ├── architecture.md    # 以代码为中心的架构详解
│   ├── roadmap.md         # 三阶段执行计划
│   └── book-chapter.md    # 《两个不完美的头脑》第六章
├── phase-1/               # Phase 1 代码
│   ├── cad/               # CadQuery 参数化脚本
│   ├── fea/               # FEA 仿真脚本
│   └── pipeline/          # AI 编排管线
├── examples/              # 输出案例
├── LICENSE
└── CONTRIBUTING.md
```

---

## 起步

```bash
# 克隆
git clone https://github.com/your-username/ai-creation-engine.git
cd ai-creation-engine

# 安装依赖
pip install cadquery calculix  # 以及更多...

# 运行第一个例子
python phase-1/pipeline/run_bracket_design.py
```

详细起步指南见 [phase-1/README.md](phase-1/README.md)

---

## 贡献

这不是一个传统的"提PR"项目。这是一个**途径/方法/哲学**的开源。

你可以：
- 把你的物理域跑通这条"以代码为中心"的管线
- 提供更多领域代码模板（钣金、散热片、CNC……）
- 分享代码→FEA→制造的实践经验
- 翻译和传播这套思想

详见 [CONTRIBUTING.md](CONTRIBUTING.md)

---

## 这本书

这个项目的根，来自一本书——《两个不完美的头脑：AI与人类的对话录》。书中记录了人与AI如何共同思考"AI如何改造物理世界"这个问题的全过程。

详见 [docs/book-chapter.md](docs/book-chapter.md)

---

## 说在最后

> **AI不造物，AI写代码——代码造物。**
>
> *AI doesn't make things. AI writes code. Code makes things.*

---

**MIT License** · 以《两个不完美的头脑》第六章为基础 · 核心方法论见 [docs/manifesto.md](docs/manifesto.md)
*Leyi & Claude · 2026年6月*
