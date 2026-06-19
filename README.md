# AI Creation Engine · 用数字的精通，去解决物理的无能

> **Mastering bits to shape atoms.**
>
> AI can build an entire app, but can't fry an egg.
> This project is the bridge.

---

## 为什么有这个项目

现在的AI有一个奇怪的裂痕——

在数字世界，它无所不能：写完整的App、做网页、生成视频、处理海量数据。精确、快速、不知疲倦。

在物理世界，它种不出一颗稻子，做不出一个煎蛋。

同时，人类几百年的工程智慧——产品图纸、大楼的施工图、材料的配方——这些**物理世界的数据化投影**，是AI和物理世界之间最精确的交集。

**这个项目的使命：用这个交集搭一座桥。**

让AI的"数据精通"穿过图纸、仿真、制造，真实地影响物理世界。

---

## 核心思想

### 一句口号
**用数字的精通，去解决物理的无能。**
*Mastering bits to shape atoms.*

### 三条信念

1. **物理世界的"Transformer时刻"还没来**——2017年的Transformer为数字AI点燃了Scaling Laws；物理AI需要自己的架构。
2. **物理数据引擎 = 物理AI的"互联网文本"**——LLM靠互联网文本启动；物理AI需要靠大规模仿真数据启动。
3. **Layer 0：用当前的AI建造未来的AI**——这个项目本身，就是AI在和人类一起设计物理AI的架构。这是一个递归。

### 四层架构

```
Layer 4: 物理执行层 → CAM / G-code / 3D打印 / 机器人指令
Layer 3: 物理验证层 → 可微分FEA/CFD引擎 + 确定性约束求解器
Layer 2: 世界模型层 → 大规模预训练的物理Foundation Model
Layer 1: 物理感知层 → 隐式神经表示 / 3D Tokenizer / 多模态融合
Layer 0: AI架构师层 → 用现有AI设计、建造、迭代整个系统
```

---

## 当前状态

**Phase 1 进行中**——选一个窄域（注塑件支架），跑通"AI设计 → FEA验证 → AI迭代"的完整循环。

| 阶段 | 时间 | 目标 |
|:---|:---|:---|
| Phase 1 | 0-3个月 | 一个窄域跑通端到端，打样验证 |
| Phase 2 | 3-6个月 | 数据规模化，训练物理直觉模型 |
| Phase 3 | 6-12个月 | 横向扩展更多物理域 |

详见 [docs/roadmap.md](docs/roadmap.md)

---

## 项目结构

```
ai-creation-engine/
├── README.md              # 项目宣言（你正在看这个）
├── docs/
│   ├── philosophy.md      # 完整的哲学体系
│   ├── architecture.md    # 四层架构详解 + Layer 0
│   └── roadmap.md         # 三阶段执行计划
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

## 这本书

这个项目的根，来自一本书——《两个不完美的头脑：AI与人类的对话录》。书中记录了人与AI如何共同思考"AI如何改造物理世界"这个问题的全过程。详见 [docs/book-chapter.md](docs/book-chapter.md)

---

## 贡献

这不是一个传统的"提PR"项目。这是一个**途径/方法/哲学**的开源。

你可以：
- 在另一个物理域跑通同样的管线（钣金、散热片、CNC……）
- 改善FEA校准流程
- 提供制造数据和验证结果
- 翻译和传播这套思想
- 在issue里分享你的实践和思考

详见 [CONTRIBUTING.md](CONTRIBUTING.md)

---

## 许可证

MIT License

---

## 说在最后

> *AI造物引擎不是一行代码——它是一种信仰：数字的精通终将穿过那条裂痕，触达物理世界。*

---

*以《两个不完美的头脑》第六章为基础*
*Leyi & Claude · 2026年6月*
