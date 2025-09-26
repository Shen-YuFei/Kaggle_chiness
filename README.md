## Kaggle_chiness — Kaggle 机器学习进阶（中文）

本仓库整理了 Kaggle Learn 的 Intermediate Machine Learning（机器学习进阶）课程的中文笔记与配套示例，涵盖缺失值、类别变量、管道、交叉验证、XGBoost 与数据泄漏等主题。

### 目录结构

- `intermediate-machine-learning/`
  - `1_introduction.ipynb` ~ `7_data-leakage.ipynb`：7 个主题的中文化 Jupyter 笔记本
  - `requirements.txt`：示例所需 Python 依赖
- `input/`
  - `melbourne-housing-snapshot/melb_data.csv`：墨尔本房价示例数据
  - `aer-credit-card-data/AER_credit_card_data.csv`：信用卡申请示例数据

### 环境准备

建议使用 Python 3.10+（推荐 3.11）和虚拟环境。

Windows PowerShell 示例：

```powershell
# 1) 创建并激活虚拟环境（可选）
python -m venv .venv
. .\.venv\Scripts\Activate.ps1

# 2) 安装依赖
pip install -r intermediate-machine-learning/requirements.txt
```

如需加速安装，可追加镜像参数（示例）：`-i https://pypi.tuna.tsinghua.edu.cn/simple`。

### 运行方式

1. 安装依赖后，启动 Jupyter：

   ```powershell
   jupyter notebook
   ```

   或使用 VS Code / Cursor 直接打开 `.ipynb` 文件。

2. 打开 `intermediate-machine-learning/` 下任一笔记本，按单元依次运行。

> 提示：交叉验证、XGBoost 等示例首次运行可能较慢，属正常现象。

### 数据说明

仓库已内置示例数据于 `input/` 目录，笔记本默认使用相对路径：

- 墨尔本房价：`input/melbourne-housing-snapshot/melb_data.csv`
- 信用卡申请：`input/aer-credit-card-data/AER_credit_card_data.csv`

若自定义了工作目录，请确保相对路径有效，或在笔记本中改为你的实际路径。

### 常见问题（FAQ）

- 问：交叉验证分数为何是负数？

  - 答：scikit-learn 评分器统一“越大越好”。MAE 属于“越小越好”，以负号表示（`neg_mean_absolute_error`）。可在代码中取相反数后再解读。

- 问：XGBoost 安装失败怎么办？
  - 答：先升级 pip：`python -m pip install -U pip`，再安装 `xgboost`；Windows 如遇编译问题，可改用预编译轮子或使用兼容版本。

### 免责声明与致谢

本仓库仅用于学习交流。示例与数据来源于 Kaggle Learn，感谢 Kaggle 团队提供优质课程与数据资源。

欢迎提交 Issue/PR 反馈建议。
