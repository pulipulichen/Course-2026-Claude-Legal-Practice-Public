請執行 Document-Driven NDA Triage Positions Update。

本次工作是根據附件 nda-triage-positions.docx 更新 Practice Profile，不是重新進行 Cold Start Interview。

### 1. 讀取資料

請完整讀取 nda-triage-positions.docx。

同時讀取目前的：

~/.claude/plugins/config/claude-for-legal/commercial-legal/CLAUDE.md

確認目前 Practice Profile 結構及 Purchasing-side playbook 設定。

### 2. 直接整理，不要訪談

- 不要啟動 Cold Start Interview。
- 不要執行 --full 或 --redo。
- 不要逐項詢問文件已經回答的問題。
- 不要要求我重新描述審閱立場。
- 不要自行增加 DOCX 沒有記載的客戶要求。
- 資料不足的地方標示 Not specified 或待律師確認，不要自行編造。

### 3. 更新 Practice Profile

將 NDA 審閱準則寫入：

## Playbook
→ ### Purchasing-side playbook
→ #### NDA triage positions

整理並保留文件中的：
- 保密資訊範圍及例外。
- 使用目的與接觸人員。
- 保密期間。
- 資料返還、刪除及備份。
- 其他 NDA 義務。
- GREEN／YELLOW／RED 分流規則。

文件中針對本課程 nda.pdf 的八條預期顏色，另外標示為本次教學案例的比對參考，不要將條款編號及顏色當成所有 NDA 通用的審閱規則。

### 4. 保留核定狀態

必須保留：

SIMULATED — NOT ATTORNEY-REVIEWED

- 不得設定 attorney-reviewed = true。
- 不得虛構律師姓名或核准日期。
- 不得宣稱本文件已經正式律師核准。

### 5. 保護既有設定

- 不要覆寫 Company Profile。
- 不要修改既有 Purchasing-side 其他審閱立場。
- 不要修改 Sales-side playbook。
- 不要修改 Escalation Matrix。
- 只新增或更新 NDA triage positions 專屬內容。
- 若其他位置仍有「NDA positions 尚未設定」等舊註記，請先列出位置及內容，不要擅自改動不相關設定。

### 6. 驗證及完成

完成後：
1. 儲存 Practice Profile。
2. 重新讀取實際儲存的檔案。
3. 確認 NDA triage positions 已經存在。
4. 確認既有設定沒有遺失。
5. 確認 SIMULATED — NOT ATTORNEY-REVIEWED 狀態仍然保留。
6. 顯示本次新增內容摘要及修改差異。

完成 Profile 更新後，先不要重新執行 NDA Review，等我確認後再開始第二輪審查。