# Karpathy 方法：本地操作版

這裡的 Karpathy 方法不是做一般筆記整理，而是把你的工作資料當成訓練資料，逐步建立一個能模仿你工作方式的 AI 工作助理。

## 核心概念

1. Dataset first：先累積高品質原始資料。
2. Tight feedback loop：每次產出後修正，讓規則越來越貼近使用者。
3. Evaluation：用固定檢查表判斷輸出是否可用。
4. Distillation：把成功案例變成模板、規則與流程。
5. Automation：把穩定流程交給排程或事件觸發。

## 對應到本知識庫

| Karpathy 概念 | 本知識庫做法 |
|---|---|
| Dataset | `raw` 原始資料 |
| Labels / Examples | 使用者確認過的草稿、文件、回覆、報告 |
| Model context | `wiki` 整理後知識 |
| System prompt | `schema` 規則與模板 |
| Eval | `schema/EVAL_CHECKLIST.md` |
| Automation | `automations` 與 `wiki/workflows` |

## 工作助理如何學會你

每次任務完成後，應判斷是否留下以下內容：

- 這次輸入資料是什麼？
- 好的輸出長什麼樣？
- 使用者修正了哪些地方？
- 哪些規則下次要記住？
- 這是否可以變成固定流程？

## 最小可行循環

1. 使用者丟資料或任務。
2. AI 先查 `schema` 與 `wiki`。
3. AI 產出草稿或整理結果。
4. 使用者修正。
5. 將修正後版本存回 `raw` 或 `wiki`。
6. 將可重複規則寫入 `schema`。

## 成功標準

- AI 能知道目前有哪些重要專案。
- AI 能指出每個專案的下一步、風險與待確認事項。
- AI 能依你的口吻產出 Email、簡報大綱、計畫書段落。
- AI 不會把未確認資訊寫成已確認。
- AI 能固定整理每日工作狀態，沒有命中也會回報。

