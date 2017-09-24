# MacOSX 笔记 - 传说中的闲人

## 附录I - Mac截图快捷键技巧
***
Mac的截图功能扩展功能很强大的，不要用QQ那个COM+Ctrl+A弱爆了的截图了~
首先说一下两种截图
1. Command＋shift＋3:全屏截图，保存截图到桌面
2. Command＋shift＋4:鼠标选定区域截图，保存截图到桌面

这里说明一下,以上两个操作，如果你同时按住Ctrl，最后保存截图在剪切板里，你可以COM+V来直接粘贴到编辑界面
第一种截图就是无脑截图了，不说什么了
第二种截图，还有小技巧
- 使用Command＋shift＋4后，按下空格键，鼠标会变成一个小相机，这时候你使用鼠标对一个窗口点击一下鼠标左键，你已经对一个窗口进行了截图。
- 按Command＋shift＋4 后 ,画一个抓取的区域，不要松开鼠标，接着
1. 按住空格可以移动这个区域；
2. 按住 Shift后，将锁定X 或者 Y轴进行拖动；
3. 按住 Option后 将按照区域圆心进行放大；

最后所有截图将直接显示在桌面上。是不是发现很神奇啊，其实还有更强大的
截图也可以在屏保的使用，操作如下
1. 首先，进入“系统偏好设置” -> “桌面于屏幕保护” -> “屏幕保护程序”。选择你想截屏的屏幕保护，按住Command-Shift，然后点击“测试”按钮。
2. 等屏幕保护开始运行后，不要松开Command-Shift键，再按照自己需求按3/4键。一张屏幕保护的截屏就完成了。
这个可以应用到很多地方，发挥你的扩展思维吧~
默认截图文件名是中文的，如何截图文件名改成英文命名，文件名由两部分构成：前缀和时间戳。
首先来修改前缀。打开终端（可以在Spotlight中输入“Terminal”并点选“应用程序”右边的“终端”），输入以下命令:

```
defaults write com.apple.screencapture name Screenshot
killall SystemUIServer
```

将蓝色部分替换为任意所需的单词即可，例如“Screenshot”。要让前缀修改生效，需要重新启动系统。
时间戳改成英文AM、PM的表示方式，需要到“系统偏好设置”。点选“语言与文本”，并选择“格式”选项卡。在中间的“时间”部分点按“自定…”按钮。把左下角的“正午前”和“正午后”右边的文字分别改成“AM”和“PM”即可。
- 如何弄掉阴影

```
defaults write com.apple.screencapture disable-shadow -bool true
killall SystemUIServer
```

- 恢复

```
defaults write com.apple.screencapture disable-shadow -bool false
killall SystemUIServer
```

- 其实截图还可以用在登陆界面
登陆界面在进入系统之前，所以截图的快捷键无法使用，但是我们可以进入系统之后再次调出登陆界面的
在终端里输入以下指令：

```
/System/Library/CoreServices/loginwindow.app/Contents/MacOS/loginwindow
```

***



## 附录II - Mac命令大全

### 目录操作
| 命令名	| 功能描述 | 使用举例 |
| ----- | :------ | :----- |
| mkdir | 创建一个目录 | mkdir dirname |
| rmdir	| 删除一个目录 | rmdir dirname |
| mvdir	| 移动或重命名一个目录 | mvdir dir1 dir2 |
| cd | 改变当前目录 | cd dirname |
| pwd | 显示当前目录的路径名 | pwd |
| ls | 显示当前目录的内容 | ls -la |
| dircmp | 比较两个目录的内容 | dircmp dir1 dir2 |
### 文件操作
| 命令名	| 功能描述 | 使用举例 |
| ----- | :------ | :----- |
| cat	| 显示或连接文件	| cat filename | 
| pg	| 分页格式化显示文件内容	| pg filename | 
| more	| 分屏显示文件内容	| more filename | 
| od	| 显示非文本文件的内容	| od -c filename | 
| cp	| 复制文件或目录	| cp file1 file2 | 
| rm	| 删除文件或目录	| rm filename | 
| mv	| 改变文件名或所在目录	| mv file1 file2 | 
| ln	| 联接文件	| ln -s file1 file2 | 
| find	| 使用匹配表达式查找文件	| find . -name "*.c" -print | 
| file	| 显示文件类型	| file filename | 
| open	| 使用默认的程序打开文件	| open filename | 
### 选择操作
| 命令名	| 功能描述 | 使用举例 |
| ----- | :------ | :----- |
| head	| 显示文件的最初几行	| head -20 filename | 
| tail	| 显示文件的最后几行	| tail -15 filename | 
| cut	| 显示文件每行中的某些域	| cut -f1,7 -d: /etc/passwd | 
| colrm	| 从标准输入中删除若干列	| colrm 8 20 file2 | 
| paste	| 横向连接文件	| paste file1 file2 | 
| diff	| 比较并显示两个文件的差异	| diff file1 file2 | 
| sed	| 非交互方式流编辑器	| sed "s/red/green/g" filename | 
| grep	| 在文件中按模式查找	| grep "^[a-zA-Z]" filename | 
| awk	| 在文件中查找并处理模式	| awk '{print $1 $1}' filename | 
| sort	| 排序或归并文件	| sort -d -f -u file1 | 
| uniq	| 去掉文件中的重复行	| uniq file1 file2 | 
| comm	| 显示两有序文件的公共和非公共行	| comm file1 file2 | 
| wc	| 统计文件的字符数、词数和行数	| wc filename | 
| nl	| 给文件加上行号	| nl file1 >file2 | 
### 安全操作
| 命令名	| 功能描述 | 使用举例 |
| ----- | :------ | :----- |
| passwd	| 修改用户密码	| passwd | 
| chmod	| 改变文件或目录的权限	| chmod ug+x filename | 
| umask	| 定义创建文件的权限掩码	| umask 027 | 
| chown	| 改变文件或目录的属主	| chown newowner filename | 
| chgrp	| 改变文件或目录的所属组	| chgrp staff filename | 
| xlock	| 给终端上锁	| xlock -remote | 
### 编程操作
| 命令名	| 功能描述 | 使用举例 |
| ----- | :------ | :----- |
| make	| 维护可执行程序的最新版本	| make | 
| touch	| 更新文件的访问和修改时间	| touch -m 05202400 filename | 
| dbx	| 命令行界面调试工具	| dbx a.out | 
| xde	| 图形用户界面调试工具	| xde a.out | 
### 进程操作
| 命令名	| 功能描述 | 使用举例 |
| ----- | :------ | :----- |
| ps	| 显示进程当前状态	| ps u | 
| kill	| 终止进程	| kill -9 30142 | 
| nice	| 改变待执行命令的优先级	| nice cc -c *.c | 
| renice	| 改变已运行进程的优先级	| renice +20 32768 | 
### 时间操作
| 命令名	| 功能描述 | 使用举例 |
| ----- | :------ | :----- |
| date	| 显示系统的当前日期和时间	| date | 
| cal	| 显示日历	| cal 8 1996 | 
| time	| 统计程序的执行时间	| time a.out | 
### 网络与通信操作
| 命令名	| 功能描述 | 使用举例 |
| ----- | :------ | :----- |
| telnet	| 远程登录	| telnet hpc.sp.net.edu.cn | 
| rlogin	| 远程登录	| rlogin hostname -l username | 
| rsh	| 在远程主机执行指定命令	| rsh f01n03 date | 
| ftp	| 在本地主机与远程主机之间传输文件	| ftp ftp.sp.net.edu.cn | 
| rcp	| 在本地主机与远程主机之间复制文件	| rcp file1 host1:file2 | 
| ping	| 给一个网络主机发送 | 回应请求	ping hpc.sp.net.edu.cn | 
| mail	| 阅读和发送电子邮件	| mail | 
| write	| 给另一用户发送报文	| write username pts/1 | 
| mesg	| 允许或拒绝接收报文	| mesg n | 
### Korn Shell 命令
| 命令名	| 功能描述 | 使用举例 |
| ----- | :------ | :----- |
| history	| 列出最近执行过的 | 几条命令及编号	history | 
| r	| 重复执行最近执行过的 | 某条命令	r -2 | 
| alias	| 给某个命令定义别名	| alias del=rm -i | 
| unalias	| 取消对某个别名的定义	| unalias del | 
### 其它命令
| 命令名	| 功能描述 | 使用举例 |
| ----- | :------ | :----- |
| uname	| 显示操作系统的有关信息	| uname -a | 
| clear	| 清除屏幕或窗口内容	| clear | 
| env	| 显示当前所有设置过的环境变量	| env | 
| who	| 列出当前登录的所有用户	| who | 
| whoami	| 显示当前正进行操作的用户名	| whoami | 
| tty	| 显示终端或伪终端的名称	| tty | 
| stty	| 显示或重置控制键定义 | stty -a | 
| du	| 查询磁盘使用情况	| du -k subdir | 
| df	| 显示文件系统的总空间和可用空间	| df /tmp | 
| w	| 显示当前系统活动的总信息	| w | 
