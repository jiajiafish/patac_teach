
### linux发展简史
*难以复制的计算机科学传奇*



> 操作系统始于二十世纪 50 年代，当时的操作系统能运行批处理程序。批处理程序不需要用户的交互，它从文件或者穿孔卡片读取数据，然后输出到另外一个文件或者打印机。
>
> 二十世纪六十年代初，交互式操作系统开始流行。它不仅仅可以交互，还能使多个用户从不同的终端同时操作主机。这样的操作系统被称作分时操作系统，它的出现对批处理操作系统是个极大的挑战。许多人尝试开发分时操作系统， 其中包括一些大学的研究项目和商业项目。当时有一个项目叫做" Multics ",它的技术在当时很创新。" Multics "项目的开发并不顺利。它花费了远超过预计的时间来完成，却没有在操作系统市场上占到多少份额。而参加该项目的一个开发团体-贝尔实验室退出了这个项目。他们在退出后开发了他们自己的一个操作系统—— UNIX。
>
> UNIX 最初免费发布并因此在大学里受到欢迎。后来，UNIX 实现了 TCP/IP 协议栈，成为了早期工作站的操作系统的一个流行选择。
>
> 1990年，UNIX 在服务器市场尤其是大学校园成为主流操作系统，许多校园都有 UNIX 主机，当然还包括一些研究它的计算机系的学生。这些学生都渴望能在自己的电脑上运行 UNIX 。不幸的是，从那时候开始，UNIX 开始变得商业化，它的价格也变得非常昂贵。而唯一低廉的选择就是 MINIX ,这是一个功能有限的类似 UNIX 的操作系统，作者 Andrew Tanebaum 开发它的目的是用于教学。
>
> 1991 年 10 月，Linus Torvalds（Linux 之父）在赫尔辛基大学接触 UNIX ,他希望能在自己的电脑上运行一个类似的操作系统。可是 UNIX 的商业版本非常昂贵，于是他从 MINIX 开始入手，计划开发一个比 MINIX 性能更好的操作系统。很快他就开始了自己的开发工作。他第一次发行的版本很快吸引了一些黑客。尽管最初的 Linux 并没有多少用处，但由于一些黑客的加入使它很快就具有了许多吸引人的特性，甚至一些对操作系统开发不感兴趣的人也开始关注它。
>
> ![Nvidia开源Tegra的3D驱动](http://static.open-open.com/news/uploadImg/20130409/20130409222600_603.jpg)
>
> Linux 本身只是操作系统的内核。内核是使其他程序能够运行的基础。它实现了多任务和硬件管理，用户或者系统管理员交互运行的所有程序实际上都运行在内核之上。其中有些程序是必需的，比如说，命令行解释器（shell）,它用于用户交互和编写 shell 脚本（.bat文件）。 Linus没有自己去开发这些应用程序，而是使用已有的自由软件。这减少了搭建开发环境而所需花费的工作量。实际上，他经常改写内核，使得那些程序能更容易在 Linux 上运行。许多重要的软件，包括 C 编译器，都来自于自由软件基金 GNU 项目。GNU 项目开始于 1984 年，目的是为了开发一个完全类似于 UNIX 的免费操作系统。为了表扬 GNU 对 Linux 的贡献，许多人把 Linux 称为GNU/Linux（GNU 有自己的内核）。

GNU的全称是  "==G==NU is ==N==ot ==U==nix",源自程序设计师的递归的黑色幽默~~~~
>
> 1992－1993 年，Linux 内核具备了挑战 UNIX 的所有本质特性，包括 TCP/IP 网络，图形界面系统（X window)，Linux 同样也吸引了许多行业的关注。一些小的公司开发和发行Linux，有几十个 Linux 用户社区成立。1994 年，Linux 杂志也开始发行。
>
> Linux 内核 1.0 在 1994 年三月发布，内核的发布要经历许多开发周期，直至到达一个稳定的版本。
> 1994 年，Torvalds 发布 Linux-v1.0；
>
> 1996 年，Torvalds 发布 Linux-v2.0，确定了 Linux 的吉祥物：企鹅；

### Linux距离我们有多远

Shotgun平台基于Centos开发,之前测试服务安装了过一个Redhat.

Shotgun上的自动化工具基于Centos进行的开发,包含

*   金图系统,
*   任务上下游数据衔接, 
*   EDR任务按照时间搜索,
*   Subassign任务,
*   服务器容量日报

我们使用的安卓操作系统也是基于Linux开发,广义上也是linux的一个发行版.

谷歌的Chromebook操作系统也是基于Linux开发

不过大部分都是不可见的部分,

### 发行版
与windows不同,linux原始的版本只定义了linux的内核,其他所有的驱动,软件都是随着用户制作的发型版发放.因此,根据不同的用途和设计者的意图,产生了无数的linux发行版.制作者不仅可以直接采用linux内核进行开发发行版,如Debian;也可以基于其他发行版开发,如国产的kylin操作系统就是基于Ubuntu操作系统进行开发而来.

> 关于国产linux操作系统是否属于自主可控的操作系统,就如同问A---ndroid是否是谷歌自己的操作系统如出一辙.Macos是基于DarwinBSD的操作系统,DarwinBSD是Unix 操作系统,只不过苹果二次开发后就没有再开放操作系统了.(开放了部分内核)

 开源贡献量比较

| company | repositories | site                         |
| ------- | ------------ | ---------------------------- |
| 微软      | 1965         | https://github.com/Microsoft |
| 谷歌      | 1351         | https://github.com/google    |
| 苹果      | 53           | https://github.com/apple     |

![img](https://static.cnbetacdn.com/article/2018/0206/95b1d6f4d3aaf66.png)

著名的发行版
* Redhat Linux :最强大的商用linux发行版,linux发展的主要推动者.

* CentOs : Community Enterprise Operating System,相当于社区版本开源的redHat linux发行版**我们公司的shotgun基于此系统进行开发**

* Debian : 最经典的linux发行版,非常多的linux都是基于Debian开发. 

* Ubuntu : 最受欢迎的linux发行版,针对桌面操作系统做了大量的优化.基于Debian操作系统

* Kali : 渗透测试系统,有相关的认证.

  ​

  ​

  ​

  linux发行版按照使用的包管理工具分为两种,apt_get包管理和yum包管理工具

  ```shell
  apt-cache search package 搜索包
  apt-cache show package 获取包的相关信息，如说明、大小、版本等
  sudo apt-get install package 安装包
  sudo apt-get install package -- reinstall 重新安装包
  sudo apt-get -f install 修复安装"-f = --fix-missing"
  sudo apt-get remove package 删除包
  sudo apt-get remove package -- purge 删除包，包括删除配置文件等
  sudo apt-get update 更新源
  sudo apt-get upgrade 更新已安装的包
  sudo apt-get dist-upgrade 升级系统
  sudo apt-get dselect-upgrade 使用 dselect 升级
  apt-cache depends package 了解使用依赖
  apt-cache rdepends package 是查看该包被哪些包依赖
  sudo apt-get build-dep package 安装相关的编译环境
  apt-get source package 下载该包的源代码
  sudo apt-get clean && sudo apt-get autoclean 清理无用的包
  sudo apt-get check 检查是否有损坏的依赖
  ```

  ​





### 区别

#### 桌面方面

*   windows :世界上最大的软件平台,可以满足任何的工作生活开发需求,软件开发技术丰富,采用的是较为松散的软件发布方式.https://code.visualstudio.com/

    ![img](/home/digital/Desktop/深度截图_选择区域_20180905124840.png)

*   linux:桌面软件非常少,采用的是开发比较流行的包管理方式进行软件发布.因此有高度依赖网络的问题.

    ```shell
    digital@digital-PC:~/Desktop/numpy_pandas_matplotlib$ sudo apt-get install vscode
    [sudo] digital 的密码：
    正在读取软件包列表... 完成
    正在分析软件包的依赖关系树       
    正在读取状态信息... 完成       
    vscode 已经是最新版 (1.22.2-1523551015)。
    下列软件包是自动安装的并且现在不需要了：
      libjpeg8 libjs-jquery libjs-modernizr libjs-underscore libpng12-0 python3-pyqt5.qtsvg python3-qtpy xxdiff
    使用'sudo apt autoremove'来卸载它(它们)。
    升级了 0 个软件包，新安装了 0 个软件包，要卸载 0 个软件包，有 1299 个软件包未被升级。

    ```

    ​

#### 服务器方面

windows:windows server 2008一直是最受欢迎的服务器操作系统,没有之一,稳定性不容置疑.

![img](http://www.azureyun.com/wp-content/uploads/2018/03/032118_0119_WindowsServ3.png)sudo apt install cmatrix

linux:很多小型的网站,个人博客,使用centos作为开发平台,主要原因是开源,免费,节省成本.稳定性经过长期的更迭已经十分的可靠,而且有很多linux下的服务器布置的套路,Lamp或者Lnmp

Linux + Apache + Mysql + Php

Linux + Nginx + Mysql + Php

![img](https://s.w.org/images/home/screen-themes.png?3)



Macos Server:只能说有自己的服务器软件,仅此而已https://www.apple.com/cn/macos/server/servers-made-easy/

sl 

![Linux下有趣的命令Linux下有趣的命令](https://www.linuxprobe.com/wp-content/uploads/2016/12/wKioL1hJWTLwZ0_fAAK6sfxGKnw851.gif)

cmatrix



![Linux下有趣的命令Linux下有趣的命令](https://www.linuxprobe.com/wp-content/uploads/2016/12/wKioL1hJWbzRW2glAAN51bl4slI879.gif)



#### 安装建议

建议安装在虚拟环境中.比如vitualbox或者vmware.

发行版建议ubuntu.

数字化平台上的实时数据分析工具,实时检测实际工作中的异常现象,并尽快处理,类似微信后台.

