### 初始化配置
  git config --global user.name = "NaerDD"
  git config --global user.email = 806915230@qq.com
  git config --list

### 区域
  工作区
  暂存区
  版本库

### git操作最基本的流程
* 创建工作目录 对工作目录进行修改
  * git add ./
    * git hash-object -w文件名(修改了多少个工作目录中的文件 此命令就要被执行多少次)
    * git update-index
  * git commit -m "注释内容"
    * git write-tree
    * git commit-tree

### git高层命令(CRUD)
  * 新增
    * git status
    * git add./    
    * git commit -m "msg"
  * 修改
    * git status
    * git add./    
    * git commit -m "msg"
  * 删除，重命名
    * git rm 文件名     git mv 老文件 新文件
    * git status 
    * git commit -m "msg" 
  * 查询
    * git status                                  :查看工作目录中文件的状态(已跟踪(已提交 已暂存 已修改) 未跟踪)
    * git diff                                    :查看未暂存的修改
    * git diff --cache                            :查看未提交的暂存
    * git log --oneline                           :查看提交记录
    * git log --oneline --decorate --graph --all  :查看整个项目的分支历史


  * git log --oneline    查看提交的历史纪录
  * git add./            将修改添加到暂存区
  * git rm 文件名        删除工作目录中对应的文件 再将修改添加到暂存区
  * git mv 原文件 新文件  将工作目录中的文件进行重命名 再将修改添加到暂存区
  * 将暂存区提交到版本库
      * git commit 
      * git commit -m 注释 将暂存区提交到版本库
      * git commit -a -m "message" -a跳过暂存区 提交到版本库

### 分支
   * 分支的本质就是一个提交对象 
   * HEAD:
      是一个指针 它默认指向master分支 切换分支时其实就是让HEAD指向不同的分支
      每次有新的提交HEAD都会带着当前指向的分支一起往前移动
   * git log --oneline --decorate --graph --all               :查看整个项目的分支历史
   * git branch                                               :查看分支列表
   * git branch name                                          :在当前提交对象上创建新分支
   * git branch name commithash                               :在指定的提交对象上创建新分支     
   * git checkout 分支名                                       :切换分支
   * git checkout -b test                                      :创建一个test分支并切换过去
   * git branch -d 分支名                                      :删除分支 删除已经被合并的分支
   * git branch -D 分支名 强制删除分支                          :强制删除分支
  



