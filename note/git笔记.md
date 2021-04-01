# 一、重新认识git

1. git是一个分布式的版本控制工具

```
分布式：在网络互不影响，独立操作      例如：git
集中式：有一个中心服务器来连接这些设备  例如：SVN
```

2. git如何使用

    1. 安装git客户端(windows,mac,...)

     ```
    https://gitforwindows.org/
     ```
    2. git常用命令

        1. 初始化git:git init
        2. 查看当前git文件状态：git status
        3. 添加文件到暂存区：git add 文件名1 
        4. 提交到本地仓库：git commit -m '版本说明'
        5. 添加可忽略文件：.gitignore
        6. 提交到远程仓库

        ```
        （1）git远程仓库（也称代码托管平台）：github,码云，gitLab
        （2）提交远程的步骤：
            第一步：创建一个远程仓库，点击登录后右上角的+，按步骤完成即可
            
              注意：
              
                 远程要定要配置好公钥/密钥
                 ssh-keygen -t ed25519 -C "你的邮箱名@126.com"
                 密钥：id_rsa      公钥：id_rsa.pub
                
                
                测试是否连接成功：ssh -T git@github.com
                
            
            第二步：配置要连接的远程仓库地址
            
             格式：git remote add 远程仓库名称 远程仓库地址
             例如： git remote add origin git@github.com:w3cteching/05Epro.git
             
             
               git@github.com:w3cteching/05Epro.git   【推荐】
               https://github.com/w3cteching/05Epro.git
               
               
            第三步：再推送到远程
                 git push origin 本地分支名：远程分支名
                  例如：git push origin master:main
                  
                   git push origin 本地分支名
                   
                   例如：git push origin master
              如果远程拒绝推送本地文件，则应该先将远程文件拉取本地，然后再推送远程
              
              拉取：
              
                 //从远程拉取到本地，并跟本地分支自动合并 
                 git pull origin 远程分支名:本地分支名  
              
                如果不能git pull，解决方案：
                第一步：只拉取到本地，不合并分支
                 git fetch  origin main:master
                 
                第二步：关联远程main分支到本地master分支
                 git branch --set-upstream-to=origin/main master
                 
                 第三步：然后再使用git pull加拉取
                 git pull --allow-unrelated-histories
                 
                 其中：allow-unrelated-histories代表允许不相关的历史记录
        ```

        

        3. git工作、本地仓库和远程仓库的关系

        ![image-20210331193505579](media/image-20210331193505579.png)

        

        4. 作业：

        1. 将上月技能代码推送到github指定的master远程仓库下

    

​	# 一、历史回退

1. 查看提交历史记录

```
//详细查看
git log
//缩略查看
git log --pretty=oneline

//查看所有的提交commit_id
git reflog --pretty=oneline
```

2. 回退到过去或现在

```
//回退到过去
git reset --hard commit_id
```



# 二、分支管理

1. 分支的作用

```
方便团队之间协作开发，分支之间的代码互不影响
git init 初始化完后，默认本地只有一个分支 master
```

2. 项目分支结构

```
master:主分支，这个分支上不做项目开发，用于发布产品的分支
dev:开发分支
bug:调度bug的分支
feature:开发新功能的功能
成员分支：例如：姓名_功能
```

<img src="media/image-20210401094324827.png" alt="image-20210401094324827" style="zoom:50%;" />

3. 分支常用命令

```
1.查看分支：git branch
例如：
  main
* master  //分支前带*，当前要操作的分支
2.创建分支: git branch 新分支名
3.切换分支: git checkout 要切换的分支名
4.自动创建并分支：git checkout -b 要创建和切换的分支
5.合并分支：git merge 要合并的分支
 
   注意：如果多人修改同一个文件，出现冲突，先解决冲突(采用当前的，采用传入，两者都保留)，再add,commit
6.分支提交到远程
   git push origin 要提交的分支名
7.删除分支

    (1)删除已经合并过的分支
      git branch -d 要删除的分支名  
    
    (2)删除未被合并的分支
      git branch -D 要删除的分支名
    
    (3)删除远程分支： 
      git push origin :要删除的分支名
    

```



# 三、克隆（clone）仓库

```
git clone 远程仓库地址

例如： git clone git@github.com:vuejs/vue.git
```



# 四、团队协作

# 五、git可视化操作

