### 对象
  * Git对象
    * key:value key是val对应的hash 键值对在git内部是一个blob类型
    * git hash-object -w fileUrl : 生成一个key(hash值):val(压缩后的文件内容)键值对存到.git/objects
  * tree对象
    * git update-index --add --cacheinfo 100644 hash test.txt :往暂存区添加一条记录(让git对象 对象 上文件名)存到.git/index
    * git write-tree : 生成树对象存到.git/objects
  * commit对象
    * echo 'first commit' | git commit-tree treehash:生成一个提交对象
    对以上对象的查询
        * git  car-file -p hash :拿对应对象的内容
        * git  car-file -t hash :拿对应对象的类型
### 查看暂存区
  * git ls-files -s


### 初始化仓库
  * git init
  * hooks 目录包含客户端或服务端的钩子脚本
  * info 包含一个全局性排除文件 起忽略作用
  * logs 日志文件
  * objects 存储所有的数据内容
  * refs 目标存储只想数据（分支）的提交对象的指针
  * config 配置文件
  * description 描述文件
  * HEAD 文件指示目前被检出的分支
  * index 文件保存暂存区信息
  * 
### Git对象
  * $ echo "test content" | git hash-object --stdin （返回转换后的哈希值 不存）
  * $ echo "test content" | git hash-object -w --stdin （存入Objects）
  * $ git cat-file -p 哈希值 （反解哈希值）
  * $ git cat-file -t 哈希值 （返回类型值）
  * git update-index --add（第一次使用） --cacheinfo 100644（普通文件100644 可执行文件100755 符号连接120000） hash值 文件名
  * git ls-files -s 查看当前暂存区
  * git对象代表文件的一次次版本 树对象代表项目的一次次版本
  * 
### linux命令
  * clear 清屏
  * echo 'xxx' 往控制台输出 xxx
  * echo 'xxx' > test.txt 创建一个test.txt文本 里面内容为xxx
  * ll 将当前目录下的子文件和子目录平铺在控制台 ( 只看一层的文件和目录 )
  * find ./  将当前目录下的子孙文件和子孙目录平铺在控制台 (全都看)
  * find ./ -type f  (只看文件 不看目录)
  * rm 文件名 （删除）
  * mv 旧文件名 新文件名 （换名字）
  * cat 文件名 （查看内容）
  * vim 文件名 (修改内容)
    * i键进入插入模式 （进入编辑状态）
    * ESC+:(退出编辑状态) + wq(保存+退出) 
    * q! 强制退出 (不保存)
    * set nu (看行号)

