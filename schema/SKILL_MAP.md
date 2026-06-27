# 分層 Skill Map

本檔定義第二大腦每一層需要的能力。這不是額外資料夾，而是 AI 操作時的技能分工。

## Skill 1：Raw Intake Skill

### 何時使用

- 使用者提供新 Email、會議紀錄、附件、口述背景、外部連結或任何未整理資料。
- 需要先保存來源，再做抽取。

### 輸入

- 原文、檔案、連結、摘要、使用者口述。

### 產出

- `raw/inbox/YYYY-MM-DD_來源_主題.md`
- 抽取：事實、待辦、風險、待確認、可能對應專案與人物。

### 檢查

- 是否保留來源？
- 是否標日期？
- 是否避免過度改寫？
- 是否把不確定內容標成 `待確認`？

## Skill 2：Wiki Distillation Skill

### 何時使用

- raw 資料已足以更新專案、人物、決策或流程。
- 使用者要求整理專案狀態、建立頁面、更新待辦、產出工作摘要。

### 輸入

- raw note、既有 wiki 頁、使用者補充。

### 產出

- `wiki/projects/*`
- `wiki/people/*`
- `wiki/decisions/*`
- `wiki/workflows/*`
- `wiki/dashboards/*`

### 檢查

- 是否有 metadata？
- 是否連回 raw？
- 是否更新待辦與風險？
- 是否保留 `待確認`？

## Skill 3：Schema Distillation Skill

### 何時使用

- 使用者修正輸出格式。
- 某種任務重複出現。
- 某個模板、檢查表或規則應該被固定下來。

### 輸入

- 使用者修正、成功輸出、重複流程、常見錯誤。

### 產出

- `schema/templates/*`
- `schema/*_RULES.md`
- `schema/EVAL_CHECKLIST.md`
- `schema/AGENTS.md`

### 檢查

- 是否是可重複規則，而不是單次專案細節？
- 是否足夠簡短、可執行？
- 是否會幫下一個 AI 少犯錯？

## Skill 4：Automation Design Skill

### 何時使用

- 使用者想把流程自動化。
- 任務有固定頻率或事件觸發條件。
- 需要建立每日、每週、會議後、Email 追蹤等流程。

### 輸入

- workflow、輸入來源、頻率、輸出格式、確認規則。

### 產出

- `automations/*`
- `wiki/workflows/*`
- 必要時更新 `schema/WORKFLOW_RULES.md`

### 檢查

- 是否有 no-hit 回報？
- 是否有失敗回報？
- 是否維持先草稿後確認？
- 是否沒有自動做外部承諾？

## Skill 5：Daily Operator Skill

### 何時使用

- 使用者要求今日工作整理、待回覆清單、每日報告、工作總覽。

### 輸入

- Gmail、Calendar、Slack、Drive、專案 wiki、使用者補充資料。

### 產出

- 每日工作助理報告。
- `wiki/dashboards/工作總覽.md` 更新。
- 必要時更新專案頁待辦。

### 固定章節

- 急需回覆
- 近期需回覆
- 等待對方
- 僅供參考
- 每日工作進度
- 待確認事項

### 檢查

- 沒有命中也要回報。
- 不把廣告、系統通知、電子報當成待回覆。
- 對外行動只產生草稿。

## Skill 6：Capability Router Skill

### 何時使用

- 使用者提出 Email、簡報、計畫書、活動企劃、表格、專案管理、會議、行程、標案、英文溝通或活動籌備需求。

### 輸入

- 使用者任務描述。
- 相關 raw、wiki、schema 或外部來源。

### 產出

- 對應能力模組。
- 應讀規則。
- 應套用 workflow。
- 應使用模板。
- 需確認事項。

### 檢查

- 是否已對應到 `schema/CAPABILITY_MAP.md` 的 8 大模組？
- 是否有至少一個 workflow 或模板可用？
- 是否涉及對外行動，需要先草稿後確認？
