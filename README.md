# DataMine Studio · 智能数据挖掘工作台

一款支持 **纯前端浏览器端运行（可直接免费部署到 GitHub Pages / 国内 EdgeOne Pages）** 与 **本地 Python FastAPI 后端加速** 双模式的现代化数据挖掘软件，采用玻璃态 Bento 网格设计与深浅极光双主题。

## 运行模式（自动切换）

- **在线纯前端模式（GitHub Pages / 国内静态托管）**：内置完整的 TypeScript 浏览器数据挖掘引擎与 SheetJS Excel 解析，**无需任何后端服务器**，访客数据全程在本地浏览器内存中计算、互不干扰、隐私安全零泄露。
- **本地 Python 增强模式**：双击 `start.bat` 或运行 `python run.py`，自动连接 FastAPI + scikit-learn + statsmodels + jieba 后端。

## 一键部署到 GitHub Pages（并加速国内访问）

仓库已内置自动部署工作流 [`.github/workflows/deploy-pages.yml`](.github/workflows/deploy-pages.yml)：

1. 在 GitHub 新建一个公开仓库（如 `datamine-studio`）
2. 在本项目目录执行推送命令：
   ```powershell
   git remote add origin https://github.com/<你的用户名>/<仓库名>.git
   git push -u origin main
   ```
3. 打开 GitHub 仓库 → **Settings → Pages → Build and deployment → Source** 选择 **GitHub Actions**
4. 等待约 1 分钟自动构建完成，即可获得免费在线访问网址：`https://<你的用户名>.github.io/<仓库名>/`

### 国内直连高速访问方案（免翻墙、免费）
推送到 GitHub 后，推荐将同一个 GitHub 仓库直接关联到以下国内免费静态托管平台（自动跟随 GitHub 推送构建，国内毫秒级打开）：
- **腾讯云 EdgeOne Pages**（支持 GitHub 一键导入，根目录填 `frontend`，构建命令 `npm run build`，输出目录 `dist`）
- **阿里云 ESA Pages**（支持 GitHub 仓库绑定，同样构建目录 `frontend` / 输出 `dist`）

## 核心功能模块

1. **数据导入与预处理**：CSV/TSV/Excel/JSON 上传、5 套内置示例数据、实时表格搜索、字段完整度进度条、缺失值/去重/异常值截断/缩放/编码与多步撤销
2. **探索性分析与可视化 (EDA)**：统计摘要、直方图 + KDE、相关性热力图、散点趋势图、分组箱线图，所有图表支持全屏弹窗与高清 PNG 导出
3. **经典数据挖掘**：K-Means / 层次聚类 / DBSCAN（含 PCA 投影与肘部法）、分类建模（混淆矩阵 / ROC-AUC / 特征重要性）、回归预测（拟合图 / 残差图）、异常检测、Apriori 关联规则
4. **时间序列预测**：Holt-Winters 指数平滑、趋势拟合、回测 RMSE/MAE/MAPE、95% 置信区间与季节性分解
5. **文本挖掘分析**：中英文分词、语义词云、高频词、TF-IDF 关键词、情感极性分布与逐条明细筛选
6. **结果与报告导出**：清洗数据 CSV/Excel 导出、精美 HTML 报告与 Markdown 报告一键下载与在线预览
