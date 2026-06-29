# Sub-agent 任務指派模板

用於複雜任務、正式文件、標案、活動、簡報、會議整理或跨資料來源工作。Sub-agent 可以是實際工具，也可以是同一 agent 內的角色分工。

## 任務基本資料

- 任務名稱：
- Confirmed Plan 連結 / 摘要：
- 對應能力模組：
- 對應 workflow：
- 交付期限：
- Orchestrator：

## Research / Source Agent

### 目標

收集、整理與驗證來源，不產出最終交付物。

### 輸入

| 來源 | 路徑 / 連結 | 用途 | 驗證狀態 |
|---|---|---|---|
| raw |  |  | 待確認 |
| wiki |  |  | 待確認 |
| schema |  |  | 是 |
| MCP / 外部資料 |  |  | 待確認 |

### 產出

- 來源清單：
- 事實：
- 待辦：
- 風險：
- 待確認：
- 可萃取到 wiki 的內容：

### 禁止

- 不把推論寫成事實。
- 不產出最終交付物。
- 不執行對外行動。

## Producer Agent

### 目標

基於 wiki、schema 模板與已驗證來源產出交付物。

### 輸入

- Research / Source Agent 來源摘要：
- 對應 wiki 頁：
- 對應 schema 模板：
- 對應輸出標準：

### 產出

| 交付物 | 格式 | 位置 / 輸出方式 | 完成標準 |
|---|---|---|---|
|  |  |  |  |

### 禁止

- 不直接把未整理 raw 當成唯一依據。
- 不跳過模板、workflow 或輸出標準。
- 不寄出、傳送或對外承諾。

## Evaluator Agent

### 目標

依 ABCDE rubric 判斷是否可交付。

### 輸入

- Confirmed Plan：
- 交付物：
- 來源清單：
- 對應 workflow：
- 對應 template：

### 評估輸出

```md
## ABCDE 評估

| 項目 | 結果 | 理由 |
|---|---|---|
| A Accuracy | Pass / Fail |  |
| B Business Fit | Pass / Fail |  |
| C Completeness | Pass / Fail |  |
| D Delivery Quality | Pass / Fail |  |
| E Evidence / Execution Safety | Pass / Major Gap / Minor Gap |  |

## Gate 結論

- 可交付 / 不可交付
```

### Gate

- A-D 必須 Pass。
- E 不可有 Major Gap。
- 未通過時不可交付，必須列缺口、修正方式並重新評估。

## Orchestrator Agent

### 職責

- 確認任務已完成 Plan Mode 與 Confirm Plan。
- 指派 Research、Producer、Evaluator。
- 整合修正。
- 僅在 Evaluator 通過後交付。

### 最終交付紀錄

- 交付物：
- 來源：
- ABCDE 結論：
- 封存位置：
- 後續待辦：

