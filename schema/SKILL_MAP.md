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

## Skill 7：Plan Controller Skill

### 何時使用

- 所有任務一開始都使用。

### 輸入

- 使用者需求。
- repo 狀態、schema、wiki、raw、外部來源。

### 產出

- Plan Mode 計畫。
- Confirm Plan 檢查結果。
- Auto Mode 進入條件。
- 必要時套用 `schema/templates/confirm_plan.md`。

### 檢查

- 是否有目標、交付物、資料來源、驗證方式？
- 是否列出風險與不可交付條件？
- 是否已取得明確 Confirm Plan？

## Skill 8：Sub-agent Orchestrator Skill

### 何時使用

- 複雜任務、正式文件、標案、活動、簡報、會議整理或跨資料來源任務。

### 輸入

- Confirmed plan。
- raw / wiki / schema。
- 外部來源或 MCP connector 結果。

### 產出

- Research / Source Agent 任務。
- Producer Agent 任務。
- Evaluator Agent 任務。
- 最終整合結果。
- 必要時套用 `schema/templates/subagent_task.md`。

### 檢查

- Producer 是否基於 wiki 與來源？
- Evaluator 是否完整執行 ABCDE？
- 未通過時是否退回修正？

## Skill 9：Evaluator Gate Skill

### 何時使用

- 每次正式交付前。

### 輸入

- 交付物。
- Confirmed plan。
- 來源清單。
- 對應 workflow、template、schema。

### 產出

- 完整 ABCDE 評估。
- 可交付 / 不可交付結論。
- 若不可交付，列缺口與修正方式。

### 檢查

- A-D 是否全部 Pass？
- E 是否沒有 Major Gap？
- 是否完整顯示評估？
- 若未達標，是否停止交付並退回修正？

## Skill 10：Connector Router Skill

### 何時使用

- 任務需要 Gmail、Calendar、Drive、GitHub、Canva、Slack、Line、音檔轉錄、Browser 或 Web Search。
- 任務需要判斷 connector 是否已授權、可用或需要替代資料來源。

### 輸入

- 使用者任務。
- `schema/MCP_CONNECTOR_MAP.md`。
- 可用 connector 與授權狀態。

### 產出

- 建議使用的 connector。
- 備援資料取得方式。
- 可執行動作與需再次確認的動作。
- 失敗回報或 no-hit 回報格式。

### 檢查

- 是否維持先草稿後確認？
- 是否避免未授權寄送、排程、刪除、分享或承諾？
- 無 connector 時是否提供貼上文字、截圖、附件或手動匯出的替代方式？

## Skill 11：Delivery Archive Skill

### 何時使用

- 正式交付物已通過 ABCDE evaluator gate。
- 任務產出文件、簡報、表格、草稿、會議紀錄、投標文件或活動企劃。

### 輸入

- 交付物。
- 來源清單。
- ABCDE 評估。
- 對應專案頁或決策頁。

### 產出

- 交付封存紀錄。
- 專案頁更新。
- 後續待辦。
- 必要時更新 schema、workflow 或 automation status。

### 檢查

- 是否連回專案頁？
- 是否保留來源與日期？
- 是否保存 ABCDE 結論？
- 是否把後續待辦寫成標準 checkbox？
