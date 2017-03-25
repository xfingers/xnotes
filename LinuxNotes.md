# Linux 笔记
Coding StudyNotes
***
#  一、Linux用户管理
## 1.查看用户
* > ` who am i `
* > ` who mom likes `

## 2.创建用户
* > ` sudo adduser lilei `    添加新用户
* > ` ls /home `    查看用户列表
* > ` su -l lilei `    切换用户
## 3.用户组
* > ` groups shiyanlou `    查看自己属于哪个用户组
* > ` cat /etc/group | sort`
* > ` cat /etc/group | grep -E "shiyanlou" `
## 4.删除用户
* > ` sudo deluser lilei --remove-home `
# 二、Linux权限
## 1.查看文件权限
* > ` ls -l `
* > ` ll `
* > ` ls -A `
* > ` ls -Al `
* > ` ls -dl /home `
## 2.变更文件所有者
* > ` touch iphone7 `
* > ` cd /home/lilei `
* > ` ls iphone7 `
* > ` sudo chown shiyanlou iphone7 `
* > ` cp iphone7 /home/shiyanlou `
## 3.修改文件权限
* > ` echo "echo \"Hello shiyanlou\"" > iphone7 `
* > ` chmod 700 iphone7 `
* > ` chmod go-rw iphone7 `
# 三、更多
***
#Linux命令行操作笔记

##重要快捷键
* Tab：命令补全
* Ctrl+c：强行中断当前程序
* Ctrl+d：键盘输入结束或退出终端
* Ctrl+s：暂停当前程序，暂停后按下任意键恢复运行
* Ctrl+z：将当前程序放到后台运行，恢复到前台命令为**fg**
* Ctrl+a：将光标移至行首，相当于**Home**键
* Ctrl+e：将光标移至行尾，相当于**End**键
* Ctrl+k：删除从光标所在位置到行末
* Alt+Backspace：向前删除一个单词
* Shift+PgUp：将终端显示向上滚动
* Shift+PgDn：将终端显示向下滚动
* 向上键：恢复之前使用过的历史命令

##通配符
* *：匹配零个或多个字符
* ？：匹配任意一个字符
* [list]：匹配list中任意字符
* [!list]：匹配除了list以外的任意字符
* [c1-c2]：匹配c1-c2中任意单一字符，如[0-9][a-z]
* {string1,string2,...}：匹配string1，string2(或更多)其一字符串
* {c1..c2}：匹配c1-c2中全部字符，如{1..10}

##在命令行中获取帮助
* man <command_name>：如 *man ls*
* <command_name> --help：如 *ls --help*

##有意思的Linux命令
* sysvbanner：
1. > ` sudo apt-get update `
2. > ` sudo apt-get install sysvbanner `
    * > ` banner NICE `
    * > ` printerbanner -w 50 A `
5. > ` sudo apt-get install toilet`
    * > ` toilet NICE`
6. > ` sudo apt-get install figlet `
    * > ` figlet NICE`
### Python 命令行
1. 查看Python版本：
> python -V
2. 进入python交互编程环境
> python
3. 打印“Hello World!”
> print ("Hello World!")
***
##Python 小备注
### 写一段小程序
1. 新建hello.py。打开终端，切换目录至桌面，然后运行vim
> vim hello.py
2. 输入代码并保存
> print ('Hello World!!!')
> wq
3. 运行代码。在终端输入python命令
> python hello.py
***
* Django-IBM: [Django-IBM](https://www.ibm.com/developerworks/cn/linux/l-django/)
* Django-Github: [Django-Github](https://github.com/xfingers/django-intro-zh/blob/master/docs/part1.md)
* Django文档翻译: [Django1.8.2文档](http://python.usyiyi.cn/django/index.html)
* 自强学堂: [自强学堂](http://www.ziqiangxuetang.com/python3/python3-data-type.html)
* Django-CMS: [Django-CMS](https://www.django-cms.org)
