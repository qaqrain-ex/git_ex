# ==========================================
# Git Branch 常用指令大全
# ==========================================

# 1. 檢視分支 (View Branches)
# ------------------------------------------
# 查看本地所有分支（當前分支前會標示 *）
git branch

# 查看本地與遠端 (Remote) 的所有分支
git branch -a

# 查看各分支最後一次 commit 的訊息
git branch -v


# 2. 建立與切換分支 (Create & Switch)
# ------------------------------------------
# 僅建立新分支（仍留在原本分支）
git branch <分支名稱>

# 建立並直接切換到新分支 (Git 2.23+ 推薦)
git switch -c <分支名稱>

# 建立並直接切換到新分支 (舊版/傳統寫法)
git checkout -b <分支名稱>


# 3. 刪除分支 (Delete Branch)
# ------------------------------------------
# 安全刪除（若有未合併的修改會阻止刪除）
git branch -d <分支名稱>

# 強制刪除（無視未合併變更）
git branch -D <分支名稱>


# 4. 重新命名分支 (Rename Branch)
# ------------------------------------------
# 修改當前所在分支的名稱
git branch -m <新分支名稱>

# 修改指定分支的名稱
git branch -m <舊分支名稱> <新分支名稱>


# ==========================================
# 完整工作流程範例 (Standard Workflow)
# ==========================================

# 步驟 1: 建立並切換到新功能分支
git switch -c feature/login

# 步驟 2: 提交程式碼變更
git add .
git commit -m "Add login functionality"

# 步驟 3: 切換回主分支
git switch main

# 步驟 4: 合併新功能分支
git merge feature/login

# 步驟 5: 刪除已合併的分支
git branch -d feature/login