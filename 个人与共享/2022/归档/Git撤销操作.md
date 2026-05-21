# Git撤销操作

\#git#

## git reset

场景一: 从暂存中移除

- 创建了一个文件 touch a.md

- git add a.md 加入暂存

- 从暂存移除 git reset

- 使用git rm –cached a.md也可以达到同样的效果

场景二: 取消提交

- touch a.md

- git commit -a -m ”commit”

- git reset –soft HEAD~1 从提交状态退回到暂存区, 文件本身不变(commit记录也不存在了)

- git reset –mixed HEAD~1 从提交状态退回到未跟踪状态, 也就是提交==>暂存==>未提交(commit记录也不存在了)

- git reset –hard HEAD~1 从提交提交状态退回到未跟踪状态, 然后将文件删除(commit记录也不存在了)

## git revert

git revert可以回退到某次commit的代码,但是会增加一份新的commit记录, git revert还会保留以前的commit历史记录, git revert更安全

## git checkout

可以切换到某次commit, 但是切换之后只可以看, 不可以写