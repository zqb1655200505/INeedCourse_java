## 北理工抢课专用程序

# 首先声明，这个脚本软件是我根据 'friskit-china'博主的I_NEED_COURSE（https://github.com/friskit-china/I_NEED_COURSE ）而写的java版本。由于原项目是使用python开发的，而且存在一个很大的局限，一个进程只能选择某一门具体的课。因此我采用java改写，优化了可同时监听多门课程。使用方法与原来python版本一样。下面的具体过程我是将原项目的readme直接粘贴过来的。与python不同的是，若是想同时监听多门课程，只需要增加配置文件的内容为多门课程对应的数据即可，但是需要将没门课程的数据以换行进行分割（即课程之间有一个空白行）

# 免责声明

1. 抢课是一种很不好的行为，因为你能抢到课，就说明有人退课。退课很有可能是为了在主观上把课让给同学、男/女朋友。
2. 抢课会给服务器带来刷新压力，所以请把刷新时间拉长一些。
3. 我只是个做工具的，把工具给你了，怎么用就看你了。
4. 如果你用了这个工具，就说明你愿意承担一切后果，而不要赖到作者头上。
5. 写文档水平太差，请发动你们的洪荒之力好好理解，理解不了也别问我了。。
6. 抢上课了就好好学习吧，以后自己写脚本。

## 程序功能

不间断刷新课程列表，自动抢能够抢到的课。建议用法：把这个程序开着，让他跑着吧。

## 程序环境

java

## 依赖库 (版本可以不一样)
1、commons-beanutils-1.9.1.jar  
2、commons-collections-3.2.1.jar  
3、commons-lang-2.6.jar  
4、commons-logging-1.2.jar  
5、ezmorph-1.0.6.jar  
6、httpclient-4.5.6.jar  
7、httpcore-4.4.10.jar  
8、httpmime-4.5.6.jar  
9、json-lib-2.4-jdk15.jar
 

## 用法
fork项目到自己仓库并clone到本地或者下载项目源代码的zip包，用idea打开直接运行就OK了。

## 关于配置文件

由于目前这个系统，人和人之间提交的表单都不一样，我的解决方案是使用一个配置文件把表单的内容记录下来。每一门课都有一个配置文件。程序执行需要读取这个配置文件。配置文件如何获取？

1. 下载fiddler：https://www.telerik.com/download/fiddler 填email地址然后点download。
2. 进入选课界面
3. 打开fiddler
4. 对想要选的课，不管是不是已经满了，都点击“选课”按钮
5. 这时候fiddler里会多一条记录，URL地址应该是：http://grdms.bit.edu.cn/yjs/dwr/call/plaincall/YYPYCommonDWRController.pyJxjhSelectCourse.dwr
6. 点击这条记录，在右侧面板点击Inspectors，在弹出的下面的选项卡中选择Raw。
7. 把文本框中空行之后的部分复制到一个空文件中，文件名任选，保存到本程序的目录中。（具体需要复制的部分见本目录下的图片“configure.png”）
8. 这个文件名就是上面用法中的“配置文件名”
9. 除了需要配置文件之外还需要一个Cookie文件。

## 关于Cookie

程序还需要保存Cookie才能模拟你本人登录，得到Cookie的方法跟上面前6布一样，只不过这时候复制的内容不是空行以后的内容，而是以“Cookie: ”为开头的一行文本。（见图cookie.png）

这个文件必须命名为cookies.txt，保存到本程序目录下。
