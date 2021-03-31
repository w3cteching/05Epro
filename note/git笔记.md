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
              
              拉取：git pull origin 远程分支名:本地分支名
        ```

         

    3. xxx

    

​	