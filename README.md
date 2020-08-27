# git-e

## 基本操作

`git init`	初始化git仓库

`git add` 	把变更录入索引

`git commit -m "<message>"`	记录索引的状态

`git status`	查看状态

`git diff`	显示差异

`git log`	查看记录

`git show <commit>`	查看提交的详细记录

`git mv <oldfilename> <newfilename>`	修改，移动文件的名称或目录的名称

`git rm <file>`	删除文件

`git clean -n|-f|-x`	删除非管理对象的文件

`git checkout -- <file>`	还原正在手头上修改，还没被添加到索引里的文件

`git reset HEAD -- <file>`	删除已添加到索引的文件 ?? didn't work

`git add -u` 	只添加已经提交过的文件到索引

## 操作分支

`git branch " "|-a`	查看分支

`git branch <branchname>`	创建分支

`git branch -m <oldbranch> <newbranch>`	修改分支名称

`git checkout -b <newbranch>` 创建并切换到新建分支

`git checkout -b <newbranch> <originbranch>` 从origin分支上分出newbranch，并切换

`git checkout <branch>`	切换分支