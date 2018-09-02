## Git 技能学习

#### Git 安装

`sudo apt-get install git` 在Linux上安装Git

`git config -l` 或者 `git config --list` 列出所有配置

`git config --global <option>` 配置全局选项

 - `git config --global user.name "YourName"`
 - `git config --global user.email "YourE-Mail"`


#### 创建版本库

`git init` 初始化一个Git仓库

`git add <file>` 暂存文件

 - `git add README.md` 或者 `git add .` 

`git commit` 提交暂存文件到本地仓库

 - `git commit -m "add README.md file"`

#### 版本穿梭

`git status` 查看工作区状态

`git diff` 查看修改内容

 - `git diff README.md`
 
`git log` 显示提交日志

`git log --pretty=oneline` 一行显示提交日志

`HEAD` 表示当前版本， `HEAD^` 上一个版本， `HEAD^^` 上上一个版本， `HEAD~100` 往上100个版本

`git reset --hard HEAD^` 回退到上一个版本

`git reset --hard 5ec5b8e` 指定回到某个版本

`git reflog` 查看命令历史

#### 版本修改

`git diff HEAD -- README.md` 查看工作区和版本库最新版本的区别

`git checkout -- <file>` 丢弃工作区的修改

 - `git checkout -- README.md`

`git reset HEAD <file>` 撤销暂存区修改

 - `git reset HEAD README.md`

`git rm <file>` 从版本库删除文件

#### 远程仓库

`ssh-keygen -t rsa -C "YourE-Mail"` 创建SSH Key

`git remote add origin git@github.com:username/project.git` 添加远程库

`git push -u origin master` 推送本地分支内容到远程库并且关联远程分支

`git push origin master` 推送master分支到远程库

`git clone git@github.com:username/project.git` 用git协议克隆一个远程库

`git clone https://github.com/username/project.git` 用https协议克隆一个远程库

`git remote` 查看远程库信息

`git remote -v` 查看远程库详细信息

`git pull` 拉取远程库的新提交

`git checkout -b <branch_name> origin/<branch_name>` 创建远程分支到本地

 - `git checkout -b test origin/test`

`git branch --set-upstream <branch_name> origin/<branch_name>` 本地分支关联远程分支

 - `git branch --set-upstream test origin/test`

`git remote remove origin` 或者 `git remote rm origin` 移除关联的远程库

#### 分支管理

`git branch` 查看分支

`git branch <name>` 创建分支

 - `git branch edit_zh`

`git checkout <branch_name>` 切换分支

 - `git checkout edit_zh`

`git checkout -b <branch_name>` 创建并切换分支

 - `git checkout -b test`

`git checkout -b dev origin/dev` 创建远程分支到本地

`git merge <branch_name>` 合并某分支到当前分支

 - `git merge test`

`git merge --no-ff -m "merge with no-ff" test` 禁用Fast forward模式合并分支

`git log --graph` 查看分支合并图

`git log --graph --pretty=oneline --abbrev-commit` 查看分支合并情况

`git branch -d <name>` 删除分支

 - `git branch -d test`

`git branch -D test` 强制删除未合并的分支

`git stash` 储藏未提交的工作

`git stash list` 查看储藏列表

`git stash apply` 恢复储藏的内容

`git stash drop` 删除储藏

`git stash pop` 恢复储藏的内容并删除储藏

#### 标签管理

`git tag <name>` 在当前打一个标签

 - `git tag v1.0`

`git tag` 查看所有标签

`git tag v0.9 4a34a5e` 在指定提交上打标签

`git show <tagname>` 查看标签信息

 - `git show v1.0`

`git tag -a v2.0 -m "version 2.0 released" 4a34a5e` 创建带有说明的标签

`git push origin v1.0` 推送标签到远程

`git push origin --tags` 推送全部标签到远程

`git tag -d v1.0` 删除标签

`git push origin :refs/tags/v1.0` 删除远程标签

#### 自定义Git

`.gitignore` 忽略特殊文件

`git add -f file` 强制添加被忽略的文件

`git check-ignore` 检查忽略规则

 - `git check-ignore -v file`

```
git config --global alias.lg 

"log --color --graph --pretty=format:

'%Cred%h%Creset -%C(yellow)%d%Creset 

%s %Cgreen(%cr) %C(bold blue)<%an>%Creset' 

--abbrev-commit"
```

配置别名
