# Jupyter Notebook 实验工作区

用于管理各类 Jupyter Notebook 实验的集成开发环境，便于按实验分文件夹管理并同步到 GitHub。

## 项目结构

```
jupyter_notebook/
├── README.md              # 本说明
├── LICENSE                # MIT 许可证
├── requirements.txt       # Python 依赖
├── .gitignore
├── .cursor/
│   └── rules/             # Cursor 实验规范（可选）
├── experiments/           # 所有实验放在此目录下
│   ├── 01_hello_world/    # 环境测试示例
│   │   ├── README.md
│   │   └── notebook.ipynb
│   └── ...
```

## 快速开始

### 1. 创建虚拟环境（推荐）

```bash
python -m venv .venv
.venv\Scripts\activate   # Windows
# source .venv/bin/activate  # Linux/macOS
```

使用 Anaconda 时可直接激活已有环境，例如：`conda activate kooki`。

### 2. 安装依赖

```bash
pip install -r requirements.txt
```

### 3. 启动 Jupyter

```bash
jupyter notebook
# 或使用 JupyterLab
jupyter lab
```

### 4. 运行示例实验

打开 `experiments/01_hello_world/notebook.ipynb`，依次运行所有单元格，可验证 Python、numpy、pandas、matplotlib 是否正常，并看到简单绘图。该示例中已配置 matplotlib 中文字体，避免中文标题/标签出现方框或 Glyph missing 警告。

### 5. 新建实验

在 `experiments/` 下新建子文件夹（如 `02_数据分析/`），在其中创建或放置 `.ipynb` 及需要的 `data/`、`output/` 等即可。

也可以直接将外部课程或项目的 Lab 拷贝到 `experiments/` 下，例如：

```
experiments/
├── 01_hello_world/
├── C1-Supervised ML_Regression and Classification/
│   └── Week 1/
│       └── C1_W1_Lab03_Model_Representation_Soln.ipynb
└── ...
```

## 实验命名与组织建议

- 使用编号 + 简短描述：`01_hello_world`、`02_数据可视化`
- 对于课程类实验，建议以「课程名/章节」作为两级目录，便于按课程和周次管理。
- 每个实验文件夹内可包含：`notebook.ipynb`、`README.md`、`data/`、`output/` 等

## 绘图中文显示说明

若在 notebook 中用 matplotlib 绘制含中文的标题或标签，建议在绘图前设置中文字体，例如：

```python
import matplotlib.pyplot as plt
plt.rcParams["font.sans-serif"] = ["Microsoft YaHei", "SimHei", "SimSun", "KaiTi"]
plt.rcParams["axes.unicode_minus"] = False
```

示例实验 `01_hello_world` 中已包含上述配置，可直接参考。

## 仓库技能

- `update-readme-on-task-complete`：在线程任务完成后检查并同步根目录 `README.md` 与 `requirements.txt`，确保仓库结构、实验路径、脚本入口、使用说明和依赖声明与当前实现保持一致。技能定义位于 `skills/update-readme-on-task-complete/SKILL.md`。

## 许可证

本项目采用 [MIT License](LICENSE)。你可以在保留版权与许可声明的前提下自由使用、修改与分发。
