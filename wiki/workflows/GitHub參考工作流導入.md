---
type: workflow
status: active
created: 2026-06-27
updated: 2026-06-27
source:
  - schema/GITHUB_WORKFLOW_REFERENCES.md
---

# GitHub 參考工作流導入

## 目的

把 GitHub 上成熟知識庫工作流的優點，轉成適合本第二大腦的操作規則。

## 導入項目

| 項目 | 參考設計 | 本地做法 |
|---|---|---|
| 快速捕捉 | QuickAdd | 所有新資料先進 `raw/inbox` |
| 每日入口 | Foam daily note | 每天建立工作控制台 |
| 任務追蹤 | Obsidian Tasks | 統一 checkbox 任務格式 |
| 查詢彙整 | Dataview | 用 YAML metadata 支援日後查詢 |
| 知識連結 | Foam wikilinks/backlinks | 專案、人物、來源互相連結 |

## 每次新增資料的標準流程

1. 建立 raw note。
2. 補 metadata。
3. 抽取任務與待確認。
4. 更新專案頁或人物頁。
5. 若形成重複流程，更新 `schema` 或 `wiki/workflows`。
6. 若需要每日追蹤，加入 `wiki/dashboards/工作總覽.md`。

## 每週整理流程

1. 檢查 `raw/inbox` 是否有未整理資料。
2. 檢查所有專案頁的 `updated` 是否過舊。
3. 檢查未完成任務。
4. 將完成事項移入專案頁的決策紀錄或產出文件。
5. 更新工作總覽。

