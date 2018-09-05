# git简介

git是什么,简单的讲就是后悔药,有人将其比喻成时光机器,重要的是理解git的工作方式.

Git有什么特点？简单来说就是：高端大气上档次！它一经出现就将之前的svn等等版本控制系统赶尽杀绝了.

Git 是 Linus Torvalds 为了帮助管理 Linux 内核开发而开发的一个开放源码的版本控制软件。Linux做为世界上最最著名的开源软件,其开发难度可想而知,为了满足日益增长的开发复杂度,以及增强Linux开源社区的凝聚力,Linus花了两个星期开发了初版的git......


> Talk is cheap ,show me the code

基本概念:
* 仓库 git中的项目

# 命令行 使用方法

说了git这么多的好话,git如何使用呢,我们慢慢来说.

## 本地git仓库
和大部分的命令行命令一样,可以通过
* **linux**   `man command`来获得命令的帮助,
* **windows** `command /?`来获得命令的帮助,

### git版本查询
* git --version
```
digital@digital-PC:~$ git --version
git version 2.13.3

```
### git配置
* git config --list 查询当前的设置的config
```
digital@digital-PC:~$ git config --list
user.name=jiaxiaole
user.email=jiaxiaole_2009@163.com
cola.spellcheck=false
core.autocrlf=input

```

* 配置git  下面这两个必须得进行配置否则git无法正常使用

```
$ git config --global user.name "jiaxiaole"
$ git config --global user.email test@runoob.com
```
### 初始化本地仓库
一个普通的目录如何才能被另眼相看为一个git目录?答案就是使用git init,会产生一个`.git`的隐藏的目录.这里面记录的git的组织方式,不要手动更改.

* git init 

```
digital@digital-PC:~/Desktop/gitdemo$ git init
已初始化空的 Git 仓库于 /home/digital/Desktop/gitdemo/.git/
digital@digital-PC:~/Desktop/gitdemo$ ls -l
总用量 0
digital@digital-PC:~/Desktop/gitdemo$ ls -la
总用量 12
drwxr-xr-x 3 digital digital 4096 8月  21 20:29 .
drwxr-xr-x 5 digital digital 4096 8月  21 20:29 ..
drwxr-xr-x 7 digital digital 4096 8月  21 20:29 .git

```
* git init gittest2

```
digital@digital-PC:~/Desktop$ git init gittest2
已初始化空的 Git 仓库于 /home/digital/Desktop/gittest2/.git/
digital@digital-PC:~/Desktop$ ls
BLOG                                                     gitdemo   placeholder.png       下载.png
chrome-dgjgnfccdkfhinkpbjondjdlooamodag-Default.desktop  gittest2  谷歌访问助手chrome版
digital@digital-PC:~/Desktop$ 


```

* git clone 远程仓库地址

```
digital@digital-PC:~/Desktop$ git clone https://github.com/fundata-varena/fundata-python-sdk.git
正克隆到 'fundata-python-sdk'...
remote: Counting objects: 66, done.
remote: Total 66 (delta 0), reused 0 (delta 0), pack-reused 66
展开对象中: 100% (66/66), 完成.
```


### git存档流程

#### 创建第一个git存档

**modified**----->>**staged**----->>**committed**


* 首先创建一个仓库,我现在创建一个叫做digital的仓库
  `git init digital`

* 然后进入这个digital目录下
  `cd digital`

* 查询当前的本地git状态
   `git status`

```
digital@digital-PC:~/Desktop/digital$ git status
位于分支 master

初始提交

无文件要提交（创建/拷贝文件并使用 "git add" 建立跟踪）
```

* 创建一个文件,然后执行`git status`看看有什么变化

```
digital@digital-PC:~/Desktop/digital$ git status
位于分支 master

初始提交

未跟踪的文件:
  （使用 "git add <文件>..." 以包含要提交的内容）

	jxl.txt

提交为空，但是存在尚未跟踪的文件（使用 "git add" 建立跟踪）
```
* 将创建的文件存储到暂存区`git add *`或者`git add .`

* `git status`
```
digital@digital-PC:~/Desktop/digital$ git status
位于分支 master

初始提交

要提交的变更：
  （使用 "git rm --cached <文件>..." 以取消暂存）

	新文件：   jxl.txt
```

* `git commit -m "第一个git"`

* `git log`
```
digital@digital-PC:~/Desktop/digital$ git log
commit b0222bbb3f9ede182ff1c8f3760a2fb913fde267 (HEAD -> master)
Author: jiaxiaole <jiaxiaole_2009@163.com>
Date:   Tue Aug 21 21:01:47 2018 +0800

```
----
**到此为止我们成功的创建(commit)了一个仓库的版本.**

我们来介绍几个新的概念

* **存储地址**:git的身份证号码,上面例子中的b0222bbb3f9ede182ff1c8f3760a2fb913fde267,实际上前七位就够用.
* **HEAD**:当前git命令的指针位置.
* **master**:默认的主branch的名字,其实可以自行修改

----

#### 切换git位置

* 修改第一章,然后执行`git add .&& git commit -m` "修改了第一段的文字"
* 执行`git log`,查看当前的版本内容
* 执行`git checkout 版本前七位`,会发现文字已经发生了变化.
* 执行`git checkout -` 退回到上一个版本
* `git log -p`显示出当前的两个版本修改了那些地方.
```
digital@digital-PC:~/Desktop/digital$ git log -p
commit 670606c447ff4f35caf95e1c19d72788a4eaace0 (HEAD -> master)
Author: jiaxiaole <jiaxiaole_2009@163.com>
Date:   Tue Aug 21 21:31:56 2018 +0800

    添加234

diff --git a/jxl.txt b/jxl.txt
index e846124..246ccfc 100644
--- a/jxl.txt
+++ b/jxl.txt
@@ -1 +1,7 @@
 新华社北京8月20日电　外交部发言人陆慷24日宣布：本次峰会主题为“合作共赢，携手构建更加紧密的中非命运共同体”。中国国家主席习近平将主持峰会并举行相关活动。中非合作论坛非方成员领导人将应邀与会，有关非洲地区组织和国际组织代表将出席峰会有关活动。
+
+第二段
+
+第三段
+
+第四段

commit a85bbed1cece15d010984de14a04ed33c8e9ed3d
Author: jiaxiaole <jiaxiaole_2009@163.com>
Date:   Tue Aug 21 21:21:58 2018 +0800

    修改了第一段文字

```

#### 添加git标签(tag)
标签的主要作用就是给重要的版本做上记号,比如说DSO,IDR,VDR
* `git add .&& git commit -m "第一部结束"`

```
digital@digital-PC:~/Desktop/digital$ git add .&& git commit -m "第一部结束"
[master 094169a] 第一部结束
 1 file changed, 2 insertions(+)

```

* `git tag -a 标签名 -m "备注"` 附注标签,a代表annotation

* `git tag` 查看当前有哪些tag
```

digital@digital-PC:~/Desktop/digital$ git log --all --oneline
d4b5f41 (HEAD, tag: v2, tag: V2, master) 第二章结束了
e761717 第二部开始
094169a (tag: v1) 第一部结束
670606c 添加234
a85bbed 修改了第一段文字
fac2364 (tag: v0.5) 第一段文字
b0222bb 第一个git

```

* 给过往的版本加上tag`git tag -a 标签名 -m "备注" 七位身份证号` 



#### 添加分支(branch)
<!------->

<!------->

* `git branch`故事的发展经常是有多种故事线
* `git checkout branchname` 切换到分支上去
* `git checkout master ` 切换会主分支
* `git checkout -b newbranch` 创建新的分支并且切换上去

```
digital@digital-PC:~/Desktop/digital$ git branch patac
digital@digital-PC:~/Desktop/digital$ git checkout patac
切换到分支 'patac'

```

#### 合并分支

* `git merge 分支名` 执行这个命令的前提是指针已经在主分支上.

```
digital@digital-PC:~/Desktop/digital$ git merge patac
自动合并 jxl.txt
冲突（内容）：合并冲突于 jxl.txt
自动合并失败，修正冲突然后提交修正的结果。
digital@digital-PC:~/Desktop/digital$ git add .
digital@digital-PC:~/Desktop/digital$ git commit -m "done"
[master 9ae8bfd] done
digital@digital-PC:~/Desktop/digital$ git log --all --oneline --graph
*   9ae8bfd (HEAD -> master) done
|\  
| * 5d22989 (patac) 造访泛亚
* | abbc231 造访设计部,没有去工程部
* | d4b5f41 (tag: v2, tag: V2) 第二章结束了
* | e761717 第二部开始
|/  
* 094169a (tag: v1) 第一部结束
* 670606c 添加234
* a85bbed 修改了第一段文字
* fac2364 (tag: v0.5) 第一段文字
* b0222bb 第一个git

```



#### 远程服务

##### 推送到远程
其实输入用户名密码
```
digital@digital-PC:~/Desktop/digital$ git remote add origin https://github.com/jiajiafish/patac1.git
digital@digital-PC:~/Desktop/digital$ git push -u origin master
Username for 'https://github.com': jiajiafish
Password for 'https://jiajiafish@github.com': 
对象计数中: 30, 完成.
Delta compression using up to 8 threads.
压缩对象中: 100% (19/19), 完成.
写入对象中: 100% (30/30), 2.70 KiB | 0 bytes/s, 完成.
Total 30 (delta 9), reused 0 (delta 0)
remote: Resolving deltas: 100% (9/9), done.
To https://github.com/jiajiafish/patac1.git
 * [new branch]      master -> master
分支 master 设置为跟踪来自 origin 的远程分支 master。



```
* 输入`git remote`看到我们的git使用的是https协议,所以每次都需要输入用户名和密码

```
digital@digital-PC:~/Desktop/digital$ git remote add origin  git@github.com:jiajiafish/patac1.git
digital@digital-PC:~/Desktop/digital$ git push -u origin master 
The authenticity of host 'github.com (13.250.177.223)' can't be established.
RSA key fingerprint is SHA256:nThbg6kXUpJWGl7E1IGOCspRomTxdCARLviKw6E5SY8.
Are you sure you want to continue connecting (yes/no)? yes
Warning: Permanently added 'github.com,13.250.177.223' (RSA) to the list of known hosts.
分支 master 设置为跟踪来自 origin 的远程分支 master。
Everything up-to-date

```
* git remote -v 可以看remote仓库的详细内容
* 这样就切换成ssh模式了,可以使用了.


##### 拉取到本地 

只有多个成员的时候才需要这种情况,因为一个人做项目的时候,你本地的项目永远是最新的.

`git pull` 等同于 `git fetch && git merge`

比如说两个人,czh和jxl在共同编辑一个文档的过程中.
```
digital@digital-PC:~/Desktop$ git clone git@github.com:jiajiafish/patac1.git czh
正克隆到 'czh'...
remote: Counting objects: 30, done.
remote: Compressing objects: 100% (10/10), done.
接收对象中: 100% (30/30), 完成.
处理 delta 中: 100% (9/9), 完成.
remote: Total 30 (delta 9), reused 30 (delta 9), pack-reused 0
digital@digital-PC:~/Desktop$ cd czh/
digital@digital-PC:~/Desktop/czh$ 
digital@digital-PC:~/Desktop/czh$ ls
jxl.txt
digital@digital-PC:~/Desktop/czh$ vi jxl.txt 
digital@digital-PC:~/Desktop/czh$ vi jxl.txt 
digital@digital-PC:~/Desktop/czh$ git push -u origin master 
Warning: Permanently added the RSA host key for IP address '13.229.188.59' to the list of known hosts.
分支 master 设置为跟踪来自 origin 的远程分支 master。
Everything up-to-date
digital@digital-PC:~/Desktop/czh$ vi jxl.txt 
digital@digital-PC:~/Desktop/czh$ git remote
origin
digital@digital-PC:~/Desktop/czh$ git remote -v
origin	git@github.com:jiajiafish/patac1.git (fetch)
origin	git@github.com:jiajiafish/patac1.git (push)
digital@digital-PC:~/Desktop/czh$ git status
位于分支 master
您的分支与上游分支 'origin/master' 一致。
尚未暂存以备提交的变更：
  （使用 "git add <文件>..." 更新要提交的内容）
  （使用 "git checkout -- <文件>..." 丢弃工作区的改动）

	修改：     jxl.txt

修改尚未加入提交（使用 "git add" 和/或 "git commit -a"）
digital@digital-PC:~/Desktop/czh$ git add .&&git commit -m "czh"
[master 582c107] czh
 1 file changed, 5 insertions(+)
digital@digital-PC:~/Desktop/czh$ git push -u origin master 
对象计数中: 3, 完成.
Delta compression using up to 8 threads.
压缩对象中: 100% (2/2), 完成.
写入对象中: 100% (3/3), 280 bytes | 0 bytes/s, 完成.
Total 3 (delta 1), reused 0 (delta 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To github.com:jiajiafish/patac1.git
   9ae8bfd..582c107  master -> master
分支 master 设置为跟踪来自 origin 的远程分支 master。

```

这时候另外一个jxl可以采用pull的形式,获得最新czh的更新.

```
digital@digital-PC:~/Desktop/jxl$ git pull
remote: Counting objects: 3, done.
remote: Compressing objects: 100% (1/1), done.
remote: Total 3 (delta 1), reused 3 (delta 1), pack-reused 0
展开对象中: 100% (3/3), 完成.
来自 github.com:jiajiafish/patac1
   9ae8bfd..582c107  master     -> origin/master
更新 9ae8bfd..582c107
Fast-forward
 jxl.txt | 5 +++++
 1 file changed, 5 insertions(+)
digital@digital-PC:~/Desktop/jxl$ 


```

但是有一个问题就是两个人同时的提交push的时候应该如何处理呢?
答案是会出现类似于无法merge的错误.
```
digital@digital-PC:~/Desktop/jxl$ git push -u origin master 
To github.com:jiajiafish/patac1.git
 ! [rejected]        master -> master (fetch first)
error: 无法推送一些引用到 'git@github.com:jiajiafish/patac1.git'
提示：更新被拒绝，因为远程仓库包含您本地尚不存在的提交。这通常是因为另外
提示：一个仓库已向该引用进行了推送。再次推送前，您可能需要先整合远程变更
提示：（如 'git pull ...'）。
提示：详见 'git push --help' 中的 'Note about fast-forwards' 小节。
```