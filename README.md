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
