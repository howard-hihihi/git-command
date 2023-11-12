git config --global  user.name "使用者名稱"
git config --global  user.email "使用者電子郵件"
git init
git add . / git add <檔名.副檔名>
git commit -m"加入文字註記修改甚麼"
git status
git log
git remote add <自訂的名稱> <網址>\n
git push -u <自訂的名稱> master   ---->  '-u'會將預設值設成<自訂的名稱>
git push 有設定預設值就可以只打 'git push'
git clone <網址>  -----> 將遠端儲存庫複製到本地端
----------------------------------------------------------------------------------------------------------------

git reset -- “檔名” : 將指定的檔案從暫存區中取消暫存（unstage）
git checkout : 等同於 discard changes (捨棄變更)
git reset --soft HEAD~1 : 會到前一個commit，用 git log 會發現前一次的 commit 會消失，這邊的數字代表要往幾個commit。
                          這個模式下的 reset，工作目錄跟暫存區的檔案都不會被丟掉，所以看起來就只有 HEAD 的移動而已。
                          也因此，Commit 拆出來的檔案會直接放在暫存區。
git reset --hard HEAD~1 : 
----------------------------------------------------------------------------------------------------------------

## conflicts
假設有A、B兩個同一個檔案修改了，A先 ‘push’ 了，但是B不知道A ‘push’ 上去了，所以當B要 ‘push’ 上去時會發生 conflicts。
所以B要先將A ‘push’ 上去的版本 ‘pull’ 下來進行 merge。
這樣B才可以 ‘push’ 上去。
----------------------------------------------------------------------------------------------------------------

git branch <分支名稱>
git branch -a : 可以查看所有分支，包括遠端的
git checkout <要查看的分支名稱>
git checkout -b <分支名稱>:  Git 存儲庫中建立並切換到一個新的分支，該分支名稱為 "feature-a"。
    1. 如果 "feature-a" 分支已經存在，則切換到該分支。
    2. 如果 "feature-a" 分支不存在，則創建一個新的分支並切換到該分支。
    3. 你現在位於新創建的 "feature-a" 分支，並且可以在該分支上進行代碼更改、提交等操作。

# delete branch have two ways
1. if we had not merge branch to master  ------>  git checkout master  ------>  git branch -D <分支名稱>
2. if we had merge branch to >  ------>  

----------------------------------------------------------------------------------------------------------------

git lfs install
git lfs track "path/to/large/file.ext" -----> 使用以下命令，將您想要存儲在 LFS 中的大文件添加到 .gitattributes 文件中
git add .gitattributes
git commit -m "Add .gitattributes for LFS"
