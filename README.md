# 第二大腦複製人

這個資料夾是你的工作型第二大腦，目標不是單純存筆記，而是讓 AI 可以讀懂你的工作脈絡、替你整理專案、產出文件草稿、追蹤待辦，並支援自動化工作流程。

核心架構固定為三層：

1. `raw`：原始資料，只保存來源與證據，不過度整理。
2. `wiki`：整理後可使用的知識頁，供日常查找、決策、寫作與交接使用。
3. `schema`：規則、模板、工作流程與 AI 操作指令。

AI 或人員進入本資料夾時，請先讀：

1. `AGENTS.md`
2. `schema/_system/START_HERE.md`
3. `schema/EXECUTION_MODE_RULES.md`
4. `schema/CONFIRM_PLAN_CHECKLIST.md`
5. `schema/SUB_AGENT_RULES.md`
6. `schema/ABCDE_RUBRIC.md`
7. `schema/MCP_CONNECTOR_MAP.md`
8. `wiki/首頁.md`
9. `wiki/dashboards/工作總覽.md`

## Karpathy 方法在這裡的做法

這裡採用「先保存原始資料，再逐步蒸餾成可用知識，最後把可重複任務變成流程」的做法：

1. 收集：任何信件、會議紀錄、檔案、想法、專案資訊，先進 `raw`。
2. 整理：把重複使用的事實、決策、人物、專案，整理到 `wiki`。
3. 規則化：把固定格式、判斷標準、輸出習慣，沉澱到 `schema`。
4. 自動化：把每天或每週重複發生的任務，登記到 `automations`。

## 目前優先目標

- 建立日常工作助理流程。
- 支援計畫書、簡報、會議整理、Email 回覆追蹤與專案待辦。
- 讓 AI 回答時能先查規則、再查整理頁，需要證據時才查原始資料。
- 外部行動採「先草稿後確認」，不自動寄信、不自動承諾。

## 標準工作流程

所有任務都採用以下流程：

1. Plan Mode：先釐清目標、交付物、資料來源、風險與驗證方式。
2. Confirm Plan：使用者必須明確回覆「確認計畫」或同義確認文字。
3. Auto Mode：確認後才可執行、修改檔案、產出正式交付物。
4. Sub-agent Flow：複雜任務依規則分派 Research、Producer、Evaluator 角色。
5. ABCDE Gate：交付前完整自評；A-D 必過，E 不可有重大缺口。

若 ABCDE 未達標準，不可交付，必須退回修正。

## v1.1 落地補強

為了讓流程能被穩定複製，已補上以下可直接套用的範本與狀態表：

- `schema/templates/confirm_plan.md`：Plan Mode 進入 Auto Mode 前的確認模板。
- `schema/templates/subagent_task.md`：Research、Producer、Evaluator、Orchestrator 任務指派模板。
- `schema/MCP_CONNECTOR_MAP.md`：Gmail、Calendar、Drive、GitHub、Canva、Slack、Line 替代方案、音檔轉錄與 web search 的能力邊界。
- `wiki/examples/ABCDE評估範例.md`：可交付與不可交付的 evaluator gate 範例。
- `wiki/workflows/交付封存流程.md`：交付後保存版本、來源、評估與待辦的流程。
- `automations/AUTOMATION_STATUS.md`：自動化啟用、授權、失敗與 no-hit 狀態表。
- `wiki/projects/第二大腦複製人範例專案.md`：標準專案頁示範。

## 8 大能力模組

- 溝通助理：Email、Line、英文溝通、國外講者邀請。
- 文件寫作：專案計畫書、活動企劃、政府投標文件。
- 簡報與美編：簡報、DM、成果發表素材。
- 表格與資料：Excel、名單、預算、追蹤表。
- 專案管理：狀態、待辦、期限、風險、等待對方。
- 會議助理：會議紀錄、逐字稿、會議資料整理。
- 行程與活動籌備：會議排程、論壇、研討會、成果發表會。
- 政府標案與研究：專業資料搜尋、標案閱讀、標案流程、投標文件。

## 已導入的 GitHub 工作流參考

- Foam：Markdown、wikilinks、daily notes、templates。
- Obsidian Tasks：全庫任務查詢、到期日、週期任務。
- Obsidian Dataview：YAML metadata 與 Markdown 查詢思路。
- QuickAdd：快速捕捉、模板、巨集流程。

本地化後的重點檔案：

- `schema/GITHUB_WORKFLOW_REFERENCES.md`
- `schema/MCP_CONNECTOR_MAP.md`
- `schema/METADATA_RULES.md`
- `schema/templates/daily_note.md`
- `schema/templates/confirm_plan.md`
- `schema/templates/subagent_task.md`
- `schema/templates/task_line.md`
- `wiki/dashboards/工作總覽.md`
