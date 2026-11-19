# Document-Driven Full Cold Start

本次請採用 **Document-Driven Setup（文件驅動設定）**，不要採用逐題訪談模式。

我已在 Claude Desktop → Code 開啟本機資料夾 full-interview/。九份教材文件都在這個資料夾中，且保留 mock-agreements/ 子資料夾。請直接讀取資料夾內的檔案，根據文件內容建立 commercial-legal 所需的 Company Profile 與 Practice Profile。不要把本次工作當成附件上傳流程。

## 1. 操作方式

- 本次採文件驅動設定，不執行逐題 Cold Start Interview。
- 不要逐一詢問公司背景、團隊人數、每月合約數量或 Playbook 立場。
- 不要要求我重新輸入已經存在於本機來源文件中的資料。
- 不要要求我逐份上傳或附加已經位於目前 Code 專案資料夾中的文件。
- 不要要求我重新回答文件已經明確記載的問題。先讀取及整理資料，再列出目標 Profile 的變更計畫。若目標檔案不存在，可建立新檔；若檔案已存在，先比較差異並在覆寫前取得我的明確確認。
- 只有在來源文件存在真正無法判斷的衝突，而且會影響設定正確性時，才提出必要問題。
- 對於刻意沒有設定的欄位，請標記 N/A、Not configured 或 Not applicable，不要自行編造。

## 2. 文件讀取與驗證

請先確認目前 Code 專案資料夾中的九份檔案是否都能實際讀取，並確認五份 PDF 位於 mock-agreements/ 子資料夾：

1. company-profile.docx
2. purchasing-playbook.docx
3. escalation-matrix.docx
4. mock-contract-samples.docx
5. mock-agreements/01-cloud-hosting.pdf
6. mock-agreements/02-system-development.pdf
7. mock-agreements/03-maintenance.pdf
8. mock-agreements/04-software-license.pdf
9. mock-agreements/05-consulting.pdf

DOCX 與 PDF 都必須確認取得實際文字內容。

如果 PDF 無法直接解析，請嘗試可用的文字擷取或 OCR 方式。仍然無法讀取時，明確標記該檔案為無法讀取，不得宣稱已經完成分析。

請不要因為部分契約 PDF 無法讀取，就阻止其他 Profile 的建立。

## 3. 資料來源與角色設定

請以目前本機專案資料夾中的教材作為本次教學設定的權威來源。

### Company Profile

以 company-profile.docx 為主要來源。

- 事務所：丙信法律事務所。
- 法域：臺灣。
- 工作語言：正體中文。
- 本次案件：代表甲子公益協會。
- 甲子是委外系統開發服務的採購方。
- 本案例採 Purchasing-side 立場。
- 事務所為虛構的小型事務所。
- 未設定的人數、姓名及每月案件量，不得自行編造。

### Purchasing-side Playbook

以 purchasing-playbook.docx 為主要來源。

直接採用文件中的：
- 責任限制。
- 損害賠償。
- 個人資料與資訊安全。
- 智慧財產權。
- 期間與終止。
- 準據法與爭議處理。
- The One Thing。

The One Thing 明確為第一項：未經授權將會員、志工或其他個人資料用於 AI 模型訓練。

不要再詢問 Sales-side 或 Purchasing-side。這次案例已確定為 Purchasing-side。

### Escalation Matrix

以 escalation-matrix.docx 為主要來源。

直接採用文件列出的九項升級條件。

特別注意：
- 沒有金額門檻。
- 沒有固定內部簽核層級。
- 沒有具名升級對象。
- 升級代表尋求第二意見或專業協助，不代表自動拒絕交易。

不要自行增加金額門檻或核准人員。

### Contract Samples

以 mock-contract-samples.docx 及五份 PDF 為來源。

這五份契約都是合成教學樣本，不是真正已簽署的契約。

可以比較條款、整理樣本差異，但不得：
- 宣稱這些是實際簽署紀錄。
- 將樣本條款視為已核准的 fallback。
- 從樣本推論真實談判慣例。
- 將樣本條件當成客戶已授權的立場。

## 4. 刻意不包含的設定

本次九份文件不包含 NDA triage positions。

這是課程刻意安排的範圍區隔，NDA 將在後續單元獨立實作。

因此：
- 不要詢問 NDA positions。
- 不要自行建立 NDA 審閱立場。
- 不要把 NDA 設定當成 Full Cold Start 未完成的必要條件。
- 在 Profile 中標示 NDA positions 尚未設定，留待後續單元。

整合服務（Ironclad、DocuSign、Google Drive、Slack）不是本次實作的必要條件。若未實際連接，請記錄狀態；本次直接讀取已開啟的本機資料夾，不要要求我逐項授權或改用 Cowork。

其他沒有提供的 House Style 或行政設定，也請標記 Not configured，不要阻止 Profile 建立。

## 5. 建立 Profile

請參考 commercial-legal Plugin 原本的 Practice Profile 結構，保留必要的章節名稱及欄位，以確保其他 Skill 能正確讀取。

建立或更新：

1. ~/.claude/plugins/config/claude-for-legal/company-profile.md
2. ~/.claude/plugins/config/claude-for-legal/commercial-legal/CLAUDE.md

Profile 內容以正體中文為主，必要的 Plugin 欄位名稱可以保留英文。

所有虛構資料必須保留：

- SIMULATED
- NOT A REAL LAW FIRM
- NOT ATTORNEY-REVIEWED

不得虛構律師核准、客戶授權、真實簽署或真實交易紀錄。

如果目標檔案已存在，先檢查其內容並顯示修改差異。若包含其他真實事務所資料，不要直接覆寫；取得明確確認前不得修改。

## 6. 完成後驗證

取得必要確認並完成寫入後，請：

1. 確認兩份 Profile 是否真的寫入指定路徑。
2. 重新讀取兩份檔案，確認內容可以正常讀取。
3. 確認 Active side 為 purchasing。
4. 確認 The One Thing 為第一項。
5. 確認 Escalation Matrix 沒有自行增加金額門檻。
6. 確認五份契約仍標示為合成教學樣本。
7. 確認 NDA positions 沒有被自行建立。

如果無法寫入本機檔案，請直接提供完整檔案內容及實際遇到的錯誤，不要宣稱已經保存成功。

## 7. 最終回報

請以一份完整的設定摘要結束工作：

- 成功讀取的檔案。
- 無法讀取的檔案及原因。
- Company Profile 建立結果。
- Practice Profile 建立結果。
- 已設定的 Playbook 與 Escalation Matrix。
- 刻意未設定的項目。
- 兩份 Profile 的實際儲存路徑。
- 重新讀取驗證結果。

不要再進行逐題訪談。