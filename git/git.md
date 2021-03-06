# 目录
[TOC]
# 代码提交操作步骤（严格遵循）：
```
git pull
git status //查看清楚有没有不需要提交的文件，或者是无意间修改的文件
git add .
git commit -m 'message'
git pull
git push

git pull = git fetch + git merge
```
# 分支问题

```javascript
git checkout -b dev // 新建分支
git push origin dev:dev // 提交本地分支到远程
```
```
1.删除本地分支 git branch -D br
2. 删除远程分支 git push origin :eml-dev

git push origin [name] // 创建远程分支(本地分支push到远程)
git push origin :test   // 刚提交到远程的test将被删除，但是本地还会保存的，不用担心
```

# 出现的问题
遇到merge,使用vi命令
i 切换到insert模式(编辑模式)
esc 从编辑模式切换到命令模式
:wq  保存并退出
enter

撤销git add操作
git reset HEAD <file>

撤销commit操作
git reset commit_id

修改commit信息
git commit --amend

# 删除分支

# fork代码并提pr
```
1. fork 代码到本地
2. 本地修改完成后new pr
```
# fork代码同步源项目
1. git remote add upstream https://github.com/zhaobulang/demo2.git（源项目）
2. git fetch upstream(更新代码)
3. git merge --no-ff remotes/upstream/master（本地项目合并远程代码）

# 回退版本
```javascript
  git reset --hard HEAD^ // 前一版
  git reset --hard HEAD^^ // 前两版
  git reset --hard HEAD~100 // 前100版
  
  // 回到最新版本
  git reset --hard 1094a
  git reflog // 记录每一次命令
```