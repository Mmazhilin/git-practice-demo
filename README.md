1. 設定 Git 環境
首先，確保你已經在命令提示字元中設定了 Git 的使用者名稱和電子郵件地址：
```
git config --global user.name "你的名字"
git config --global user.email "你的電子郵件"
```
2. 創建或進入專案資料夾
打開 CMD，然後切換路徑到你要上傳的專案資料夾。如果需要創建新資料夾，使用以下命令：
```
mkdir my-project
cd my-project
```
3. 初始化 Git 倉庫
在專案資料夾中初始化 Git 倉庫：
```
git init
```
4. 新增檔案
將你要上傳的檔案移動到該資料夾中，然後使用以下命令將檔案新增到 Git：
```
git add .
```
這裡的 . 表示新增所有變更的檔案。

5. 提交更改
提交新增的檔案，並添加描述信息：
```
git commit -m "第一次提交"
```
6. 連接到遠端倉庫
如果你還沒有創建 GitHub 倉庫，可以在 GitHub 網站上創建一個新的倉庫。然後，使用以下命令連接到該倉庫：
```
git remote add origin https://github.com/你的帳號/你的倉庫.git
```
7. 上傳到 GitHub
最後，使用以下命令將更改推送到 GitHub：
```
git push -u origin master
```
如果你的主要分支是 main，請使用：
```
git push -u origin main
```
注意
如果這是你第一次推送到這個遠端倉庫，可能會要求你輸入 GitHub 的使用者名稱和密碼。
確保在上傳之前，所有檔案都已經正確新增和提交。

### 補充
1. 查看當前分支
查看當前所在的分支：

```
git branch
```
這會列出所有的分支，並且在當前分支前會有一個星號 (*)。

2. 切換到已有的分支
切換到已經存在的分支，可以使用以下命令：

```
git checkout branch-name
```
將 branch-name 替換成你想切換的分支名稱。

3. 創建並切換到新分支
如果你想創建一個新的分支並立即切換到該分支，可以使用以下命令：
```
git checkout -b new-branch-name
```
將 new-branch-name 替換成你想要的分支名稱。

4. 確認切換
再次使用 git branch 命令確認你已經成功切換到目標分支。

注意事項
如果當前分支有未提交的更改，Git 會阻止你切換到其他分支，除非這些更改被提交或儲存（使用 git stash）。
確保在切換分支之前，已經將當前的變更提交，以避免潛在的衝突。

### 完全退回到某个提交:
1.查看提交歷史
```
git log
```

> commit 43603dc9e52b168d8df8e574729af58e4f28dfc0 (master)
> Author: Mmazhili <jg1211jg@gmail.com>
> Date:   Wed Oct 9 19:08:19 2024 +0800

> 新增 test.txt

> commit acb4cecf8090ab65549e7708ff757e9d4095bca6
> Author: Mmazhilin <45139687+Mmazhilin@users.noreply.github.com>
> Date:   Wed Oct 9 19:01:51 2024 +0800

> Update README.md

> commit 095beb2cc7845508536effaee62118c2430bf08c
> Author: Mmazhilin <45139687+Mmazhilin@users.noreply.github.com>
> Date:   Wed Oct 9 18:57:23 2024 +0800

> Create README.md

> commit 7093a2514c54dfc3b4bd66ed1904d40506396bb6
> Author: Mmazhilin <45139687+Mmazhilin@users.noreply.github.com>
> Date:   Wed Oct 9 18:28:08 2024 +0800

> Initial commit


2.使用 git reset 撤销提交
保留更改在暫存區
```
git reset --soft <commit-hash>
```
保留更改在工作目錄，但不在暫存區
```
git reset --mixed <commit-hash>
```
删除所有更改
```
git reset --hard <commit-hash>
```
注意：使用 --hard 會永久刪除所有未提交的更改，請警慎使用。
`commit-hash 提交號碼`
3.上傳更改到遠程倉庫
```
git push origin <branch-name> --force
```
`branch-name 分支`
