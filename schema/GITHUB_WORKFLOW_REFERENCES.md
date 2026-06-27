# GitHub 工作流程參考

本檔整理從 GitHub 上常見個人知識庫與 Obsidian 工作流專案可借用的設計。這些做法只作為本知識庫的參考，不取代固定架構 `raw / wiki / schema`。

## 參考來源

| 來源 | 可借用設計 | 本地化做法 |
|---|---|---|
| Foam | Markdown、wikilinks、backlinks、daily notes、templates | 保留純 Markdown，建立每日筆記、連結與模板 |
| Obsidian Tasks | 全庫任務查詢、到期日、週期任務、完成狀態 | 統一使用 checkbox 任務格式與日期欄位 |
| Obsidian Dataview | 用 YAML frontmatter 與 inline fields 查詢 Markdown | 每個 wiki 頁補 metadata，方便未來彙整 |
| QuickAdd | 快速捕捉、模板、巨集 | 建立 inbox 捕捉流程與固定輸入模板 |

## 對本知識庫的採用原則

### 1. 每個可查詢頁面都要有 metadata

專案、人物、流程、每日報告都應該在檔案開頭保留 YAML frontmatter。

必要欄位：

```yaml
---
type:
status:
created:
updated:
related_projects:
related_people:
source:
---
```

### 2. 任務格式要統一

任務採用 Markdown checkbox，並盡量保留日期、負責人與來源。

```md
- [ ] 任務內容 | due: YYYY-MM-DD | owner: 使用者 / 待確認 | source: raw/...
```

完成時：

```md
- [x] 任務內容 | done: YYYY-MM-DD | source: raw/...
```

### 3. 連結比資料夾更重要

資料夾負責基本分類，連結負責工作脈絡。

建議連結：

- 專案頁連到人物頁。
- 專案頁連到原始資料。
- 每日報告連到專案頁。
- 決策紀錄連到來源與後續待辦。

### 4. 每日筆記是工作流入口

每日筆記不是日記，而是每天的工作控制台：

- 今天要處理什麼？
- 哪些事要回覆？
- 哪些事等對方？
- 哪些專案有風險？
- 今天新增了哪些 raw 資料？

### 5. 儀表板只彙整，不放原始證據

儀表板放在 `wiki/dashboards`，用途是快速掃描。來源證據仍留在 `raw`，正式整理仍在 `wiki/projects` 與 `wiki/people`。

## 不採用的做法

- 不把整個資料庫改成複雜的 Obsidian plugin 專案。
- 不把所有資料都放進每日筆記。
- 不使用無法追溯來源的自動摘要取代 raw。
- 不讓自動化直接對外寄送或承諾。

