# Metadata 規則

為了讓第二大腦可以被搜尋、查詢、自動整理，每個重要 Markdown 頁面都應有 metadata。

## 通用欄位

```yaml
---
type: project | person | workflow | decision | daily | raw | dashboard
status: active | waiting | paused | completed | draft | reference
created: YYYY-MM-DD
updated: YYYY-MM-DD
related_projects: []
related_people: []
source: []
---
```

## 專案頁欄位

```yaml
---
type: project
status: active
created: YYYY-MM-DD
updated: YYYY-MM-DD
priority: high | medium | low |待確認
deadline: YYYY-MM-DD | 待確認
owner: 使用者 | 待確認
stakeholders: []
source: []
---
```

## 人物頁欄位

```yaml
---
type: person
status: active
created: YYYY-MM-DD
updated: YYYY-MM-DD
organization:
role:
related_projects: []
source: []
---
```

## 每日報告欄位

```yaml
---
type: daily
date: YYYY-MM-DD
created: YYYY-MM-DD
updated: YYYY-MM-DD
source: []
---
```

## 任務 inline 欄位

任務用一行呈現，方便之後搜尋：

```md
- [ ] 任務內容 | due: YYYY-MM-DD | owner: 待確認 | project: [[專案名稱]] | source: raw/...
```

若沒有期限：

```md
- [ ] 任務內容 | due: 待確認 | owner: 待確認 | project: [[專案名稱]]
```

