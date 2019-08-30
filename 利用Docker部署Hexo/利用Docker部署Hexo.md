# 使用Docker在CentOS云服务器中搭建Hexo博客

​	因为之前的域名`raool.top`过期了，于是这几天在公司闲暇的时候，重新买了个看着还不错的域名`panjunwen.xyz`，别看现在xyz域名跟白菜价一样，以后续费可比top域名贵多了。所以既然现在有了这个域名，那就买台服务器搭个博客，写点东西玩耍一下吧。

## 购买域名和服务器

​	在[阿里云](https://cn.aliyun.com)购买服务器，有学生优惠。进入官网之后拉到最底下选择「学生机」可以进入到购买[学生服务器](https://promotion.aliyun.com/ntms/act/campus2018.html)的页面，只要是24岁以下只要实名认证了的就是学生身份。

​	**一年114**（2019.8.8）的费用，乞丐配置，搭个博客足够用了。

​	域名的话在[万网](https://wanwang.aliyun.com)选择一个自己看着顺眼的就可以。个人比较推荐xyz域名，目前已经有很多大企业已经在使用xyz域名部署服务了。

​	购买完成后对域名进行**解析**，解析到服务器的ip地址。

​	最后记得给服务器进行**备案**。

##使用Docker

### 安装Docker

​	购买服务器完成后可以使用ssh远程登录控制你的服务器，这方面可以使用`Terminus（Mac）`，一个界面优美简洁的客户端，可以记录下服务器的登录名和密码，下次登录就不用这么麻烦啦。

​	**安装的话按照教程[CentOS安装Docker](https://www.runoob.com/docker/centos-docker-install.html)安装就可以了。**

### 编写Dockerfile

​	安装完成后确保Docker可以正常运行。

- 新建一个Dockerfile文件：

``` dockerfile
FROM node
WORKDIR /blog.panjunwen.xyz(你自己的域名)
RUN npm i -g hexo-cli
CMD ["hexo","-p","80","server"]
EXPOSE 80
```

​	这里的意思是在node环境下安装hexo命令行，然后容器启动的时候直接启动hexo服务器并让它监听80端口。

- 把Dockerfile文件上传到服务器中（或者直接的服务器用Vim编写dockerfile），可以使用ftp方式上传，如使用`ForkLift(Mac)`。
- 在Dockerfile同级目录下运行命令：

``` bash
docker build -t blog .
```

​	把Dockerfile构建成镜像，并起名blog。

​	

## 运行容器

​	镜像有了，接下来直接启动容器就可以啦。

​	

## 配置Nginx和SSH

## 使用Docker-Compose

#### 安装Docker-Compose





