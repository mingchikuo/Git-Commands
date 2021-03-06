# Git-Commands



## 基礎操作
#### git cat-file "" -t
查看git object之type。

#### git cat-file "" -s
查看git object之大小。

#### git cat-file "" -p
查看git object之內容。

#### git ls-files -s
查看staged檔案。

#### git init
初始化一個空白的本地倉庫。

#### git add --all
一次git add所有檔案。

#### git commit -m "描述"
把staged檔案更新至本地倉庫，並直接加描述。

#### git log
查看log。

#### git reflog
查看歷史操作進程。

#### git status
查看檔案之狀態。



## 分支操作
#### git branch
列出所有分支。

#### git branch ""
創立分支。

#### git branch -D ""
強制刪除分支。

#### git checkout 分支名或commit名
移動到指定分支。

#### git checkout -b 分支名
直接創立與移動到該分支。

#### git branch -vv
查看本地master與遠程master分支點的落差。

#### git push origin master
更新遠程code並同步master。

#### git pull
一步完成git fetch與git merge，但有可能發生conflict。

#### git merge 分支名
Fast Forward，若有其他作者生成新的master則形成3 way merge。
有可能因為修改道同一文件而產生conflict。

#### code . 
用code來解分支衝突。

#### git rebase master
有時不能fast forward，會在分支上重整base，但有可能對其他開發者造成損毀。



## 精簡倉庫
#### tree .git/
#### git gc
#### rm -rf .git/hooks/*.sample


## 遠端操作

### git pull遇到錯誤：error: Your local changes to the following files would be overwritten by merge:解決方法
error: Your local changes to the following files would be overwritten by merge:
意思是我桌上型電腦上新修改的程式碼的檔案，將會被git伺服器上的程式碼覆蓋；我當然不想剛剛寫的程式碼被覆蓋掉，看了git的手冊，發現可以這樣解決：

#### 方法1：如果你想保留剛才本地修改的程式碼，並把git伺服器上的程式碼pull到本地（本地剛才修改的程式碼將會被暫時封存起來）
git stash
git pull origin master
git stash pop
如此一來，伺服器上的程式碼更新到了本地，而且你本地修改的程式碼也沒有被覆蓋，之後使用add，commit，push 命令即可更新原生代碼到伺服器了。

#### 方法2、如果你想完全地覆蓋本地的程式碼，只保留伺服器端程式碼，則直接回退到上一個版本，再進行pull：
git reset --hard
git pull origin master
注：其中origin master表示git的主分支。

#### git remote add origin名 git連結
連結當前到遠端倉庫，並將使用master冠名為origin名。

#### git remote -v
查看目前使用的遠端分支名。

#### github上的倉庫setting中的branches
可修改預設使用分支。

#### git branch -r 
查看遠程分支狀態。

#### git remote show origin
檢查遠程分支跟本地分支相連的情況。。

#### git fetch --prune
同步遠程分支指標並修剪過期分支。

#### git branch -vv
檢查本地與遠端分支相連的情況。

#### git fetch
#### git merge origin/master
下圖情況時可用來跟遠端master merge後同步。
![image](https://i.imgur.com/sm97OqV.png)
也可以用
#### git pull 
一步代替兩步。

#### git fetch
#### git diff origin/master
懷疑有conflict時的嚴謹做法。


