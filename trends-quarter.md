# Quarterly Heatmap — LLM 大型代碼庫研究

Source: `papers-classification-v3.json` (n=641 analyzed papers).
Generated: 2026-05-31. Quarters: 2024Q1 → 2026Q2 (2026Q1/Q2 進行中).

### 📋 Quarterly heatmap — markdown table (AI / copy-friendly)

| Sub | 描述 | 2024Q1 | 2024Q2 | 2024Q3 | 2024Q4 | 2025Q1 | 2025Q2 | 2025Q3 | 2025Q4 | 2026Q1 | 2026Q2 | 總計 | 趨勢 |
|---|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|:-:|
| **— A 基礎模型 —** | |  |  |  |  |  |  |  |  |  |  | | |
| `A1` 通用大型語言模型 | GPT-4 / LLaMA / DeepSeek-V3 等通用 LLM 直接拿來做 code 生成，不針對 SWE 任務… | 2 | · | · | 1 | · | · | 4 | 2 | · | · | **9** | ↗ |
| `A2` Code 預訓練模型 | 在大量原始碼上預訓練的 code-specific LLM。代表：StarCoder、CodeLlama、DeepSee… | · | 1 | 1 | 1 | 1 | · | · | 3 | · | · | **7** | → |
| `A3` SWE 任務 fine-tuned 模型 | 針對 SWE-bench 等真實 GitHub issue 解決任務做 RL/SFT 特化的模型（SWE-RL、Ling… | · | · | · | 4 | 3 | 1 | 2 | 7 | · | · | **17** | ↗ |
| `A4` Encoder / Encoder-Decoder code 模型 | CodeBERT / GraphCodeBERT / CodeT5 / UniXcoder 等以 encoder 為主的… | · | · | · | 1 | · | · | · | 2 | · | · | **3** | ↗ |
| `A5` 特殊架構 / Inference 系統 | MoE、reasoning 模型、agent 訓練生態、KV cache 等特殊架構或推理時系統優化。 | 1 | · | · | 1 | · | · | · | 4 | · | · | **6** | ↗ |
| `A6` 通用訓練方法 | LoRA / PEFT / FIM / PPO / scaling laws / federated learning … | · | 1 | · | 1 | · | 1 | 1 | 2 | · | · | **6** | ↗ |
| **— B Benchmark —** | |  |  |  |  |  |  |  |  |  |  | | |
| `B-env` 環境重現 benchmark | 評估 agent 能否從 README 把 repo 跑起來（裝依賴、解環境、跑 test）。EnvBench、SUPE… | · | · | · | 3 | 1 | 1 | · | · | · | · | **5** | → |
| `B1` 函式級 code 生成 benchmark | 單函式或單檔 code generation 基準。HumanEval、MBPP、APPS、BigCodeBench、L… | 2 | 4 | 2 | 4 | 6 | 11 | 6 | 7 | · | · | **42** | ↗ |
| `B2` SWE-bench 系列 (issue 解決) | 輸入 GitHub issue，輸出能通過隱藏測試的 PR。SWE-bench / SWE-bench+ / Multi… | 1 | 1 | 1 | 2 | · | · | 4 | 4 | 1 | 2 | **16** | → |
| `B3` Repo-level 任務 benchmark | 跨多檔的 repo 級 code 生成 / 完成 / 翻譯任務。RepoBench、DevEval、RepoTransB… | 2 | 1 | · | 4 | 2 | · | 3 | 1 | · | 1 | **14** | → |
| `B4` Code translation benchmark | 跨語言 code 翻譯評測。XLCoST / CodeTransOcean / AVATAR / RustRepoTra… | · | · | · | 1 | · | 1 | 1 | 3 | · | · | **6** | ↗ |
| `B5` Agent 互動 benchmark | 評估 agent 工具使用與多輪交互的通用 benchmark。AgentBench、τ-bench、MINT、Inje… | · | · | 1 | · | · | · | 1 | · | · | 1 | **3** | → |
| `B6` 安全 / 品質 benchmark | 評估 LLM 產出 code 的安全漏洞、可靠性、品質。CodeSecEval / SecRepoBench / Red… | 1 | 1 | 3 | 1 | · | 1 | 1 | 4 | · | 1 | **13** | → |
| `B7` Metrics 與 code search | evaluation metric 與 code search 基準。CodeBLEU、CodeXGLUE、CodeSe… | · | · | 1 | 1 | · | · | · | 3 | · | · | **5** | → |
| `B8` 訓練語料 / 資料生成 | 預訓練或 agent 訓練用的大規模 code 資料集生成。The Stack、RepoFusion、SWE-smith… | · | · | · | · | · | 2 | · | 1 | · | · | **3** | ↗ |
| **— C Agent 框架 —** | |  |  |  |  |  |  |  |  |  |  | | |
| `C1` Minimalist agent (Agentless) | 不用 agent loop、固定 pipeline 解 issue（定位 → 修補 → 驗證）。Agentless 為原… | · | 4 | 1 | 1 | 2 | 3 | 4 | 7 | · | · | **22** | ↗ |
| `C2` Full-stack 通用 agent | 從 issue 到 PR 端到端的通用 SWE agent 平台。OpenHands、SWE-agent、AutoCod… | 1 | 1 | 2 | 1 | · | 1 | 2 | 3 | · | · | **11** | → |
| `C3` SWE issue 解決專用 agent | 針對 GitHub issue 解決任務專門設計的 agent（含訓練、debate、verifier）。LingmaA… | 2 | 5 | 4 | 3 | 3 | 8 | 9 | 13 | 1 | 1 | **49** | ↗ |
| `C4` Test-time scaling agent | 推理時用 MCTS / repeated sampling / 動態 re-sample 提升 agent 表現。SWE… | 1 | · | 2 | 2 | 2 | 4 | 3 | 8 | · | · | **22** | ↗ |
| `C5` Multi-agent 協作 | 多個 agent 分工協作（架構師/編碼者/測試者）的 SE 框架。MetaGPT、ChatDev、AutoGen、Ag… | · | · | · | · | · | · | · | 4 | · | · | **4** | 🆕 |
| `C6` Code translation agent | 把 code translation 包成 agent 並加 execution 驗證迴圈。TransAgent、Rep… | · | · | 1 | · | · | · | 3 | 1 | · | 1 | **6** | ↗ |
| `C7` 工具整合 / FL / 文件 agent | 把 fault localization、tool use、文件生成包成 agent。CodeAgent、AgentFL… | 1 | · | · | · | · | · | 1 | · | · | 1 | **3** | → |
| `Cx` 工業案例 (Industry case) | 企業實際導入 LLM/agent 的真實 production case study。Google TF→JAX、ING… | · | · | 1 | · | 1 | · | 2 | 3 | 3 | 3 | **13** | ↗↗ |
| **— D Retrieval / Context —** | |  |  |  |  |  |  |  |  |  |  | | |
| `D1` Iterative retrieval | 反覆「retrieve → 生成 → 用結果再 retrieve」的迴圈式檢索。RepoCoder、Repoformer… | · | · | · | · | · | 2 | 2 | 2 | · | · | **6** | 🆕 |
| `D2` Code graph 檢索 | 把 repo 建成 AST / CFG / DFG / 知識圖譜然後做圖檢索。RepoGraph、CodexGraph、… | 1 | · | 2 | 1 | · | 1 | 2 | 4 | · | · | **11** | ↗ |
| `D3` 跨檔上下文整合 | 在 code completion 時拼入跨檔 / 整個 repo 的上下文。REPOFUSE、PoCo、FragRel… | 1 | 1 | · | 4 | 2 | 7 | 7 | 2 | · | · | **24** | ↗ |
| `D4` RAG / 文件檢索 | retrieval-augmented generation 與文件檢索結合。ReACC、DocPrompting、Li… | · | 1 | 1 | · | 2 | 4 | 7 | 2 | · | · | **17** | ↗ |
| `D5` 長上下文壓縮 / 管理 | 壓縮 prompt 或動態管理 agent 的上下文。LLMLingua、HCP、CAT、KGCompass、Lost … | · | 1 | 1 | · | 2 | · | 3 | 1 | · | 1 | **9** | ↗ |
| `D6` Memory / Planning | 為 agent 設計外部記憶或計畫機制。MemGPT、CodePlan、Memorizing Transformers、… | · | · | · | · | · | · | 1 | 1 | · | · | **2** | ↗ |
| `D7` 靜態分析增強檢索 | 用編譯器 / LSP / 靜態分析資訊輔助 retrieval。STALL+、LLM-Assisted Static A… | · | · | · | · | · | · | · | · | · | 1 | **1** | → |
| `D8` RL for retrieval | 用 reinforcement learning 訓練 retrieval policy。RLCoder、Search-… | · | · | · | · | · | · | · | 1 | · | · | **1** | ↗ |
| `D9` Intent / 規格 / Code QA | 意圖抽取、規格生成、code repo 問答。SpecRover、CoReQA、TIGER、SpecGen、CodeRe… | · | 1 | · | 1 | · | · | · | · | · | · | **2** | ↘↘ |
| **— E Prompting —** | |  |  |  |  |  |  |  |  |  |  | | |
| `E1` ReAct / Reflexion 推理模式 | Thought → Action → Observation 推理迴圈。ReAct、Reflexion、ART。 | · | 1 | · | · | · | · | · | · | 1 | · | **2** | ↘↘ |
| `E2` Chain-of-Thought / 提示工程 | Chain-of-Thought、self-consistency、prompt pattern catalog 等 p… | 1 | · | · | 2 | · | · | 1 | 1 | · | · | **5** | → |
| `E3` Self-debug 自我除錯 | 讓 LLM 看執行結果自己除錯改 code。Self-Debug、OpenCodeInterpreter、Debug l… | · | · | · | · | 1 | · | · | · | · | · | **1** | ↗ |
| **— F APR / Translation / Migration —** | |  |  |  |  |  |  |  |  |  |  | | |
| `F-migration` 通用大規模 migration 方法論 | 不綁特定企業的通用 migration 框架與方法論（與 Cx 工業 case 區別）。CodeMigrator、AIM… | · | · | · | · | 1 | 1 | 1 | 3 | · | · | **6** | 🆕 |
| `F-security` Repo-level 安全審計與漏洞修補 | 對整 repo 做安全審計、自動漏洞修補、smart contract 審計。RepoAudit、ACFIX、Pente… | · | 1 | 1 | 1 | 4 | 1 | 8 | 6 | · | · | **22** | ↗ |
| `F1` Repair agent | 把 program repair 包成自主 agent。RepairAgent、RepairLLaMA、ARJA-CLM… | · | · | 1 | · | · | · | · | · | · | 1 | **2** | ↘↘ |
| `F10` 性能 bug 優化 | 偵測與修復性能 bug、優化效能、bandwidth。BugPilot、LLM Performance Bug、DB P… | · | · | · | · | · | 2 | 5 | · | · | · | **7** | 🆕 |
| `F11` Code 任務 test-time scaling | 針對 refactoring / clone detection / code quality 等具體 code 任務的… | · | · | · | 1 | 2 | 3 | 4 | 5 | · | · | **15** | ↗↗ |
| `F12` Code summarization / 文件 / commit | LLM 自動產生 comment / docstring / commit message / code review。… | 1 | 1 | 3 | 3 | 1 | 3 | 7 | 3 | · | · | **22** | ↗ |
| `F13` Test generation 與 merge | 自動生成 unit test、Test-First、merge conflict 解決。TDD-Bench、TESTEV… | · | · | 1 | 1 | 1 | · | 2 | 2 | · | · | **7** | ↗ |
| `F2` 對話式 / 迭代 repair | 用對話式 LLM 反覆 retry 修補（不是自主 agent）。ChatRepair、Conversational A… | · | · | · | 1 | 1 | 2 | 7 | 2 | · | · | **13** | ↗↗ |
| `F3` C → Rust 安全遷移 | 把 C / C++ 程式自動翻譯成 safe Rust，含驗證與符號方法。VERT、AlphaTrans、Syzygy、… | · | · | · | · | 2 | 3 | 3 | 2 | · | · | **10** | 🆕 |
| `F4` 通用 code translation | 跨任意語言的 code translation 通用方法。SpecTra、UniTrans、SteloCoder、cal… | 1 | 3 | 1 | 3 | 1 | · | 2 | 10 | · | · | **21** | ↗ |
| `F5` Fault localization / 跨語言除錯 | 用 LLM 定位 bug、跨語言錯誤定位、crash report 解析。BLAZE、DEVLoRe、Multi-Age… | · | · | 1 | 2 | 3 | 4 | 4 | 3 | · | · | **17** | ↗ |
| `F6` Refactoring 重構 | 用 LLM 做 Extract Method、識別碼擴展、code smell 重構。MANTRA、Refactorin… | 2 | · | 2 | 3 | 1 | 1 | 1 | 5 | · | · | **15** | → |
| `F7` Repo-level / 統一 APR | 在整個 repo 範圍做 program repair，整合多工具與記憶。ExpeRepair、FixAgent、Hyb… | · | 3 | · | 2 | 3 | 5 | 7 | 4 | · | · | **24** | ↗ |
| `F8` Hallucination 偵測與抑制 | 偵測或抑制 LLM code 中的 API 誤用 / 幻覺。De-Hallucinator、Hallucination … | · | · | 2 | 1 | 3 | 3 | 3 | 6 | · | 1 | **19** | ↗ |
| `F9` 安全 / 可信 code 生成 | constrained decoding、reflection-based control 讓生成 code 更可信 /… | 1 | · | 2 | 1 | 1 | 3 | 6 | 7 | · | · | **21** | ↗ |
| **— G Survey / Empirical —** | |  |  |  |  |  |  |  |  |  |  | | |
| `G1` LLM4SE 大綜論 | LLM for Software Engineering 領域系統性 survey。From Code Foundati… | · | · | · | 2 | 1 | 1 | · | 2 | · | · | **6** | ↗ |
| `G2` APR 領域 survey | LLM-based Automated Program Repair 領域 systematic literature … | · | 2 | · | · | 2 | · | · | · | · | · | **4** | → |
| `G3` Agent for SE survey + 落差研究 | LLM agent for SE 領域 survey + research vs industry 落差實證。Bridg… | · | · | · | · | · | · | · | 4 | · | · | **4** | 🆕 |
| `G4` Code generation 綜論 | Code generation 領域 survey + RACG/RAG 綜述 + 工業 code completion… | · | 1 | · | 1 | · | · | · | 5 | · | · | **7** | ↗ |
| `G5` LLM 通用 survey | 通用 LLM、LLM-as-a-Judge、code 理解能力評估等 broad survey。 | · | · | · | 1 | 3 | · | · | 3 | · | · | **7** | ↗↗ |
| `G6` Empirical / Copilot 使用研究 | GitHub Copilot 等 AI 工具的開發者使用模式、生產力、PR 接受率等實證研究。 | 1 | · | · | 4 | 1 | · | 3 | 8 | · | 6 | **23** | ↗ |
| `G7` Security / Vuln Survey | 軟體安全、漏洞偵測、MCP landscape、reverse engineering 等安全主題 survey。 | · | · | · | 1 | · | · | · | · | · | · | **1** | ↘↘ |
| **— UNKNOWN 未分類 —** | |  |  |  |  |  |  |  |  |  |  | | |
| `UNKNOWN` 未分類 (PDF 損毀) | PDF 損毀無法分類的條目（已標記）。 | · | · | · | · | · | · | 1 | 1 | · | · | **2** | ↗ |
| **該 quarter 全體論文總數 (base rate)** | | **23** | **35** | **38** | **68** | **59** | **80** | **134** | **177** | **6** | **21** | **641** | |

> 趨勢欄僅以 2024Q1–2025Q4 八個完整季度計算（2026 進行中）。↗↗ 暴漲 / ↗ 加速 / → 穩定 / ↘ 退潮 / ↘↘ 大幅退潮 / 🆕 完全新興 / · = 0


## Trend legend
- **↗↗** explosive (late avg ≥ 1.5 with early avg < 0.3)
- **↗** accelerating (late > early × 1.6)
- **→** stable
- **↘** declining (late < early × 0.6)
- **↘↘** sharp decline (late < early × 0.4)
- **🆕** emerging (early == 0, late ≥ 1)
- **—** insufficient data

Base rate (per quarter): 2024Q1=23, 2024Q2=35, 2024Q3=38, 2024Q4=68, 2025Q1=59, 2025Q2=80, 2025Q3=134, 2025Q4=177, 2026Q1=6, 2026Q2=21. Total = 641.

Companion files:
- `trends-quarter.json` — full structured data
- `strategy-time-trends-quarter-heatmap.html` — visual heatmap (CSS-styled)
