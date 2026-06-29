---
type: example
status: reference
created: 2026-06-29
updated: 2026-06-29
related_projects: ["[[第二大腦複製人範例專案]]"]
related_people: []
source: ["schema/ABCDE_RUBRIC.md", "schema/EVAL_CHECKLIST.md"]
---

# ABCDE 評估範例

本頁示範交付前 evaluator gate 的完整輸出。A-D 必須 Pass；E 不可有 Major Gap。

## 範例一：可交付

### 情境

使用者要求依已整理 wiki 產出論壇活動企劃草稿。

## ABCDE 評估

| 項目 | 結果 | 理由 |
|---|---|---|
| A Accuracy | Pass | 活動日期、對象、來源頁與待確認項目已標示；未確認資訊未寫成事實。 |
| B Business Fit | Pass | 內容符合論壇籌備場景，語氣正式，可供內部討論。 |
| C Completeness | Pass | 已包含目標、受眾、議程、講者、分工、時程、風險與待確認。 |
| D Delivery Quality | Pass | 結構清楚，可直接複製到企劃書或簡報大綱。 |
| E Evidence / Execution Safety | Minor Gap | 部分講者可出席性仍待確認，但已清楚標示，不影響內部草稿使用。 |

## Gate 結論

- 可交付。

## 範例二：不可交付

### 情境

使用者要求產出政府投標文件，但只提供標案名稱，尚未提供招標文件或正式公告來源。

## ABCDE 評估

| 項目 | 結果 | 理由 |
|---|---|---|
| A Accuracy | Fail | 缺少正式招標文件，無法確認資格、截止時間、文件清單與評選標準。 |
| B Business Fit | Pass | 文件方向符合投標需求。 |
| C Completeness | Fail | 缺少資格要求、必要附件、時程與風險判讀。 |
| D Delivery Quality | Fail | 只能形成初步架構，不能作為正式投標文件。 |
| E Evidence / Execution Safety | Major Gap | 若直接交付，可能造成錯誤投標判斷或漏件風險。 |

## Gate 結論

- 不可交付。

## 缺口

- 缺正式招標公告或招標文件。
- 缺投標截止時間、資格條件、文件清單與評選標準。
- 缺來源日期與版本。

## 修正方式

- 請使用者提供標案 PDF、政府採購網連結或正式公告。
- Research / Source Agent 先整理資格、文件、時程、風險。
- Producer Agent 只在來源完整後產出投標文件草稿。
- Evaluator Agent 重新執行 ABCDE gate。

## 重新評估時間

- 取得正式標案來源後立即重新評估。

