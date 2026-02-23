# Jupyter Notebook 实验工作区

用于管理各类 Jupyter Notebook 实验的集成开发环境，便于按实验分文件夹管理并同步到 GitHub。

## 项目结构

```
jupyter_notebook/
├── README.md           # 本说明
├── requirements.txt    # Python 依赖
├── experiments/        # 所有实验放在此目录下
│   ├── 01_hello_world/ # 示例：每个实验一个子文件夹
│   │   └── notebook.ipynb
│   └── ...
└── .gitignore
```

## 快速开始

### 1. 创建虚拟环境（推荐）

```bash
python -m venv .venv
.venv\Scripts\activate   # Windows
# source .venv/bin/activate  # Linux/macOS
```

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

### 4. 新建实验

在 `experiments/` 下新建子文件夹，例如 `02_数据分析/`，在其中创建或放置 `.ipynb` 文件即可。

## 实验命名建议

- 使用编号 + 简短描述：`01_hello_world`、`02_数据可视化`
- 每个实验文件夹内可包含：`notebook.ipynb`、`data/`、`output/` 等

## 许可证

按需添加。
