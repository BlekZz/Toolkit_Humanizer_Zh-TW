# tw-work-writing 1.0.0 發布驗收

驗收日期為 2026-11-27（台灣時間）。本版包含五種場景，每個場景都支援潤稿與根據已知資料起草。安裝包根目錄是 `tw-work-writing/`，包含 `SKILL.md`、MIT `LICENSE` 和六份參考資料。

## 36 個案例的驗收結果

以三個獨立的 Codex 子代理分批處理，各批 12 案。試跑者只能看到請求和技能指引，依各案判斷入口與參考檔。完成後依案例的 `mode`、`scene` 和 `checks` 逐案比對。每批在同一個子代理上下文內依序處理。此處紀錄的是合成素材的行為驗收，CLI 實測另列於下方。[案例資料](../evals/cases.json)

完整試跑 36 案，含 14 案潤稿與 22 案起草。首次 35 案通過。第 36 案的首次成稿用「其中 6 件」把核准件數納入當日收件口徑。新增報告規則並重跑後，主管稿分別寫出收件 18 件、核准 6 件，客戶稿只交代個案收件及待審核。最終 36 案全數通過。

| # | 案例 | 入口 | 場景 | 成稿的驗收訊號 |
| --- | --- | --- | --- | --- |
| 1 | `report-edit-denominator` | 潤稿 | 報告 | 4.2% 降至 3.8%，兩週皆排除測試單，未將降幅歸因於流程優化。 |
| 2 | `report-edit-source` | 潤稿 | 報告 | 保留業界調查歸屬、約 47% 及每週兩次以上，出處缺項列在正文外。 |
| 3 | `report-edit-clean` | 潤稿 | 報告 | 原稿照錄，保留中位數、相同條件與尖峰未測。 |
| 4 | `report-draft-limit` | 起草 | 報告 | 4 月 84%、5 月 89%，保留入口變動、結案後 24 小時發問卷及回收數缺項。 |
| 5 | `report-draft-no-decision` | 起草 | 報告 | 內測完成、兩項資安待複核，12 月 3 日維持未定案的提議。 |
| 6 | `support-edit-estimate` | 潤稿 | 客服 | 已收申請，核准後預計 3 至 5 個工作天退回原付款方式。 |
| 7 | `support-edit-conflict` | 潤稿 | 客服 | 以已收退貨且尚未退款為準，入帳依發卡銀行，舊稿衝突列在正文外。 |
| 8 | `support-draft-no-eta` | 起草 | 客服 | 今天上午已交物流，今天能否送達仍未確認。 |
| 9 | `support-draft-too-little` | 起草 | 客服 | 先索取適用政策及案件摘要，未判定退款資格。 |
| 10 | `support-draft-policy-branches` | 起草 | 客服 | 列出兩種寄回運費條件，保留換貨原因尚未確認。 |
| 11 | `support-draft-protected-label` | 起草 | 客服 | 照錄介面上的實際按鈕，正文沒有未提供的錯誤處理。 |
| 12 | `procedure-edit-version-order` | 潤稿 | SOP | 保留桌面版 2.4.1、角色、備份與空佇列。顯示 `Paused` 才能匯出。 |
| 13 | `procedure-edit-version-branches` | 潤稿 | SOP | 分開 3.0.x 和 3.1.x，`File name` 仍是 3.1.x 的選填步驟。 |
| 14 | `procedure-edit-missing-transition` | 潤稿 | SOP | 1.7 版及雙人覆核保留，正文只到在 `Batch Import` 點選 `Upload CSV`。 |
| 15 | `procedure-draft-known-order` | 起草 | SOP | 依 5.2 版已知路徑操作，預覽顯示 `Ready` 才可下載。 |
| 16 | `procedure-draft-missing-middle` | 起草 | SOP | 4.6 版先關閉自動同步，步驟只到在 `Stock Ops` 選取 `Import Batch`。 |
| 17 | `procedure-draft-unknown-order` | 起草 | SOP | 問兩個動作應先執行哪一個。 |
| 18 | `procedure-draft-unknown-version` | 起草 | SOP | 7.1 與 7.2 各自保留步驟，先確認環境版本。 |
| 19 | `procedure-draft-customer-overlay` | 起草 | 客服與 SOP | 保留 Android App 6.3、原下單帳號及 `PDF receipt` 的操作順序。 |
| 20 | `announcement-edit-effective-scope` | 潤稿 | 公告 | 12 月 10 日 10:00 台灣時間起適用，沒有把發邀請的權限限縮到管理員。 |
| 21 | `announcement-edit-maintenance-window` | 潤稿 | 公告 | 03:00–05:00 UTC+8 維持預計時段，只有需離線報表的管理員須提前下載。 |
| 22 | `announcement-edit-incident-conflict` | 潤稿 | 公告 | 18:10 是首次回報，影響僅限台灣區網頁版發票下載，移出舊稿承諾。 |
| 23 | `announcement-draft-confirmed-times` | 起草 | 公告 | 保留 16:00 更新及 17:00 預計恢復，並交代可用原帳號查網頁版。 |
| 24 | `announcement-draft-no-commitments` | 起草 | 公告 | 只建議已收到同月報表的人使用附件，狀態頁只列為連結。 |
| 25 | `announcement-draft-unknown-scope` | 起草 | 公告 | 15:25 接獲兩個工作區回報，維持範圍待查，處置及時間缺項列正文外。 |
| 26 | `announcement-draft-effective-date-missing` | 起草 | 公告 | 稿件標待確認，Pro 企業工作區管理員僅在生效後須操作。 |
| 27 | `announcement-draft-partial-recovery` | 起草 | 公告 | 11:20 只確認預覽恢復，批次匯出仍不可用，12:30 是下次更新。 |
| 28 | `marketing-edit-voice-cta` | 潤稿 | 行銷 | 以「你」面向社團新手，保留「查看範本」及網址。 |
| 29 | `marketing-edit-offer-scope` | 潤稿 | 行銷 | 指定茶包滿 NT$1,000、`TEA150` 折 NT$150，日期、限次、運費排除保留。 |
| 30 | `marketing-edit-unsupported-claims` | 潤稿 | 行銷 | 只寫 350 mL 及旋蓋，未核准的功效、贈品和引言留待確認。 |
| 31 | `marketing-draft-brand-audience` | 起草 | 行銷 | 用「您」向校園行政新手介紹功能，保留「預約 20 分鐘導覽」與網址。 |
| 32 | `marketing-draft-feature-not-efficacy` | 起草 | 行銷 | 通勤情境只描述三個內袋和拉鍊，保留「查看尺寸」。 |
| 33 | `marketing-draft-unconfirmed-offer` | 起草 | 行銷 | 交代每包 12 枚、適用 X2 和「查看規格」，沒有預告促銷。 |
| 34 | `marketing-draft-approved-testimonial` | 起草 | 行銷 | 引文與「林老師」逐字保留，三個班維持為一次使用經驗。 |
| 35 | `marketing-draft-missing-cta` | 起草 | 行銷 | 保留週末手帳情境與產品規格，購買狀態和管道留在正文外確認。 |
| 36 | `mixed-draft-audience` | 起草 | 報告與客服 | 重跑後分寫收到 18 件、核准 6 件，個案稿只交代已收、待審核。 |

## CLI 實測

完整案例試跑涵蓋兩種入口與五種場景。以下另驗證各 CLI 能否在隔離專案找到技能、依名稱呼叫、讀到場景參考檔，並完成實際模型回覆。

| 工具 | 安裝及呼叫 | 觀察到的結果 |
| --- | --- | --- |
| Claude Code 2.1.332 | `.claude/skills/tw-work-writing/`，以 `/tw-work-writing` 呼叫 Sonnet | 啟動事件列出 skill 與斜線命令。`Read` 從隔離專案讀取 `references/announcements.md`。回覆保留 16:00 更新及 17:00 預計恢復，結果事件為 `error: false`。正文後另列了未提供的管道與重試資訊。 |
| Codex 桌面隨附 CLI 0.171.0-alpha.13.2 | `.agents/skills/tw-work-writing/`，以 `$tw-work-writing` 呼叫 Standard 模型 | 本機提示目錄列出 skill，實際模型回覆保留核准前提和退款區間，事件為 `turn.completed`。讀取 `references/customer-support.md` 的子程序未能啟動，回報 `registered Core launch requires an installed app`。 |
| Codex 官方獨立 CLI 0.172.0 | 用 ZIP 解壓後安裝至 `.agents/skills/tw-work-writing/`，以相同方式呼叫 | `turn.completed`，成稿保留已收件、未核准及核准後預計 3 至 5 個工作天。參考檔讀取遭本機政策拒絕，錯誤為 `blocked by policy`。 |

上述兩次獨立啟動的 Codex CLI 均有安裝辨識及模型回覆的證據，場景參考檔讀取仍未通過。桌面隨附執行檔的錯誤出自註冊式 Core 程序啟動。[Codex Core 啟動原始碼](https://github.com/openai/codex/blob/main/codex-rs/windows-sandbox-rs/src/app_package.rs)

## Codex Desktop Local 實測

2026-11-27 在 Windows 的 Codex Desktop Local 聊天重測通過。先驗證原版 ZIP 的 SHA-256，再從 ZIP 將 8 個檔案暫裝到專案的 `.agents/skills/tw-work-writing/`，逐檔比對安裝內容與解壓來源一致。

| 驗收項目 | 本次觀察到的結果 |
| --- | --- |
| 呼叫 | 在 Local 測試聊天以 `$tw-work-writing` 起草客服退款回覆，聊天回合狀態為 `completed`。 |
| 技能版本 | PowerShell `Get-Content` 讀取 `.agents/skills/tw-work-writing/SKILL.md`，結束碼 `0`，輸出包含 `version: "1.0.0"`。 |
| 場景參考檔 | `Get-Content` 讀取 `.agents/skills/tw-work-writing/references/customer-support.md`，結束碼 `0`，輸出包含「一對一客服回覆」及「寫清楚從哪個事件開始算」。讀檔沿用 Local 聊天的現有政策。 |
| 產生成稿 | 回覆交代已收到申請、目前尚未核准。退款預估為審核通過後 3 到 5 個工作天，退回原付款方式。讀檔驗收說明放在客服正文外。 |

## Codex Desktop Local 雙技能安裝包驗收

2026-11-27 在 Windows 的 Codex Desktop Local 聊天以 `$humanize-tw` 完成兩份文稿。使用當時的本機政策與 `gpt-6.2-sol`（`medium`）。兩支技能從雙技能 ZIP 一起安裝到專案的 `.agents/skills/`，10 個安裝檔逐檔以 SHA-256 比對 ZIP 內容和專案來源，全部相符。

| 驗收項目 | 工具或成稿的實際訊號 |
| --- | --- |
| 手動入口 | `Get-Content` 讀取 `.agents/skills/humanize-tw/SKILL.md`，結束碼 `0`，輸出包含 `name: humanize-tw`。 |
| 相鄰主技能 | `Get-Content` 讀取 `.agents/skills/tw-work-writing/SKILL.md`，結束碼 `0`，輸出包含 `version: "1.0.0"`。 |
| 客服分流 | `Get-Content` 讀取 `.agents/skills/tw-work-writing/references/customer-support.md`，結束碼 `0`，輸出包含「一對一客服回覆」及時程起算點指引。 |
| SOP 分流 | `Get-Content` 讀取 `.agents/skills/tw-work-writing/references/procedures.md`，結束碼 `0`，輸出包含「操作說明與 SOP」及將適用範圍、前置條件放在步驟前的指引。 |
| 根據資料起草客服 | 正文交代已收到退款申請、尚未核准，並寫出「若審核通過，款項預計會在核准後 3 到 5 個工作天內退回您原先使用的付款方式」。沒有額外的審核期限或通知承諾。 |
| 潤飾既有 SOP | 正文保留僅適用桌面版 2.4.1、`Workspace Admin`、完成當日備份及「確認工作佇列為空」。依序開啟 `Batch Jobs`、點選 `Pause New Jobs`，畫面顯示 `Paused` 後才點選 `Export Log`。 |
| 回合完成 | 聊天回合狀態為 `completed`。兩份正文各自成段，實測資訊列在正文外。 |

[雙技能安裝包](../dist/Toolkit_Humanizer_Zh-TW-skills.zip) 檔案本身的 SHA-256 為 `41091a952b4774007806f4644f65a19f21e849920e310a2f924038f2ca400df6`。

## GitHub Release 乾淨專案重裝驗收

2026-11-27 從 [GitHub Release 下載雙技能 ZIP](https://github.com/BlekZz/Toolkit_Humanizer_Zh-TW/releases/download/v1.0.0/Toolkit_Humanizer_Zh-TW-skills.zip)，核對上列 SHA-256。將解壓後的兩個目錄分別裝入兩個空白專案的 `.agents/skills/` 和 `.claude/skills/`。每邊 10 個安裝檔與解壓來源逐檔相符。

| 工具 | 重裝後的實際訊號 |
| --- | --- |
| Codex Desktop Local | 技能清單辨識乾淨專案的 `humanize-tw` 和 `tw-work-writing`。在既有的 Local 驗收聊天以 `$humanize-tw` 呼叫，三次 `Get-Content` 的工具工作目錄都是乾淨專案。入口、相鄰主技能及 `references/customer-support.md` 的結束碼均為 `0`，客服參考檔輸出含「一對一客服回覆」。回合完成，正文保留尚未核准及核准後預計 3 到 5 個工作天退回原付款方式。 |
| Claude Code 2.1.332 | 從乾淨專案啟動，啟動事件列出 `/humanize-tw`。呼叫後，`Read` 實際讀到同一安裝目錄的主技能與 `references/customer-support.md`，後者首行為「一對一客服回覆」。重跑結果 `is_error: false`，正文只寫已收件、尚未核准，以及核准後預計 3 到 5 個工作天退回原付款方式。 |

Windows 的獨立 Codex CLI 能辨識技能並產生回覆，但本次 `Get-Content` 子程序啟動失敗，回報 `setup refresh had errors`。同一批安裝檔在 Desktop Local 讀取成功。Claude Code 的一次試跑在正文加上素材未提供的通知承諾。限定正文只寫目前狀態和退款條件後，重跑符合上述驗收結果，README 範例也補入這個限制。

## 發布檔

- [安裝包](../dist/tw-work-writing-v1.0.0.zip)
- [安裝與使用](../README.md#安裝)

ZIP 解壓後共有 8 個檔案，逐檔 SHA-256 與工作區來源一致。下方是 ZIP 檔案本身的 SHA-256。

```text
295f5c6c71fc8f0c87dcda1c629e99c51fd05bb174c5fac7c1e29ee7ddb7a885
```
