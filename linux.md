*~~<font color=red>@2019072102d</font>~~ *
# 1.推荐学习网站

> https://www.linuxprobe.com/
# 2.安装虚拟机及红帽操作系统
> 1.虚拟机安装地址：https://pan.baidu.com/share/init?surl=dF9YCfB
> 百度网盘密码为：sm7s
> 2.红帽系统安装地址：https://pan.baidu.com/s/1dEWdcch
> 百度网盘密码为：j94c
> 3.使用虚拟机：
> (1)创建虚拟机-->典型-->稍后安装操作系统-->linux redhat 7-->设置位置和虚拟机名字-->默认设置-->完成-->内存2GB(根据电脑内存设置，一般设置为电脑内存的一半，但当电脑内存大于4个G的时候，通常都设置为2GB-->
> ![在这里插入图片描述](https://img-blog.csdnimg.cn/20190722211812684.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L0lUX1NvZnRFbmdpbmVlcg==,size_16,color_FFFFFF,t_70)说明：处理器的核心数量根据电脑的实际数量来设置(查看电脑处理器核心数量的方法：右击电脑选择设备管理器，选择处理器，一般显示几个就表明电脑的处理器的核心数量时几个)-->新CD/DVD(使用ISO镜像文件，选择下载好的镜像文件)-->网路适配器选择仅主机模式
>说明：桥接模式：相当于在物理主机与虚拟机网卡之间架设了一座桥梁，从而可以通过物理主机的网卡访问外网。
NAT模式：让VM虚拟机的网络服务发挥路由器的作用，使得通过虚拟机软件模拟的主机可以通过物理主机访问外网，在真机中NAT虚拟机网卡对应的物理网卡是VMnet8。
仅主机模式：仅让虚拟机内的主机与物理主机通信，不能访问外网，在真机中仅主机模式模拟网卡对应的物理网卡是VMnet1。
-->把USB控制器、声卡、打印机设备等不需要的设备统统移除掉
(2)安装红帽系统
-->使用方向键选择第一个选项安装操作系统-->选择语言为英文(美国)-->单击SOFTWARE SELECTION选项，选中Server with GUI单选按钮，然后单击左上角的Done按钮即可-->单击NETWORK & HOSTNAME选项后，将Hostname字段设置为linuxprobe.com，然后单击左上角的Done按钮-->返回到安装主界面，单击INSTALLATION DESTINATION选项来选择安装媒介并设置分区。此时不需要进行任何修改，单击左上角的Done按钮即可-->单击Begin Installation按钮后即可看到安装进度-->选择ROOT PASSWORD设置root管理员的密码-->设置账号及密码-->单击Reboot-->单击LICENSE INFORMATION选项接受即可-->
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190722214606719.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L0lUX1NvZnRFbmdpbmVlcg==,size_16,color_FFFFFF,t_70)-->![在这里插入图片描述](https://img-blog.csdnimg.cn/20190722214620972.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L0lUX1NvZnRFbmdpbmVlcg==,size_16,color_FFFFFF,t_70)
# 3.linux命令
## 3.1常用系统工作命令
### 3.1.1echo命令
> echo命令用于在终端输出字符串或变量提取后的值，格式为“echo [字符串 | $变量]”。
>1.指定字符串“Linuxprobe.com”输出到终端屏幕的命令为：echo Linuxprobe.Com
>2.使用$变量的方式提取变量SHELL的值，并将其输出到屏幕上：echo $SHELL
### 3.1.2date命令
> date命令用于显示及设置系统的时间或日期，格式为“date [选项] [+指定的格式]”。

|参数| 作用|
|--|--|
| %t | 跳格[Tab键] |
| %H | 小时（00～23）|
| %I | 小时（00～12）| 
| %M | 分钟（00～59）|
| %S | 秒（00～59）|
| %j | 今年中的第几天 |

> 1.按照默认格式查看当前系统时间的date命令如下所示：date
> 2.按照“年-月-日 小时:分钟:秒”的格式查看当前系统时间的date命令如下所示：date "+%Y-%m-%d %H:%M:%S"
>3.将系统的当前时间设置为2017年9月1日8点30分的date命令如下所示：date -s "20170901 8:30:00"
>4.再次使用date命令并按照默认的格式查看当前的系统时间，如下所示：date
>5.date命令中的参数%j可用来查看今天是当年中的第几天。这个参数能够很好地区分备份时间的新旧，即数字越大，越靠近当前时间。该参数的使用方式以及显示结果如下所示：date "+%j"
### 3.1.3reboot命令
>reboot命令用于重启系统，其格式为reboot。
### 3.1.4poweroff命令
> poweroff命令用于关闭系统，其格式为poweroff。
### 3.1.5wget命令
> wget命令用于在终端中下载网络文件，格式为“wget [参数] 下载地址”。

|参数| 作用 |
|--|--|
| -b | 后台下载模式 |
| -P | 下载到指定目录 |
| -t | 最大尝试次数 |
| -c | 断点续传 |
| -p | 下载页面内所有资源，包括图片、视频等 |
| -r | 递归下载 |



 



