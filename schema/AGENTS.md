# Agent 操作規則

本知識庫的目標是建立「工作型第二大腦複製人」，不是一般筆記庫。

## 固定架構

- `raw`：原始證據層。
- `wiki`：可使用知識層。
- `schema`：規則與流程層。
- `automations`：週期性或可觸發的工作流程設計。

不得任意改名為其他架構，例如 notes、docs、archive、database。

分層規則見 `schema/LAYER_RULES.md`。
分層技能分工見 `schema/SKILL_MAP.md`。
能力模組見 `schema/CAPABILITY_MAP.md`。

## 預設任務模式

收到新資料時：

1. 放入或引用 `raw`。
2. 抽取可重複使用的事實。
3. 更新對應的 `wiki` 頁。
4. 若形成固定做法，更新 `schema` 或 `wiki/workflows`。
5. 若需要週期執行，記錄到 `automations`。

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

## 回答前檢查

- 這是事實、推論，還是待確認？
- 是否有來源？
- 是否應該更新專案頁？
- 是否應該產生待辦？
- 是否涉及外部行動，需要先草稿後確認？
- 是否要更新 metadata 的 `updated` 日期？
- 是否要把新任務加入工作總覽或每日工作控制台？

## 禁止事項

- 不要用漂亮摘要取代來源證據。
- 不要把多個版本的來源混成一個無法追溯的版本。
- 不要自動寄出信件或對外承諾。
- 不要刪除原始資料。

## 參考工作流

已參考 GitHub 上常見 Markdown 知識庫工作流，採用以下設計：

- Foam 式連結與每日筆記。
- Obsidian Tasks 式任務格式。
- Dataview 式 metadata。
- QuickAdd 式快速捕捉。

細節見 `schema/GITHUB_WORKFLOW_REFERENCES.md`。
