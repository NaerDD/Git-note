### 切换分支
  * 最佳实践：每次切换分支前 当前分支一定得是干净的(已提交状态)
  * 坑：
    在切换分支时，如果当前分支上右未暂存的修改 或者未提交的暂存
    分支可以切换成功 但是这种操作会污染其他分支 将你的操作带到主分支 
  * 改动三个地方:
    * HEAD
    * 暂存区
    * 工作目录
### 后悔药
  * 工作区
    * 如何撤回自己在工作目录中的修改：git checkout --filename

  * 暂存区
    * 如何撤回自己的暂存
       * git ls-files -s 查看当前暂存区
       * $ git cat-file -p 哈希值 （反解哈希值）
       * git reset HEAD 文件名 //将文件add到暂存区后 查看状态自然会提示 如何撤回

  * 版本库
    * 如何撤回自己的提交
      * git commit --amend (注释有误,重新给用户一次机会改注释)
### reset
  * git log :
  * git reflog :主要是HEAD有变化 那么git reflog机会纪录下来

  * 三部曲 (带着分支一起移动)
   * 第一部: git reset --soft HEAD  只动了HEAD
   * 第二部: git reset --mixed HEAD  动了HEAD 动了暂存区
      * git rest --mixed HEAD filename 只动HEAD和暂存区指定文件
   * 第三部: git reset --hard HEAD  全动了
      * 第三部和 git checkout commithash 很相似 
       1. checkout只动HEAD           --hard动HEAD而且带着分支一起走 
       2. checkout对工作目录是安全的  --hard是强制覆盖工作目录 
      * git checkout commithash
      * git checkout --filename
          1.相比于git reset --hard commitHash --file
          2.第一 第二步都没做
          3.只动了工作目录
      * git checkout commithash <file>
        * 将会跳过第一步
        * 更新暂存区
        * 更新工作区
    
      