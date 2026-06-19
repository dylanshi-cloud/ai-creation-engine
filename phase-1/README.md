# Phase 1：注塑件支架 · 验证期

> 目标：跑通"AI设计→FEA验证→AI迭代"的完整循环
> 时间：0-3个月

---

## 环境安装

```bash
# CadQuery
pip install cadquery

# CalculiX (Windows: 需要从官网下载安装)
# https://www.calculix.de/
# 然后
pip install calculix

# 辅助工具
pip install numpy trimesh matplotlib

# 验证安装
python -c "import cadquery; print(cadquery.__version__)"
python -c "import calculix; print('OK')"
```

---

## 目录结构

```
phase-1/
├── cad/                  # CadQuery 参数化设计脚本
│   ├── bracket_base.py   # L型支架基础模型
│   ├── bracket_variants.py  # 变体生成器
│   └── utils.py          # 通用工具
├── fea/                  # FEA 仿真脚本
│   ├── run_fea.py        # 调用CalculiX执行仿真
│   └── parse_results.py  # 解析FEA结果
├── pipeline/             # AI 编排管线
│   └── design_loop.py    # 设计→FEA→迭代循环
└── README.md
```

---

## 第一步：跑通第一个参数化支架

```python
# cad/bracket_base.py
import cadquery as cq

def create_l_bracket(
    width=85,         # mm
    height=45,        # mm  
    thickness=3.0,    # mm
    rib_count=3,
    rib_height=5,
    rib_thickness=1.5
):
    """Create a parameterized L-bracket."""
    # 主结构: L型
    bracket = (
        cq.Workplane("XY")
        .box(width, thickness, height)
        .faces(">Z").workplane()
        .box(thickness, width - thickness, height)
        # 圆角
        .edges("|Z").fillet(1.0)
    )
    
    # 加强筋
    if rib_count > 0:
        spacing = (width - 2*thickness) / (rib_count + 1)
        for i in range(rib_count):
            pos = thickness + spacing * (i + 1)
            bracket = bracket.faces(">X").workplane().center(0, 0) \
                .box(rib_thickness, rib_height, height - 2) \
                .edges("|X").fillet(0.5)
    
    return bracket

if __name__ == "__main__":
    bracket = create_l_bracket()
    cq.exporters.export(bracket, "bracket_default.step")
```

---

## 第二步：验证每一步

1. 运行 CadQuery 脚本，生成 `.step` 文件
2. 在 FreeCAD 或查看器中打开，确认几何正确
3. 运行 FEA 脚本，获得应力/形变结果
4. AI 分析结果，提出修改建议
5. 修改参数，重新生成

---

## 第三步：打样

最优设计出工程图 → 找义乌供应链注塑打样 → 实际测试 → 校准FEA参数。
