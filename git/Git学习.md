什么是git



版本管理工具vcs



2、用来做什么？

分布式控制

多个开发人员协调工作

有效监听谁做的修改

本地与远程操作



3、一些git基础命令

![image-20220115181453277](C:\Users\hp\AppData\Roaming\Typora\typora-user-images\image-20220115181453277.png)



开始：

去官网下载， git官网：https://git-scm.com/

然后打开下载好的文件， 根据提示完成安装即可。



测试是否安装成功

打开命令行， 输入git --version 

![image-20220115181819415](C:\Users\hp\AppData\Roaming\Typora\typora-user-images\image-20220115181819415.png)

显示版本号， 即安装成功



输入 git init 初始化git仓库

![image-20220115182016644](C:\Users\hp\AppData\Roaming\Typora\typora-user-images\image-20220115182016644.png)

发现目录中多了一个.git的文件

![image-20220115182725060](C:\Users\hp\AppData\Roaming\Typora\typora-user-images\image-20220115182725060.png)





进行一些基础的配置

```shell
git config --global user.name 'xiaozhang'
git config --global user.email '862449030@qq.com'
```

![image-20220115182633136](C:\Users\hp\AppData\Roaming\Typora\typora-user-images\image-20220115182633136.png)



git status 查看状态

![image-20220115182947883](C:\Users\hp\AppData\Roaming\Typora\typora-user-images\image-20220115182947883.png)

红色表示未提交

git add index.html

git add *.html 将所有的html文件添加到git仓库

git add .    添加所有文件

![image-20220115183039854](C:\Users\hp\AppData\Roaming\Typora\typora-user-images\image-20220115183039854.png)

绿色表示已经添加文件到git仓库



每当修改已经提交到git仓库中的文件时， 需要重新提交，

此时我们修改了已经提交的文件， 再次使用git status查看状态时， 会显示这个文件 “ modified ”

![image-20220115183531787](C:\Users\hp\AppData\Roaming\Typora\typora-user-images\image-20220115183531787.png)



这个时候我们需要重新添加

使用命令 git add . 

使用git status 查看状态后， 文件都已经被添加， 这时我们使用命令

git commit -m'备注'



![image-20220115184244962](C:\Users\hp\AppData\Roaming\Typora\typora-user-images\image-20220115184244962.png)









如何忽略， 不想上传的文件




创建俩文件

![image-20220115190257122](C:\Users\hp\AppData\Roaming\Typora\typora-user-images\image-20220115190257122.png)



创建一个.gitignore文件， 在里面写入你不上传的文件

![image-20220115190220692](C:\Users\hp\AppData\Roaming\Typora\typora-user-images\image-20220115190220692.png)

这时我们再次使用gitstatus查看状态， 只有一个.gitinore的文件未提交， 并没有我们写入到.gitinore

![image-20220115190433756](C:\Users\hp\AppData\Roaming\Typora\typora-user-images\image-20220115190433756.png)





忽略文件夹 ： 在文件中写入 /文件夹名称







分支如何使用



创建分支

切换分支：git checkout 分支名称

![image-20220115193957535](C:\Users\hp\AppData\Roaming\Typora\typora-user-images\image-20220115193957535.png)



切换到主线： git checkout master



在分支中进行的操作不会影响主线中的内容



主线以及分支的合并







4、 如何操作远程仓库



官网： https://github.com/

![image-20220116090149472](C:\Users\hp\AppData\Roaming\Typora\typora-user-images\image-20220116090149472.png)





查看是否连接， 命令： git remote

![image-20220116090013607](C:\Users\hp\AppData\Roaming\Typora\typora-user-images\image-20220116090013607.png)





push到主线

git push -u origin master



















