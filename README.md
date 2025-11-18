Project Overview

本專案研究以 事件驅動（Event-Driven） 為核心的盤中市場決策架構，
透過三層式流程：

L0：事件偵測

L1：事件語義化

L2：LLM 決策代理人

探索大型語言模型在盤中事件中的推理能力與決策一致性。

此 Repository 用於論文研究之版本控管，包含：

文獻整理

方法設計

架構實作

實驗流程

研究紀錄



Objectives

建立事件驅動式盤中市場分析流程

使用 XGBoost 進行事件偵測（L0）

設計事件語義化與 Prompt 生成（L1）

建立 LLM 決策代理人（L2）

分析模型推理行為、決策一致性與限制

建立可重現、可驗證的研究架構



System Architecture
L0 — Event Detection (XGBoost)

使用盤中資料建立監督式事件偵測模型

以未來短期報酬 / 波動度作為事件標示

支援不平衡資料訓練

使用 SHAP 分析特徵重要度

L1 — Event Semantic Layer

將 L0 偵測事件轉換成 LLM 可理解的語義化描述

整合最近 1–5 分鐘 K 線等市場上下文

自動生成 L2 的標準化輸入格式

L2 — LLM Decision Agent

輸出：

多 / 空 / 不進場

推理理由

信心度（0.00–1.00）

研究重點：

推理品質

行為一致性

對市場事件敏感度

決策模式（非最終報酬率）



📁 Repository Structure
docs/
   literature/      文獻導讀
   design/          架構與方法設計
notes/              研究紀錄
src/
   L0/              事件偵測模型（XGBoost）
   L1/              語義化與 Prompt 模組
   L2/              LLM 決策代理人
data/
   examples/        資料格式示例（無實際金融資料）
README.md



Literature Overview

所有文獻導讀位於 docs/literature/。
每篇包含：

研究背景

動機

目的

方法

實驗

結果

限制

與本研究之關聯

（不含主觀推論，僅整理原文內容）



Current Progress

Repository 初始化完成

新增第一篇文獻導讀（Park 2024）

L0 / L1 / L2 研究方向已確立

README 已更新為事件驅動版本



Roadmap
L0 — Event Detection

盤中資料前處理

標註策略

XGBoost 訓練

SHAP 分析

L1 — Event Semantics

Prompt 模板設計

事件語義化格式定義

L2 — LLM Decision Agent

初版推理測試

決策格式化

行為分析



Evaluation

事件分布

命中率

LLM 決策一致性

行為模式分析

初步回測
