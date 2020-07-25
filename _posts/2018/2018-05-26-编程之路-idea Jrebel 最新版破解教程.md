---
layout:     post             				# 使用的布局（不需要改）
title:      idea Jrebel 最新版破解教程   # 标题 
subtitle:   ✍🏽 					  				#副标题
date:       2018-05-26  					# 时间
author:     Ian                  			# 作者
header-img: img/img/home-bg-o.jpg	#这篇文章标题背景图片
catalog: true                        	# 是否归档
tags:                              		#标签
    - 编程之路
    - jrebel
---

### 引言
我之前也是用<https://my.jrebel.com/login> 激活的，最近不知道咋搞的，一直激活不了，还专门注册了几个账号。。。。坑。

安装jrebel 直接IDEA在线安装，去下面链接下载自己需要的反向代理工具 [大神写的反向代理工具](https://github.com/ilanyu/ReverseProxy/releases/tag/v1.0) 

### mac版：

1. 下载ReverseProxy_darwin_amd64
2. 双击运行ReverseProxy_darwin_amd64
3. 打开idea，在License server http://127.0.0.1:8888
4. 正常来说就验证通过，8888是默认的端口号，如果有被占用冲突，可能就需要修改成其他端口

#### Mac可能会遇到的问题
用Safari下载下来就是.dms，用Chrome下载下来的确没有后缀了，但是被系统识别成了文稿，如何解决。

##### 在终端执行以下命令：

1. chmod 777 ReverseProxy_darwin_amd64文件位置，例如：chmod 777 /Users/abcde/Downloads/ReverseProxy_darwin_amd64

2. `$bash ReverseProxy_darwin_amd64`文件位置，例如：`$bash /Users/abcde/Downloads/ReverseProxy_darwin_amd64`

3. 打开idea，在License server http://127.0.0.1:8888

### win版（64位）
1. 下载`ReverseProxy_windows_amd64`
2. 双击运行`ReverseProxy_windows_amd64`
3. 打开idea，在`License server http://127.0.0.1:8888`
4. 正常来说就验证通过，8888是默认的端口号，如果有被占用冲突，可能就需要修改成其他端口

### 直接nginx反代

下面代码粘贴在nginx\conf\nginx.conf下

```
server {
listen 8888;
location / {
proxy_pass http://idea.lanyus.com:80;
}

proxy_set_header Host "idea.lanyus.com";
}
```
然后使用http://127.0.0.1:8888 即可


### JRebel 2018.1使用反代失败解决

授权地址增加了GUID检测

使用 http://xxx.com:8888/jrebelusername 这样的地址无法激活了
需要修改为 http://xxx.com:8888/88414687-3b91-4286-89ba-2dc813b107ce 这样的地址

如：http://192.168.123.12:8888/88414687-3b91-4286-89ba-2dc813b107ce

后面的那串为GUID，随便找个GUID在线生成器生成个就行了

从老版本升级到该版本的不受影响，激活后一定手动要切换到离线模式，可离线180天，可随时重点下，180天周期会重新刷新

#### 离线模式
离线模式在 settings--> Jrebel 左边会有一个work offline 按钮， 将最右边的offline seat duration值改为180，然后点击work offline 即可， 切换离线模式时不要关闭激活服务

这篇写的比较详细可以参考：<https://blog.csdn.net/qq_27093465/article/details/79148498>






