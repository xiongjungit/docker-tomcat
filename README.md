docker-tomcat
===================

![](https://dn-daoweb-resource.qbox.me/image-icon/tomcat.svg)


基础的运行tomcat应用程序服务器docker镜像


镜像标签
----------
```
    dockerxman/tomcat:latest
    dockerxman/tomcat:8.0
    dockerxman/tomcat:7.0
    dockerxman/tomcat:6.0
    dockerxman/tomcat:5.5
    dockerxman/tomcat:4.1
```


使用
-----

在docker-tomcat文件夹执行以下命令创建镜像 `dockerxman/tomcat`:

    docker build -t docker/tomcat .

运行镜像并绑定端口 :

    docker run -d -p 8080:8080 dockerxman/tomcat


第一次你运行你的容器,将在tomcat中创建一个随机密码的特权新用户`admin`。查看容器的运行日志获取密码:

    docker logs <CONTAINER_ID>

您将看到一个如下输出:

    ========================================================================
    You can now connect to this Tomcat server using:

        admin:b1uKcRK3r6SF

    Please remember to change the above password as soon as possible!
    ========================================================================

在这种情况下,`b1uKcRK3r6SF`是分配给“admin”用户的密码。你现在可以登录到管理控制台配置tomcat服务器:

    http://127.0.0.1:8080/manager/html
    http://127.0.0.1:8080/host-manager/html


设置一个特定的管理员帐户密码
-------------------------------------------------

如果你想使用一个预设的密码,而不是一个随机生成的一个,你可以运行容器时
设置环境变量“TOMCAT_PASS”设置你的特定密码:

    docker run -d -p 8080:8080 -e TOMCAT_PASS="mypass" dockerxman/tomcat

现在,您可以测试你的部署:

    http://127.0.0.1:8080/

完成!


代码创建和维护
-------------
* QQ: 479608797

* 邮件: fenyunxx@163.com

* [github](https://github.com/xiongjungit/docker-tomcat)

* [dockerhub](https://hub.docker.com/r/dockerxman/)


