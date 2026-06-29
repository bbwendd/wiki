# Agent 操作規則

本知識庫的目標是建立「工作型第二大腦複製人」，不是一般筆記庫。

## 強制治理流程

所有任務都必須遵守：

1. Plan Mode：收斂需求，形成可執行計畫。
2. Confirm Plan：使用者必須明確確認計畫。
3. Auto Mode：確認後才可執行。
4. Evaluator Gate：交付前依 ABCDE rubric 完整自評。

規則詳見：

- `schema/EXECUTION_MODE_RULES.md`
- `schema/CONFIRM_PLAN_CHECKLIST.md`
- `schema/SUB_AGENT_RULES.md`
- `schema/ABCDE_RUBRIC.md`
- `schema/EVAL_CHECKLIST.md`
- `schema/MCP_CONNECTOR_MAP.md`

未達 ABCDE gate 時不可交付，必須退回修正。
正式交付後，依 `wiki/workflows/交付封存流程.md` 保存交付物、來源、評估結論與後續待辦。

## 固定架構

- `raw`：原始證據層。
- `wiki`：可使用知識層。
- `schema`：規則與流程層。
- `automations`：週期性或可觸發的工作流程設計。

不得任意改名為其他架構，例如 notes、docs、archive、database。

分層規則見 `schema/LAYER_RULES.md`。
分層技能分工見 `schema/SKILL_MAP.md`。
能力模組見 `schema/CAPABILITY_MAP.md`。
外部工具與 connector 邊界見 `schema/MCP_CONNECTOR_MAP.md`。

## 預設任務模式

收到新資料時：

1. 先進 Plan Mode。
2. 通過 Confirm Plan 後才進 Auto Mode。
3. 放入或引用 `raw`。
4. 抽取可重複使用的事實。
5. 更新對應的 `wiki` 頁。
6. 若形成固定做法，更新 `schema` 或 `wiki/workflows`。
7. 若需要週期執行，記錄到 `automations`。
8. 交付前執行 ABCDE Evaluator Gate。
9. 交付後執行交付封存，必要時更新 `automations/AUTOMATION_STATUS.md`。

若使用者要求建立或改善第二大腦，先補齊每層規則與 skill map，再建立具體專案頁或自動化。

## 能力模組

使用者的工作型 AI 分身應覆蓋以下 8 類能力：

- 溝通助理。
- 文件寫作。
- 簡報與美編。
- 表格與資料。
- 專案管理。
- 會議助理。
- 行程與活動籌備。
- 政府標案與研究。

任務進來時，先查 `schema/CAPABILITY_MAP.md`，再查對應 workflow 與模板。

## v1.1 可套用模板

- Plan Mode 進入 Auto Mode 前，可套用 `schema/templates/confirm_plan.md`。
- 複雜任務、正式文件、標案、活動或跨資料來源任務，可套用 `schema/templates/subagent_task.md`。
- 交付前可參考 `wiki/examples/ABCDE評估範例.md`。
- 自動化啟用、授權、失敗與 no-hit 狀態，記錄於 `automations/AUTOMATION_STATUS.md`。

## 回答前檢查

- 是否仍在 Plan Mode，尚未取得 Confirm Plan？
- 這是事實、推論，還是待確認？
- 是否有來源？
- 是否應該更新專案頁？
- 是否應該產生待辦？
- 是否涉及外部行動，需要先草稿後確認？
- 是否需要查 `schema/MCP_CONNECTOR_MAP.md` 確認 connector 邊界？
- 是否要更新 metadata 的 `updated` 日期？
- 是否要把新任務加入工作總覽或每日工作控制台？
- 正式交付後是否需要建立交付封存紀錄？

## 禁止事項

- 不要用漂亮摘要取代來源證據。
- 不要把多個版本的來源混成一個無法追溯的版本。
- 不要跳過 Plan Mode。
- 不要未經 Confirm Plan 直接進入 Auto Mode。
- 不要未做 ABCDE 評估就交付。
- 不要自動寄出信件或對外承諾。
- 不要刪除原始資料。

## 參考工作流

已參考 GitHub 上常見 Markdown 知識庫工作流，採用以下設計：

- Foam 式連結與每日筆記。
- Obsidian Tasks 式任務格式。
- Dataview 式 metadata。
- QuickAdd 式快速捕捉。

細節見 `schema/GITHUB_WORKFLOW_REFERENCES.md`。
