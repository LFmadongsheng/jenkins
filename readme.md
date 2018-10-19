## jenkins实现前端自动化部署记录

###  首先他需要java环境 然后下载 jenkins 

### 默认安装,创建管理员账号, 就可以登录了(http://localhost:8080/) 这个是本地构建进去之后大概就这个样子

![](https://raw.githubusercontent.com/LFmadongsheng/imagesBed/master/img/20181018180159.png)

#### 前端构建 用到了node 需要下载node插件  

### 还需要配置目标服务器的 Publish over SSH

#### 下载插件  在系统管理 ->  插件管理

![](https://raw.githubusercontent.com/LFmadongsheng/imagesBed/master/img/20181018180512.png)

这是系统管理的一些东西 这里面用到了  系统设置 下面 最后面有一个 publish over SSH


![](https://raw.githubusercontent.com/LFmadongsheng/imagesBed/master/img/20181018185113.png)

ssh Server name (根据项目)随便起
Hostname  项目部署服务器地址
username  服务器用户名
remote directory  项目在服务器路径

点击高级 出现下图 
password : 服务器密码
![](https://raw.githubusercontent.com/LFmadongsheng/imagesBed/master/img/20181018185614.png)

之后就可以开始做项目具体配置构建了

1新建任务

![](https://raw.githubusercontent.com/LFmadongsheng/imagesBed/master/img/20181018185923.png)

选择构建一个自由风格的软件项目

![](https://raw.githubusercontent.com/LFmadongsheng/imagesBed/master/img/20181018190032.png)

2 配置
![](https://raw.githubusercontent.com/LFmadongsheng/imagesBed/master/img/20181018190109.png)

3 源码管理
![](https://raw.githubusercontent.com/LFmadongsheng/imagesBed/master/img/20181018190207.png)
![]

4 构建触发器
(https://raw.githubusercontent.com/LFmadongsheng/imagesBed/master/img/20181018190413.png)

构建触发器设置在什么情况下触发构建

5 构建环境

![](https://raw.githubusercontent.com/LFmadongsheng/imagesBed/master/img/20181019102613.png)


6 构建

![](https://raw.githubusercontent.com/LFmadongsheng/imagesBed/master/img/20181019102731.png)

由于我本地windows的系统 所以执行了windows批处理命令 (如果在服务器上直接执行shell方便很多)

7  构建后的操作 

![](https://raw.githubusercontent.com/LFmadongsheng/imagesBed/master/img/20181019102956.png)

在这里选择了之前下载的插件 send build artifacts over SSH

![](https://raw.githubusercontent.com/LFmadongsheng/imagesBed/master/img/20181019103154.png)

这里 SSH server Name  是之前系统设置里面配的服务名字
Transfer Set Source Files  这是要传输给服务器的文件
Exec command  这里就是上传服务器之后要执行的shell命令了

