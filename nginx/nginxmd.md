

nginx



是啥？nginx



是啥：？http和反向代理服务器

优势：使用内存少， 并发能力强









1、反向代理

正向代理

用户知道目标服务器地址，但由于网络限制等原因，无法直接访问。这时候需要先连接代理服务器，然后再由代理服务器访问目标服务器。

反向代理

反向代理对用户则是不可知的，比如我们访问百度网站，百度的代理服务器对外的域名为 [https://www.baidu.com](https://link.zhihu.com/?target=https%3A//www.baidu.com) 。具体内部的服务器节点我们不知道，现实中我们通过访问百度的代理服务器后，代理服务器给我们转发请求到他们N多的服务器节点中的一个给我们进行搜索后将结果返回。



负载均衡

动静分离





####  安装

因为Nginx依赖于gcc的编译环境，所以，需要安装编译环境来使Nginx能够编译起来。

> yum install gcc-c++



2.Nginx的http模块需要使用pcre来解析正则表达式，需要安装pcre。

> yum install -y pcre pcre-devel



3.安装依赖的解压包。

> yum install -y zlib zlib-devel



4ssl 功能需要 openssl 库，安装 openssl。



> yum install -y openssl openssl-devel





然后Nginx官网下载

http://nginx.org/en/download.html

【说明】

Mainline version：Mainline 是 Nginx 目前主力在做的版本，可以说是开发版

Stable version：最新稳定版，生产环境上建议使用的版本

Legacy versions：遗留的老版本的稳定版我们选择Stable version，点击下载。



下载完毕后解压：

使用命令：

> tar -zxvf nginx-1.16.1.tar.gz 

在进入 /usr/local/nginx目录执行

> ./configure
>
> make
>
> make install



这样还是无法访问到linux中的nginx服务

需要以下配置

查看防火墙配置

>  firewall-cmd --list-all

给防火墙添加规则

> sudo firewall-cmd --add-port=80/tcp --permanent

重启防火墙

> firewall-cmd --reload







常用命令：



查看版本号： ./nginx -v

查看nginx是否启动： ps -ef | gerp nginx

启动nginx： ./nginx

关闭nginx： ./nginx  -s stop

重加载nginx：./nginx -s reload





nginx的配置文件

 

分为三部分



全局块

![image-20220116101840983](C:\Users\hp\AppData\Roaming\Typora\typora-user-images\image-20220116101840983.png)



events块



![image-20220116101956213](C:\Users\hp\AppData\Roaming\Typora\typora-user-images\image-20220116101956213.png)







http块

它包裹http全局块和server块









![image-20220116092443637](C:\Users\hp\AppData\Roaming\Typora\typora-user-images\image-20220116092443637.png)



反向代理

实例1 

请求80的时候， 跳转到tomcat的8080端口中

如何实现以下需求：

![image-20220116103707690](C:\Users\hp\AppData\Roaming\Typora\typora-user-images\image-20220116103707690.png)

完成以下配置即可

![image-20220116162636970](C:\Users\hp\AppData\Roaming\Typora\typora-user-images\image-20220116162636970.png)



实例2

请求



![image-20220116164652743](C:\Users\hp\AppData\Roaming\Typora\typora-user-images\image-20220116164652743.png)





7 nginx原理







