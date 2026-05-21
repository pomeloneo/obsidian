# git

\#interview # git revert HEAD # → 撤销指定的commit（👍）

# 👉 git revert和git rebase —onto的区别：

git revert会增加一条新的commit，它的内容与指定commit的修改是相反的，两次相互抵消从而达到撤销的效果，并且在commit历史中，会存在两条提交，一条原始commit，一条它的反转commit，而git rebase —onto是直接将commit从历史记录中直接删除

# $git rebase -i 目标commit # → 修改历史某一次提交

# git reset —hard HEAD # → 回滚到指定版本，同时清空工作目录的所有改动

# git merge —abort # → 终止本次merge，并回到merge前的状态（👍）