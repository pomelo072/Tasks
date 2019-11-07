# GIT学习

- 创建版本库
- 版本控制
- 远程仓库
- 分支管理
- 标签管理
- 使用GitHub
- 自定义Git

---

## 创建版本库

  		1. `cd`命令可以跳转目录，`mkdir`命令用于创建目录，`pwd`命令可以查看当前文件夹。
    		2. 使用命令`git init`把此目录变成可以使用Git管理的仓库。
      		3. 把文件放入仓库：
       1. 把文件放入目录中。
       2. 使用命令`git add <file>`告诉Git，添加文件到仓库。
       3. 使用命令`git commit`，把文件提交给仓库。（使用`git commit -m "xxx"`可以添加说明）

---

## 版本控制

1. 使用命令`git status`查看仓库状态。
2. 使用命令`git diff`查看变动内容。
3. 使用命令`git log`查看历史记录。（可以添加`--pretty=oneline`命令精简显示）
4. 如果文件改动后，需要再次用命令`git add` `git commit`再次提交。

> ### 版本回退
>
> 1. 使用命令`git reset --hard commit_id`进行版本回退。
> 2. 使用命令`git reflog`查看命令记录。（以便反悔）

> ### 撤销修改
>
> 1. 如果想丢弃工作区的修改，使用命令`git checkout -- <file>`。
> 2. 丢弃已经添加到暂存区的东西，使用命令`git reset HEAD <file>`。

> ### 删除文件
>
> 1. 使用命令`rm <file>` ，删除文件管理器中的文件。
> 2. 使用命令` git rm <file>`，删除版本库中的文件并再次`git commit`。
> 3. 如果删错了，可以用撤销操作（1）的操作恢复。（前提是没有删除版本库中的文件）

---

## 远程仓库

1. 创建SSH key，输入命令`ssh-keygen -t rsa -C "email"`，在主目录中的`.ssh`会生成两个文件，`id_rsa`和`id_rsa.pub`。

> ### 添加远程库
>
> 1. 关联远程库，使用命令`git remote add origin git@github.com:path/repo-name.git`。
> 2. 第一次推送，使用命令`git push -u origin master`。
> 3. 后续推送使用命令`git push origin master`。

> ### 从远程库克隆
>
> 1. 使用命令`git clone git@github.com:path/repo-name.git`。

---

## 分支管理

> ### 创建与合并分支
>
> - 查看分支：`git branch`
> - 创建分支：`git branch <name>`
> - 切换分支：`git checkout <name>`或`git switch <name>`
> - 创建并切换分支：`git checkout -b <name>`或`git switch -c <name>`
> - 合并分支到当前分支：`git merge <name>`（如果加上`--no-ff`参数使用普通合并模式，留有历史）
> - 删除分支：`git branch -d <name>`
> - 丢弃一个没有被合并的分支：`git branch -D <name>`

> ### 解决冲突
>
> - 如果分支合并失败，需要手动修改至合适的内容，再次提交
> - 可以使用命令`git log --graph`查看分支合并图。

> ### bug分支
>
> 当手头工作未完成时，使用命令`git stash`复制工作现场，恢复使用工作现场使用命令`git stash pop`。复制到另一个分支使用命令`git cherry-pick <commit>`。

> ### 分支操作
>
> - 查看远程库：`git remote`（详细信息加参数`-v`）
> - 推送分支：`git branch origin <branch-name>`（如果推送失败，使用`git pull`抓取远程的新提交）
> - 在本地创建和远程分支对应的分支：`git checkout -b branch-name origin/branch-name`
> - 建立本地分支和远程分支的关联：`git branch --set-upstream branch-name origin/branch-name`
> - 把本地未push的分支历史合并成直线：`git rebase`

---

## 标签管理

> ### 创建标签
>
> - 创建标签：`git tag <tagname> [commit_id]`
> - 指定标签信息：`git tag -a <tagname> -m "message"`
> - 查看命令：`git tag`

> ### 操作标签
>
> - 推送一个本地标签：`git push origin <tagname>`
> - 推送所有未推送过的本地标签：`git push origin --tags`
> - 删除一个本地标签：`git tag -d <tagname>`
> - 删除一个远程标签：`git push origin:refs/tags/<tagname>`

---

李子夏

2019年11月6日  18:45



