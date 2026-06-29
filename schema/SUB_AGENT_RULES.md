# Sub-agent 分工規則

本檔定義 sub-agent 角色。這些角色先作為規則與流程使用，不強制每次真的啟動多代理工具；複雜任務可依本檔啟動 sub-agent。

## 啟動條件

以下任務建議啟動 sub-agent 分工：

- 正式專案計畫書、活動企劃、政府投標文件。
- 需要大量 raw / wiki / 外部資料整理。
- 需要簡報、表格、會議紀錄等正式交付物。
- 涉及跨專案、跨人物、跨工具的工作。
- Evaluator 發現未達 ABCDE 門檻，需要獨立修正。

## Research / Source Agent

### 目的

收集、整理與驗證來源。

### 輸入

- raw 資料。
- wiki 頁。
- 外部連結、Gmail、Drive、Calendar、政府標案、MCP connector。

### 產出

- 來源清單。
- 事實、待辦、風險、待確認。
- 可萃取到 wiki 的結構化內容。

### 禁止

- 不產出最終交付物。
- 不把推論寫成事實。

## Producer Agent

### 目的

基於 wiki 與已確認來源產出交付物。

### 輸入

- wiki 頁。
- schema 模板。
- Research / Source Agent 的來源摘要。

### 產出

- 簡報大綱。
- 專案計畫書。
- 活動企劃。
- 政府投標文件。
- Email / Line 草稿。
- 表格規格。
- 會議紀錄。

### 禁止

- 不直接使用未整理 raw 作為唯一依據。
- 不跳過模板與輸出標準。

## Evaluator Agent

### 目的

依 ABCDE rubric 評估交付物，決定是否可交付。

### 輸入

- 交付物。
- 計畫。
- 來源清單。
- 對應 schema 與 workflow。

### 產出

- ABCDE 完整評估。
- Pass / Fail。
- 缺口清單。
- 修正要求。

### Gate

- A-D 必須通過。
- E 不可有重大缺口。
- 未通過不可交付。

## Orchestrator Agent

### 目的

負責模式控制、任務分派與最終整合。

### 職責

- 確保任務先進 Plan Mode。
- 確保 Confirm Plan 後才進 Auto Mode。
- 安排 Research、Producer、Evaluator 角色。
- 整合修正結果。
- 只在 Evaluator 通過後交付。

## Sub-agent 資料流

1. Research / Source Agent：raw 與外部資料 -> 來源摘要。
2. Wiki Distillation：依 schema 萃取到 wiki。
3. Producer Agent：基於 wiki 與模板產出交付物。
4. Evaluator Agent：依 ABCDE 評估。
5. Orchestrator Agent：通過後交付；不通過則退回修正。

