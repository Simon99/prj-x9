# 運用 LLM 修改與維護大型代碼庫 — arXiv 文獻總覽

26 篇 2026 年 arXiv 預印本的全文核對總覽，分 A/B/C/D 四類；其中 5 篇含 infographic 圖解（A1 / A4 / B1 / C1 / D1）。

🔗 **線上閱讀**：[index.html](./index.html)（或直接打開 GitHub Pages URL）

## 分類

| 類 | 主題 | 篇數 |
|---|---|---|
| **A** | 業界／真實世界案例 | 8 |
| **B** | repo 層級修改與維護的方法／框架 | 9 |
| **C** | 版本升級／遷移／現代化 | 4 |
| **D** | 大規模實證研究與評測 | 5 |

## 圖解版

含 13 張 infographic（base64 內嵌，~5 MB），覆蓋以下 5 篇：

- **A1** Nikolov et al. 2026 · TF→JAX Migration at Google · arXiv:2603.27296（4 張）
- **A4** Peralta et al. 2026 · Why Agentic PRs Merged or Rejected · MSR '26 · arXiv:2605.22534（1 張）
- **B1** Liu et al. 2026 · DAIRA · arXiv:2603.22048（3 張）
- **C1** Lam et al. 2026 · SWE-Chain · arXiv:2605.14415（2 張）
- **D1** Chen et al. 2026 · SWE-CI · arXiv:2603.03823（3 張）

## 引用規範

- 每一事實／數字標註至原論文章節（§）與頁碼（p.）
- 圖中描述性敘述為繁體中文；技術術語、產品名稱、API、統計符號保留英文
- 本報告所有結論均經 PDF 全文逐頁核對

## 產製方式

- Markdown 原稿由多 agent 全文重讀後產出
- HTML 由 React + marked.js 渲染，單檔自含（不需後端）
- Infographic 由 Gemini Nano Banana Pro 2K 產生
