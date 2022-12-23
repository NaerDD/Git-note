### git分支本质
  1. 分支本质是一个提交对象,所有的分支都会有机会被HEAD所引用(HEAD一个时刻只会指向一个分支)
  2. 当我们有新的提交的时候 HEAD会带着当前持有的分支往前移动
### git分支
  * 创建分支            git branch name
  * 切换分支            git branch checkout name
  * 版本穿梭            git branch name commitHash
  * 创建并切换          git checkout -b name
  * 普通删除              git branch -d name
  * 强制删除              git branch -D name
  * 合并分支              git merge name
    1. 快进合并 不会产生冲突 (一条线上)
    2. 典型合并 有机会产生冲突
    3. 解决冲突 打开冲突的文件 修改 add commit
  * 查看分支列表  git branch
  * 查看合并到当前分支的分支 git branch --merged
      * 一旦出现再这个列表中就应该删除
  * 查看没有合并到当前分支的分支 git branch --no-merged
      * 一旦出现再这个列表中就应该观察一下是否需要合并

### git分支的注意点
  1. 在切换的时候一定要保证当前分支是干净的!!!
    1. 允许切换分支:
      1. 分支上所有的内容都已经提交
      2. (避免)分支上的内容是初始化创建 处于未跟踪状态
      3. (避免)分支上的内容是初始化创建 第一次处于已暂存状态

  2. 不允许切换分支:
      1. 分支上所有的内容处于 已修改状态 或第二次以后的已暂存状态

  3. 在分支上工作做到一半的时候 如果需要切换分支 我们可以暂存起来
      1. git stach:会将当前分支上的工作推到一个栈中
      2. 分支切换 进行其他工作 完成其他工作后 切回原分支
      3. git stash apply 将栈顶的工作内容还原 但不让任何内容出栈
      4. git stash drop  取出栈顶的工作内容后 就应该让其删除(出栈)
      4. git stash pop  = apply+drop
      5. git stash list 查看存储

### 后悔药
  * 工作区 git checkout --filename

  * 暂存区
       * git ls-files -s 查看当前暂存区
       * $ git cat-file -p 哈希值 （反解哈希值）
       * git reset HEAD 文件名 //将文件add到暂存区后 查看状态自然会提示 如何撤回

  * 版本库
      * git commit --amend (注释有误,重新给用户一次机会改注释)


    