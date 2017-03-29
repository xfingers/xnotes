# Django 笔记 - 传说中的闲人
# 基础
## 01 Django 概述
Python下有许多款不同的 Web 框架。Django 是重量级选手中最有代表性的一位。许多成功的网站和 APP 都基于 Django。 Django 是由 Python 开发的一个免费的开源网站框架，由 Python 写成，可以用于快速搭建高性能、优雅的网站！Django 遵守 BSD 版权，初次发布于2005年7月, 并于2008年9月发布了第一个正式版本1.0 。
Django采用了MVC的软件设计模式，即模型M，视图V和控制器C。
Django 中提供了开发网站经常用到的模块，常见的代码都为你写好了，通过减少重复的代码，Django 使你能够专注于 web 应用上有 趣的关键性的东西。为了达到这个目标，Django 提供了通用Web开发模式的高度抽象，提供了频繁进行的编程作业的快速解决方法，以及为“如何解决问题”提供了清晰明了的约定。Django的理念是DRY(Don't Repeat Yourself)来鼓励快速开发！

### 学Django需要什么基础
- Django是 python 语言写的一个Web框架包，所以你得知道一些 Python 基础知识。
- 其次你最好有一些做网站的经验，懂一些网页 HTML, CSS, JavaScript 的知识。
没有经验也没有关系，慢慢来就好了，你一定可以学会，Django 很简单！

### Django 特点
- 强大的数据库功能：用python的类继承，几行代码就可以拥有一个丰富，动态的数据库操作接口（API），如果需要你也能执行SQL语句
- 自带的强大的后台功能：几行简单的代码就让你的网站拥有一个强大的后台，轻松管理你的内容！
- 优雅的网址：用正则匹配网址，传递到对应函数，随意定义，如你所想！
- 模板系统：强大，易扩展的模板系统，设计简易，代码，样式分开设计，更容易管理。
- 缓存系统：与memcached或其它的缓存系统联用，更出色的表现，更快的加载速度。
- 国际化：完全支持多语言应用，允许你定义翻译的字符，轻松翻译成不同国家的语言。

### Django 全貌
- urls.py : 网址入口，关联到对应的views.py中的一个函数（或者generic类），访问网址就对应一个函数。
- views.py : 处理用户发出的请求，从urls.py中对应过来, 通过渲染templates中的网页可以将显示内容，比如登陆后的用户名，用户请求的数据，输出到网页。
- models.py : 与数据库操作相关，存入或读取数据时用到这个，当然用不到数据库的时候 你可以不使用。
- forms.py : 表单，用户在浏览器上输入数据提交，对数据的验证工作以及输入框的生成等工作，当然你也可以不使用。
> templates 文件夹: views.py 中的函数渲染templates中的Html模板，得到动态内容的网页，当然可以用缓存来提高速度。
- admin.py : 后台，可以用很少量的代码就拥有一个强大的后台。
- settings.py : Django 的设置，配置文件，比如 DEBUG 的开关，静态文件的位置等。

## 02 Django 环境搭建
### 版本选择

|Django 版本|Python版本| 备注 |
|:-:|:-|:-|
| 1.5.x | 2.6.5, 2.7, 3.2, 3.3 | - |
| 1.6.x | 2.6.X, 2.7.X, 3.2.X, 3.3.X | - |
| 1.7.x | 2.7, 3.2, 3.3,3.4 | 注意：Python 2.6 不支持了 |
| 1.8.x | 2.7, 3.2, 3.3, 3.4, 3.5 | 长期支持版本 LTS |
| 1.9.x | 2.7, 3.4, 3.5 | 不支持 3.3 了 |
| 1.10.x | 2.7, 3.4, 3.5, 3.6| - |

> Django 1.11.x 下一个长期支持版本，将于2017年4月发布

一般来说，选择长期支持版本比较好。使用最新版本的问题就是，可能要用到的一些第三方插件没有及时更新，无法正常使用这些三方包。
当然如果需要新版本的功能也可以使用新版本，毕竟 Django 1.9 以后admin界面还是更漂亮些 

### 安装 Django
> 注意：以下方法中任何一种方法安装都可，不用每个都试一次。另外 建议自行安装 ipython，这样在用起来会爽很多。进入终端的时候输入 ipython 可以有提示。当然也可以选择用 bpython
#### (1) 用pip来安装
- 先安装 pip（最简单的办法就是安装python3.6，里面已经集成了pip。）
A. Ubuntu：
```
sudo apt-get install python-pip
```
B. Fedora
```
yum install python-pip
```
C. Linux, Mac OSX, Windows 下都可以用[get-pip.py](https://pip.pypa.io/en/latest/installing/) 来安装。
- 利用 pip 安装 Django
```
(sudo) pip install Django
或者
(sudo) pip install Django==1.10.6
```
如果想升级 pip 可以用：
```
(sudo) pip install --upgrade pip
```
#### (2) 下载源码安装:https://www.djangoproject.com/download/

如果是源码包，比如 django-1.10.6.tar.gz

- Linux 或 Mac 下
```
tar -xvf django-1.10.6.tar.gz
cd django-1.8.16
(sudo) python setup.py install
```

- Windows 下

直接用解压软件解压，然后到命令行（XP/Win7/Win10点击开始，在下面的那个输入框中输入 cmd, 回车运行)
比如在 D:\django-1.10.6\  这个文件夹下
```
cd D:
cd django-1.10.6
python setup.py install
```
#### (3) Linux 用自带源进行安装(不推荐)

- ubuntu 下安装 Django
```
sudo apt-get install python-django -y
```
- Fedora 下安装用 yum
```
yum install python-django
```

**注意**：自带源安装的 Django 一般版本比较旧，而用 pip 可以安装最新的版本。
### 检查是否安装成功
终端上输入 python ,点击 Enter，进行 python 环境
```
D:\>python
Python 3.6.0 (v3.6.0:41df79263a11, Dec 23 2016, 08:06:12) [MSC v.1900 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.
>>> import django
>>> django.VERSION
(1, 10, 6, "final", 0)
>>> django.get_version()
"1.10.6"
>>>
```
如果运行后看到版本号，就证明安装成功了

### 搭建多个互不干扰的开发环境(可选)
有的时候会发现，一个电脑上有多个项目，一个依赖 Django 1.8，另一个比较旧的项目又要用 Django 1.5，这时候怎么办呢？
我们需要一个依赖包管理的工具来处理不同的环境。
如果不想搭建这个环境，只想用某一个版本的 Django 也可以，但是推荐学习此内容！
##### (1) 环境搭建
开发会用 virtualenv 来管理多个开发环境，virtualenvwrapper 使得 virtualenv 变得更好用

```
# 安装:
(sudo) pip install virtualenv virtualenvwrapper
```

**Linux/Mac OSX 下** ：

修改~/.bash_profile或其它环境变量相关文件(如 .bashrc 或用 ZSH 之后的 .zshrc)，添加以下语句

```
export WORKON_HOME=$HOME/.virtualenvs
export PROJECT_HOME=$HOME/workspace
source /usr/local/bin/virtualenvwrapper.sh
```

修改后使之立即生效(也可以重启终端使之生效) ：

```
source ~/.bash_profile
```

**Windows 下** ：

```
pip install virtualenvwrapper-win
```

> 可选 : Windows 下默认虚拟环境是放在用户名下面的 Envs 中的，与桌面，我的文档，下载等文件夹在一块的。更改方法：计算机，属性，高级系统设置，环境变量。

##### (2) 使用方法

- mkvirtualenv djdemo：创建运行环境 djdemo
- workon djdemo: 工作在 djdemo 环境 或 从其它环境切换到 djdemo 环境
- deactivate: 退出终端环境

其他的：

- rmvirtualenv ENV：删除运行环境ENV
- mkproject mic：创建 mic 项目和运行环境 mic
- mktmpenv：创建临时运行环境
- lsvirtualenv: 列出可用的运行环境
- lssitepackages: 列出当前环境安装了的包

创建的环境是独立的，互不干扰，无需 sudo 权限即可使用 pip 来进行包的管理。

## 03 Django 基本命令
> 本节主要是一些django最基本的命令，需要多多练习。打开 Linux 或 MacOS 的 Terminal （终端）直接在 终端中输入这些命令（不是 python 的 shell中）。如果是 windows 用 cmd（开始 搜索 cmd 或者 快捷键 win + R，输入 cmd) 直接在 cmd 上操作。

### 新建一个 django project
```
$: django-admin.py startproject project-name
# 特别是在 windows 上，如果报错，尝试用 django-admin 代替 django-admin.py 试试
```
> 一个 project 为一个项目，project-name 项目名称，改成你自己的，要符合Python 的变量命名规则（以下划线或字母开头）

### 新建 app
```
python manage.py startapp app-name
或 
django-admin.py startapp app-name
```
> 一般一个项目有多个app, 当然通用的app也可以在多个项目中使用。

### 同步数据库
```
python manage.py syncdb
 
# 注意：Django 1.7.1及以上的版本需要用以下命令
python manage.py makemigrations
python manage.py migrate
```
> 这种方法可以创建表，当你在models.py中新增了类时，运行它就可以自动在数据库中创建表了，不用手动创建。
**备注**：对已有的 models 进行修改，Django 1.7之前的版本的Django都是无法自动更改表结构的，不过有第三方工具 south。

### 使用开发服务器
开发服务器，即开发时使用，一般修改代码后会自动重启，方便调试和开发，但是由于性能问题，建议只用来测试，不要用在生产环境。
```
python manage.py runserver
 
# 当提示端口被占用的时候，可以用其它端口：
python manage.py runserver 8001
python manage.py runserver 9999
（当然也可以kill掉占用端口的进程）
 
# 监听所有可用 ip （电脑可能有一个或多个内网ip，一个或多个外网ip，即有多个ip地址）
python manage.py runserver 0.0.0.0:8000
# 如果是外网或者局域网电脑上可以用其它电脑查看开发服务器
# 访问对应的 ip加端口，比如 http://172.16.20.2:8000
```

### 清空数据库
```
python manage.py flush
```
> 此命令会询问是 yes 还是 no, 选择 yes 会把数据全部清空掉，只留下空表。

### 创建超级管理员
```
python manage.py createsuperuser
 
# 按照提示输入用户名和对应的密码就好了邮箱可以留空，用户名和密码必填
 
# 修改 用户密码可以用：
python manage.py changepassword username
```

### 导出数据 导入数据
```
python manage.py dumpdata appname > appname.json
python manage.py loaddata appname.json
```

### Django 项目环境终端
```
python manage.py shell
```
如果你安装了 bpython 或 ipython 会自动用它们的界面，推荐安装 ipython。
这个命令和 直接运行 python 或 ipython 进入 shell 的区别是：你可以在这个 shell 里面调用当前项目的 models.py 中的 API，对于操作数据，还有一些小测试非常方便。

### 数据库命令行
```
python manage.py dbshell
```
Django 会自动进入在settings.py中设置的数据库，如果是 MySQL 或 postgreSQL,会要求输入数据库用户密码。
在这个终端可以执行数据库的SQL语句。如果您对SQL比较熟悉，可能喜欢这种方式。

### 更多命令
> 终端上输入 python manage.py 可以看到详细的列表，在忘记子名称的时候特别有用。
更详细的介绍，点击对应版本去官网查看：[1.10](https://docs.djangoproject.com/en/1.10/ref/django-admin/)



## 04 Django 视图与网址
## 05 Django URL name详解
## 06 Django 模板(templates)
## 07 Django 模型(数据库)
## 08 Django 自定义 Field
## 09 Django 数据表更改
## 10 Django QuerySet API
## 11 Django 后台
## 12 Django 表单
## 13 Django 配置
## 14 Django 静态文件
## 15 Django 部署(Apache)
## 16 Django 部署(Nginx)
## 17 Django 发送邮件
***
# 中级
## 18 Django 数据导入
## 19 Django 数据迁移
## 20 Django 多数据库联用
## 21 Django 用户注册系统
## 22 Django 缓存系统
## 23 Django 生成静态网页
## 24 Django 安全
## 25 Django 国际化
## 26 Django session
## 27 Django 传递数据给JS
## 28 Django Ajax
## 29 Django Ajax CSRF认证
## 30 Django Sitemap站点地图
## 31 Django 只用 Django 数据库
## 32 Django 通用视图
## 33 Django 上下文渲染器
## 34 Django 中间件
## 35 Django 微信接口
## 36 Django 单元测试
***
# 项目实战
## 开发内容管理系统
## 开发ERP
