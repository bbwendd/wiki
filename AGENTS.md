# AGENTS.md

本 repo 是工作型第二大腦與 AI 專案作業系統。任何 agent 進入本 repo，都必須先遵守本檔。

## 必讀順序

1. `schema/_system/START_HERE.md`
2. `schema/EXECUTION_MODE_RULES.md`
3. `schema/CONFIRM_PLAN_CHECKLIST.md`
4. `schema/SUB_AGENT_RULES.md`
5. `schema/ABCDE_RUBRIC.md`
6. `schema/EVAL_CHECKLIST.md`

## 強制模式

所有任務都必須先進 Plan Mode。即使是小任務，也至少要形成簡短計畫。

只有在使用者明確確認計畫後，才可進入 Auto Mode。有效確認包含：

- `確認計畫`
- `同意此計畫`
- `照這個計畫執行`
- 其他語意明確的同意執行文字

沉默、模糊回覆、單純提供更多資料，不算 Confirm Plan。

## 交付門檻

交付前必須依 `schema/ABCDE_RUBRIC.md` 完整自評。

- A Accuracy：必須通過。
- B Business Fit：必須通過。
- C Completeness：必須通過。
- D Delivery Quality：必須通過。
- E Evidence / Execution Safety：不可有重大缺口。

未達門檻時不可交付；必須退回修正，列出缺口、修正方式，再重新評估。

## Sub-agent 規則

Sub-agent 先作為角色與流程規則使用，不強制每次啟動多代理工具。複雜任務可依 `schema/SUB_AGENT_RULES.md` 分派：

- Research / Source Agent
- Producer Agent
- Evaluator Agent
- Orchestrator Agent

## 知識流

專案知識必須先進 `raw`，再依 `schema` 萃取到 `wiki`。產出簡報、企劃書、投標文件、會議紀錄或其他交付物時，應基於 `wiki` 與可追溯來源。

## 禁止事項

- 不可跳過 Plan Mode。
- 不可未經 Confirm Plan 直接 Auto Mode。
- 不可未做 ABCDE 評估就交付。
- 不可把未確認資訊寫成事實。
- 不可自動寄信、傳訊息、修改行程或對外承諾。

