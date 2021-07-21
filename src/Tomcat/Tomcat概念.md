# Tomcat概念
## 1. Tomact服务器和Servlet版本的对应关系

<img src="https://gitee.com/YunboCheng/imageBad/raw/master/image/20210713124308.png" style="zoom:50%;" />

## 2 .Tomcat软件目录的介绍

- bin	专门用来存放 Tomcat 服务器的可执行程序
- conf   专门用来存放 Tomcat 服务器的配置文件
- lib     专门用来存放 Tomcat 服务器的jar包 （jar包：对javaEE实现的规范，j存放ava类）
- logs   专门用来存放 Tomcat  服务器运行时输出的日志信息(某年某月某时 的记录)
- temp    专门用来存放 Tomcat  运行时产生的临时数据，工程完成之后会进行释放。
- webapps  专门用来存放部署的 web 工程。(里边一个目录一个工程)
- work  是 Tomcat  工作时的目录，用来存放 Tomcat  运行时 jsp 翻译为 Servlet 的源码，和Session钝化(对象的序列化和反序列化)的目录。把一个jsp文件编译为一个java文件，并把他编辑为一个类文件，new出一个对象，去调用这个对象中的方法。

## 3. 如何启动 Tomcat  服务器

- 找到 Tomcat  目录下的bin目录下的 startup.bat 文件，双击，就可以启动 Tomcat  服务器。

- 如何测试 Tomcat  服务器启动成功呢？

- 打开浏览器，在浏览器地址栏输入以下的地址(找到本机的地址)：

- 这里只能使用 http 协议 必须使用 8080 端口号是因为在 Tomcat7的目录下的conf（配置文件）中的server.xml文件中设置了 访问的浏览器的协议以及端口号
  - port="8080" protocol="HTTP/1.1" （支持http协议，端口号为8080） 
  - Define a SSL HTTP/1.1 Connector on port 8443 (不支持https协议)
    - http://localhost:8080
    - http://127.0.0.1:8080 
    - http://自己笔记本的真是ip:8080
    当出现如下界面说明启动成功：
    <img src="https://gitee.com/YunboCheng/imageBad/raw/master/image/20210713130818.png" style="zoom:50%;" />

## 4. 常见的启动失败情况

- 双击 startup.bat 文件，就会出现一个小黑窗口一闪而过。
- 这个时候绝大多数都是没有配置好 JAVA_HOME 环境变量。

## 5. 常见JVAV_HOME配置错误

- JAVA_HOME 必须全部大写
- JAVA_HOME 中间必须是下划线，不要减号
- JAVA_HOME 配置的路径只需要配置到 jdk 的安装目录即可。不需要带上 bin 目录。

## 6.另一种启动 Tomcat 服务器的方式

1. 打开命令行
2. cd 到 你的 Tomcat 的 bin目录下
3. 输入启动命令：catalina run

## 7. 停止 Tomcat 服务器

1. 点击 Tomcat 关闭按钮
2. 把 Tomcat 窗口置为当前窗口，然后按快捷键 Ctrl + C 
3. 找到 Tomcat 的 bin 目录下的 shutdown.bat 双击，就可以停止 Tomcat 服务器（主要）

## 8.如何修改 Tomcat 的端口号

- mysql默认端口号：3306
- Tomcat默认端口号 ：8080
- http协议默认的端口号 ：80   http://www.baidu.com:80

找到 Tomcat 目录下的 conf 目录，找到 sever.xml  找到  Connector 标签 

将 port 中的 8080 改为 你需要的端口号。

![](https://gitee.com/YunboCheng/imageBad/raw/master/image/20210713171421.png) 

![](https://gitee.com/YunboCheng/imageBad/raw/master/image/20210714205057.png)
## 9.如何部署 Web 工程到 Tomcat 中

1. 第一种部署方式：只需要把 web 工程的目录拷贝到 Tomcat 的 webapps 目录下即可。

   - 在 webapps 目录下创建一个 Test 工程

     <img src="https://gitee.com/YunboCheng/imageBad/raw/master/image/20210713173648.png" style="zoom:50%;" />

   - 把上午做的提交表单放在 Test 文件夹下

     <img src="https://gitee.com/YunboCheng/imageBad/raw/master/image/20210713173801.png" style="zoom:50%;" />

   - 如何访问 Tomcat 下的web工程。

     此时在浏览器地址栏输入 http://localhost:8080  代表此时查询路径在 Tomcat 目录下的 webapps 目录中，

     <img src="https://gitee.com/YunboCheng/imageBad/raw/master/image/20210713174211.png" style="zoom:50%;" />

     此时要访问 Test工程（即Test文件夹），直接在 地址后加文件名称  http://localhost:8080/Test/重点：表单验证.html

2. 第二种部署方式：找到 Tomcat 下的 D:\Tomcat7\conf\Catalina\localhost 目录，在这个目录下创建配置文件

   <!--Context 表示一个工程的上下文
          path表示工程的访问路径：/abc
          docBase表示你的工程目录在哪里
   -->

   下边的这个就是配置文件的格式

   <Context path = "abc/" docBase = "E:\book"/>

## 10.手托html页面和浏览器中输入地址访问的背后不同的原因



## 11.默认访问的工程和默认访问的的资源

- 当我们子啊浏览器地址栏输入访问地址如下：

  http://ip:port/       没有工程名的时候，默认访问的是 ROOT工程。

- 当我们在浏览器地址栏中输入的访问地址如下：

  http://ip:port/工程名/   没有资源名，默认访问的 index.html 页面。

## 12.IDEA整合 Tomcat 服务器

1. 在idea的设置中找到 构建、执行、部署下 找到应用程序服务器
2. 点击上方的 + 号，选择Tomcat服务器，在弹出的对话框的 Tomcat主目录中找到自己计算机 Tomcat的软件位置。
3. 当将 Tomcat 主目录填写完成之后，下边的Tomcat 基目录会自己填充好，并且会在中间显示出 该Tomcat 的版本号
4. 当你下一次在创建 模块的时候 ，应用程序服务器的那一栏可以选择你刚才配置的 Tomcat 文件

## 13.如何创建动态的 Web 工程

1. 创建一个新模块：先有工程，再有模块  选择Java Enterprise 选择应用程序服务器，选择刚才配置的 Tomcat版本文件
2. 选择要创建什么类型的模块：