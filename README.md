# git-e

## 基本操作

`git init`	初始化git仓库

`git add` 	把变更录入索引

`git commit -m "<message>"`	记录索引的状态

`git status`	查看状态

`git diff`	显示差异

`git log`	查看记录

`git show <commit-sha>`	查看提交的详细记录

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

`git merge <branch>`	合并分支，先checkout到主分支，然后merge新分支内容

`git merge --no-ff <branch>`	非fast-forward型合并提交

`git merge --squash <branch>`	汇合branch上所有提交，并merge到现在分支

`git branch -d <branch>`	删除分支

## 操作标签

`git tag <tagname>`	建立标签

`git tag -a <tagname>`	建立含批注的标签：vim输入

`git tag -am "<批注内容>" <tagname>`	建立含批注的标签：直接输入

`git tag`	查看标签列表

`git tag -n`	查看标签列表，并显示标签的注解

`git tag -d <tagname>`	删除标签tagname

`git push origin <tagname>`	推送标签到远程仓库

`git push origin --tags`	一次性推送所有标签到远程仓库

`git tag -a <tagname> <commitId>`	为特定Id提交打上标签

`git show <tagname>`	查看本地某个标签的信息

## 操作提交记录

`git commit --amend`	修改最近的提交记录

`git commit --amend`	只修改最近的提交记录的注解，没有向索引add更改时

`注：上一条(sha-6e8cb3) 只有一条记录，但是由两次add和三次commit形成`



`git rebase -i <commit>`	修改过去的提交记录

`这里的commit为要修改commit前面一个commit记录, 也可以用HEAD~~,HEAD~2`

-->在显示的提交记录列表中，将要修改提交行首的 ”pick" 改为 “edit” ，保存退出

-->

1. 编辑已经指定"edit"的文件，保存文件，`git add .`
2. 然后`git commit --amend` 执行提交。
3. 最后`git rebase --continue` 完成`git rebase` 操作



`git rebase -i <commit>`	只修改过去提交记录的注解

`这里的commit为要修改commit前面一个commit记录, 也可以用HEAD~~,HEAD~2`

-->在显示的提交记录列表中，将要修改提交行首的 ”pick" 改为 “edit” ，保存退出

-->

1. 直接`git commit --amend` 执行提交。
2. 最后`git rebase --continue` 完成`git rebase` 操作



`git rebase -i <commit>`	合并前面的提交，

`这里的commit为要汇合commit前面一个commit记录, 也可以用HEAD~~,HEAD~2`

-->在显示的提交记录列表中，将要修改提交行首的 ”pick" 改为 “squash” ，保存退出

-->vim 编辑合并后的新的提交message，完成合并。（&will be squashed to one)



`git rebase --abort`	上面的rebase操作要中途退出rebase的命令



`git reflog`	查看HEAD的移动历史

`git reflog <ref>`	查看分支前面的移动历史记录，ref:分支名称



`git revert HEAD`	取消最近一次提交



`git reset --hard HEAD~`	放弃最近一次提交，移动HEAD到倒数第二commit

`git reset --hard <commit>`	放弃最近的提交，移动HEAD到commit

`git reset --hard ORIG_HEAD`	取消最近的reset



`git cherry-pick <commit>`	摘樱桃，把特定commit提交复制到当前分支



`git log --grep <pattern>`	查找包含特定注解的提交	



## 远端操作

`git clone <url>`	复制现有的远程数据库，会自动设定remote，在push/fetch/pull时，省略url

`git remote add <name> <url>`	复制现有的远程数据库

`git remote |-v`	显示远程数据库列表

`git checkout <branch-name-of-remote>`	在远程数据库的分支创建本地数据库的分支

`git push <repository> <refspec-branchname>` 在远程数据库创建分支／反映修改内容到分支

`git fetch <repository> <refspec-branchname>`	查看远程数据库分支的修改内容

`git pull <repository> <refspec-branchname>`	读取远程数据库的分支的修改内容