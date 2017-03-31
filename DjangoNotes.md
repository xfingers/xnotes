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
> Django中网址是写在 urls.py 文件中，用正则表达式对应 views.py 中的一个函数(或者generic类)
### (1) 新建一个项目(project), 名称为 mysite
```
django-admin startproject mysite
```
**备注**：
1. 如果 django-admin 不行，请用 django-admin.py
2. 如果是在Linux是用源码安装的，或者用 pip 安装的，也是用  django-admin.py 命令
运行后,如果成功的话, 我们会看到如下的目录样式   (没有成功的请参见环境搭建一节)：
```
mysite
├── manage.py
└── mysite
    ├── __init__.py
    ├── settings.py
    ├── urls.py
    └── wsgi.py
```
> 执行命令后，新建了一个 mysite 目录，其中还有一个 mysite 目录，这个子目录 mysite 中是一些项目的设置 settings.py 文件，总的urls配置文件 urls.py 以及部署服务器时用到的 wsgi.py 文件， __init__.py 是python包的目录结构必须的，与调用有关。
进入外层那个 mysite 目录下(不是mysite中的mysite目录)

### (2) 新建一个应用(app), 名称叫 learn
```
python manage.py startapp learn # learn 是一个app的名称
```
可以看到mysite中多个一个 learn 文件夹，其中有以下文件。
```
learn/
├── __init__.py
├── admin.py
├── models.py
├── tests.py
└── views.py
```
> 注：Django 1.8.x 以上的，还有一个 migrations 文件夹。Django 1.9.x 还会在 Django 1.8 的基础上多出一个 apps.py 文件。但是这些都与本文无关。
把我们新定义的app加到settings.py中的INSTALL_APPS中
修改 mysite/mysite/settings.py

```
INSTALLED_APPS = (
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
 
    'learn',
)
```
**备注**:这一步是干什么呢? 新建的 app 如果不加到 INSTALL_APPS 中的话, django 就不能自动找到app中的模板文件(app-name/templates/下的文件)和静态文件(app-name/static/中的文件) , 后面你会学习到它们分别用来干什么.

### (3) 定义视图函数（访问页面时的内容）
在learn这个目录中,把views.py打开,修改其中的源代码,改成下面的
```
#coding:utf-8
from django.http import HttpResponse
 
def index(request):
    return HttpResponse(u"欢迎光临 产品草堂!")
```
第一行是声明编码为utf-8, 因为我们在代码中用到了中文,如果不声明就报错.

第二行引入HttpResponse，它是用来向网页返回内容的，就像Python中的 print 一样，只不过 HttpResponse 是把内容显示到网页上。

我们定义了一个index()函数，第一个参数必须是 request，与网页发来的请求有关，request 变量里面包含get或post的内容，用户浏览器，系统等信息在里面（后面会讲，先了解一下就可以）。
函数返回了一个 HttpResponse 对象，可以经过一些处理，最终显示几个字到网页上。
那问题来了，我们访问什么网址才能看到刚才写的这个函数呢？怎么让网址和函数关联起来呢？

### (4) 定义视图函数相关的URL(网址)  （即规定 访问什么网址对应什么内容）
打开 mysite/mysite/urls.py 这个文件, 修改其中的代码:
由于 Django 版本对 urls.py 进行了一些更改：
Django 1.7.x 及以下的同学可能看到的是这样的：
```
from django.conf.urls import patterns, include, url
 
from django.contrib import admin
admin.autodiscover()
 
urlpatterns = patterns('',
    url(r'^$', 'learn.views.index'),  # new
    # url(r'^blog/', include('blog.urls')),
 
    url(r'^admin/', include(admin.site.urls)),
)
```
Django 1.8.x及以上，Django 官方鼓励（或说要求）先引入，再使用：
```
from django.conf.urls import url
from django.contrib import admin
from learn import views as learn_views  # new
 
urlpatterns = [
    url(r'^$', learn_views.index),  # new
    url(r'^admin/', admin.site.urls),
]
```
以上都修改并保存后,我们来看一下效果!

在终端上运行 python manage.py runserver 我们会看到类似下面的信息:
```
$ python manage.py runserver
 
Performing system checks...
 
System check identified no issues (0 silenced).
 
You have unapplied migrations; your app may not work properly until they are applied.
Run 'python manage.py migrate' to apply them.
 
December 22, 2015 - 11:57:33
Django version 1.9, using settings 'mysite.settings'
Starting development server at http://127.0.0.1:8000/
Quit the server with CONTROL-C.
```
我们打开浏览器,访问 http://127.0.0.1:8000/
**注意**：如果是在另一台电脑上访问要用 python manage.py ip:port 的形式，比如监听所有ip:
```
python manage.py runserver 0.0.0.0:8000
 
监听机器上所有ip 8000端口，访问时用电脑的ip代替 127.0.0.1
```
Django中的 urls.py 用的是正则进行匹配的，如果不熟悉，您可以学习正则表达式以及Python正则表达式。

### (5) 在网页上做加减法
#### 采用 /add/?a=4&b=5 这样GET方法进行
```
django-admin.py startproject calc_views
cd calc
python manage.py startapp calc
```
自动生成目录大致如下（因不同的 Django 版本有一些差异，如果差异与这篇文章相关，我会主动提出来，没有说的，暂时可以忽略他们之间的差异，后面的教程也是这样做）：
```
calc_views/
├── calc
│   ├── __init__.py
│   ├── admin.py
│   ├── models.py
│   ├── tests.py
│   └── views.py
├── manage.py
└── calc_views
    ├── __init__.py
    ├── settings.py
    ├── urls.py
    └── wsgi.py
```
修改一下 calc/views.py文件
```
from django.shortcuts import render
from django.http import HttpResponse
 
def add(request):
    a = request.GET['a']
    b = request.GET['b']
    c = int(a)+int(b)
    return HttpResponse(str(c))
```
**注**：request.GET 类似于一个字典，更好的办法是用 request.GET.get('a', 0) 当没有传递 a 的时候默认 a 为 0
接着修改 calc_views/urls.py 文件，添加一个网址来对应我们刚才新建的视图函数。

Django 1.7.x 及以下的同学可能看到的是这样的：
```
from django.conf.urls import patterns, include, url
 
from django.contrib import admin
admin.autodiscover()
 
urlpatterns = patterns('',
    # Examples:
    url(r'^add/$', 'calc.views.add', name='add'), # 注意修改了这一行
    # url(r'^blog/', include('blog.urls')),
 
    url(r'^admin/', include(admin.site.urls)),
)
```
Django 1.8.x及以上，Django 官方鼓励（或说要求）先引入，再使用。
```
from django.conf.urls import url
from django.contrib import admin
from calc import views as calc_views
 
 
urlpatterns = [
    url(r'^add/$', calc_views.add, name='add'),  # 注意修改了这一行
    url(r'^admin/', admin.site.urls),
]
```
注意：低版本的 Django 也可以先引入，再使用

打开开发服务器并访问
```
python manage.py runserver
# 如果提示 Error: That port is already in use.在后面加上端口号8001,8888等
python manage.py runserver 8001
```
打开网址：http://127.0.0.1:8000/add/ 就可以看到 **MultiValueDictKeyError at /add/**

这是因为我们并没有传值进去，我们在后面加上 ` ?a=4&b=5 ` ，即访问 http://127.0.0.1:8000/add/?a=4&b=5 就可以看到网页上显示一个 9，试着改变一下a和b对应的值试试看？

#### 采用 /add/3/4/ 这样的网址的方式
面介绍的时候就说过 Django 支持优雅的网址
我们接着修改 calc/views.py文件，再新定义一个add2 函数，原有部分不再贴出
```
def add2(request, a, b):
    c = int(a) + int(b)
    return HttpResponse(str(c))
```
接着修改 calc_views/urls.py 文件，再添加一个新的 url
Django 1.7.x 及以下：
```
url(r'^add/(\d+)/(\d+)/$', 'calc.views.add2', name='add2'),
```
Django 1.8.x 及以上：
```
url(r'^add/(\d+)/(\d+)/$', calc_views.add2, name='add2'),
```
可以看到网址中多了 (\d+), 正则表达式中 \d 代表一个数字，+ 代表一个或多个前面的字符，写在一起 \d+ 就是一个或多个数字，用括号括起来的意思是保存为一个子组（更多知识请参见 Python 正则表达式），每一个子组将作为一个参数，被 views.py 中的对应视图函数接收。
再访问 http://127.0.0.1:8000/add/4/5/ 就可以看到和刚才同样的效果，但是这回网址更优雅了

## 05 Django URL name详解
基于上一节的代码来开始这一节的内容。笔记中所有的文件，没有特别说明的，都是以 utf8 格式编码的，请养成这个习惯。

### (1) 打开 calc_views/urls.py
```
from django.conf.urls import url
from django.contrib import admin
from calc import views as calc_views

urlpatterns = [
    url(r'^add/$', calc_views.add, name='add'),
    url(r'^add/(\d+)/(\d+)/$', calc_views.add2, name='add2'),
    url(r'^admin/', admin.site.urls),
]
```
> url(r'^add/$', calc_views.add, name='add'), 这里的 name='add' 是用来干什么的呢？
简单说，name 可以用于在 templates, models, views ……中得到对应的网址，相当于“给网址取了个名字”，只要这个名字不变，网址变了也能通过名字获取到。
为了进一步弄清这个问题，我们先建一个首页的视图和url

### (2) 修改 calc/views.py
```
from django.http import HttpResponse
from django.shortcuts import render
 
 
def index(request):
    return render(request, 'home.html')
 
 
#...此处省去一些代码
```
> render 是渲染模板，不懂先照着打就好。

### (3) 将 'calc' 这个 app 加入到 calc_views/settings.py 中
```
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
 
    'calc',
]
```
这样，使用render的时候，Django 会自动找到 INSTALLED_APPS 中列出的各个 app 下的 templates 中的文件。
> 小提示，DEBUG=True 的时候，Django 还可以自动找到 各 app 下 static 文件夹中的静态文件（js，css，图片等资源）

### (4) 在 calc 这个 app 中新建一个 templates 文件夹，在templates中新建一个 home.html 
文件 calc/templates/home.html 中写入以下内容（保存时用 utf8 编码）
```
<!DOCTYPE html>
<html>
<head>
    <title>自强学堂</title>
</head>
<body>
 
<a href="/add/4/5/">计算 4+5</a>
 
</body>
</html>
```
修改 calc_views/urls.py
```
# ...此处省去一些代码
 
urlpatterns = [
    url(r'^$', calc_views.index, name='home'),
    url(r'^add/$', calc_views.add, name='add'),
    url(r'^add/(\d+)/(\d+)/$', calc_views.add2, name='add2'),
    url(r'^admin/', admin.site.urls),
]
```
运行开发服务器，访问 http://127.0.0.1:8000/ 可以看到结果

计算加法的时候用的是 /add/4/5/ ，后来需求发生变化，比如改成 /4_add_5/，但在网页中，代码中很多地方都写死的 /add/4/5/，比如模板中可能是这么写的 
```
<a href="/add/4/5/">计算 4+5</a>
```
** 如果这样写“死网址”，会使得在改了网址（正则）后，模板（template)，视图(views.py，用以用于跳转)，模型(models.py，可以用用于获取对象对应的地址）用了此网址的，都得进行相应的更改，修改的代价很大，一不小心，有的地方没改过来，就不能用了。**

那么有没有更优雅的方式来解决这个问题呢？当然答案是肯定的。

我们先说一下如何用 Python 代码获取对应的网址（可以用在 views.py，models.py等各种需要转换得到网址的地方）：
我们在终端上输入(推荐安装 ipython, 这样Django会用 ipython的 shell)
```
python manage.py shell
```
```
>>> from django.core.urlresolvers import reverse  # django 1.4.x - django 1.10.x
>>> from django.urls import reverse  # django 1.10.x 新的，更加规范了
 
>>> reverse('add2', args=(4,5))
u'/add/4/5/'
>>> reverse('add2', args=(444,555))
u'/add/444/555/'
```
** reverse 接收 url 中的 name 作为第一个参数 **，我们在代码中就可以通过 reverse() 来获取对应的网址（这个网址可以用来跳转，也可以用来计算相关页面的地址），只要对应的 url 的name不改，就不用改代码中的网址。

在网页模板中也是一样，可以很方便的使用。
```
# 不带参数的：
{% url 'name' %}
# 带参数的：参数可以是变量名
{% url 'name' 参数 %}
 
例如：
<a href="{% url 'add2' 4 5 %}">link</a>
```
上面的代码渲染成最终的页面是
```
<a href="/add/4/5/">link</a>
```
这样就可以通过 {% url 'add2' 4 5 %} 获取到对应的网址 /add/4/5/

当 urls.py 进行更改，前提是不改 name（这个参数设定好后不要轻易改），获取的网址也会动态地跟着变，比如改成：
```
url(r'^new_add/(\d+)/(\d+)/$', calc_views.add2, name='add2'),
```
** 注意看重点 add 变成了 new_add **，但是后面的 name='add2' 没改，这时 {% url 'add2' 4 5 %} 就会渲染对应的网址成 ** /new_add **/4/5/

用在 views.py 或 models.py 等地方的 reverse函数，同样会根据 name 对应的url获取到新的网址。

想要改网址的时候，修改 urls.py 中的正则表达式部分（url 参数第一部分），name 不变的前提下，其它地方都不需要修改。

** 另外，比如用户收藏夹中收藏的URL是旧的，如何让以前的 /add/3/4/自动跳转到现在新的网址呢？ **

要知道Django **不会**帮你做这个，这个需要自己来写一个跳转方法：
具体思路是，在 views.py 写一个跳转的函数：
```
from django.http import HttpResponseRedirect
from django.core.urlresolvers import reverse  # django 1.4.x - django 1.10.x
#  from django.urls import reverse  # new in django 1.10.x
 
def old_add2_redirect(request, a, b):
    return HttpResponseRedirect(
        reverse('add2', args=(a, b))
    )
```
urls.py中：
```
url(r'^add/(\d+)/(\d+)/$', calc_views.old_add2_redirect),
url(r'^new_add/(\d+)/(\d+)/$', calc_views.add2, name='add2'),
```

这样，**假如用户收藏夹中**有 /add/4/5/ ，访问时就会自动跳转到新的 /new_add/4/5/ 了

开始可能觉得直接写网址简单，但是用多了你一定会发现，用“死网址”的方法很糟糕。

## 06 Django 模板(templates)
在前面的几节中我们都是用简单的 django.http.HttpResponse 来把内容显示到网页上，本节将讲解如何使用渲染模板的方法来显示内容。

### (1) 创建一个 zqxt_tmpl 项目，和一个 名称为 learn 的应用
```
django-admin.py startproject zqxt_tmpl
cd zqxt_tmpl
python manage.py startapp learn
```

### (2) 把 learn 加入到 settings.INSTALLED_APPS中
```
INSTALLED_APPS = (
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
 
    'learn',
)
```

### (3) 打开 learn/views.py 写一个首页的视图
```
from django.shortcuts import render
 
 
def home(request):
    return render(request, 'home.html')
```

### (4) 在 learn目录下新建一个 templates 文件夹，里面新建一个 home.html
默认配置下，Django 的模板系统会自动找到app下面的templates文件夹中的模板文件。
目录的结构是这样的：
```
zqxt_tmpl
├── learn
│   ├── __init__.py
│   ├── admin.py
│   ├── migrations
│   │   └── __init__.py
│   ├── models.py
│   ├── templates
│   │   └── home.html
│   ├── tests.py
│   └── views.py
├── manage.py
└── zqxt_tmpl
    ├── __init__.py
    ├── settings.py
    ├── urls.py
    └── wsgi.py
```

### (5) 在 home.html 中写一些内容
```
<!DOCTYPE html>
<html>
<head>
    <title>欢迎光临</title>
</head>
<body>
欢迎光临产品客栈
</body>
</html>
```

### (6) 将视图函数对应到网址，更改 zqxt_tmpl/urls.py
Django 1.7.x 及以下可以这样：
```
from django.conf.urls import include, url
from django.contrib import admin
 
 
urlpatterns = [
    url(r'^$', 'learn.views.home', name='home'),  # new
    # url(r'^blog/', include('blog.urls')),
 
    url(r'^admin/', include(admin.site.urls)),
]
```
Django 1.8.x 及以上：
```
from django.conf.urls import include, url
from django.contrib import admin
from learn import views as learn_views

urlpatterns = [
    url(r'^$', learn_views.home, name='home'),
    url(r'^admin/', include(admin.site.urls)),
]
```
注意：Django 1.10.x 中为
```
url(r'^admin/', admin.site.urls),
```
去掉了 include

### (7) [可选] 创建数据库表
```
python manage.py syncdb
 
# Django 1.9.x 以及上要用
python manage.py migrate
```
创建数据库虽然本节不会用到，但是可以让一些提示消失（提示你要创建数据库之类的）

### (8) 运行开发服务器，看看效果
```
python manage.py runserver
```
> Django 1.10.x 中自己把 urls.py 中对应的地方修改成 (去掉 include)
```
url(r'^admin/', admin.site.urls),
```
> 模板补充知识：网站模板的设计，一般的，我们做网站有一些通用的部分，比如 导航，底部，访问统计代码等等
> nav.html, bottom.html, tongji.html,可以写一个 base.html 来包含这些通用文件（include)
```
<!DOCTYPE html>
<html>
<head>
    <title>{% block title %}默认标题{% endblock %} - 自强学堂</title>
</head>
<body>
 
{% include 'nav.html' %}
 
{% block content %}
<div>这里是默认内容，所有继承自这个模板的，如果不覆盖就显示这里的默认内容。</div>
{% endblock %}
 
{% include 'bottom.html' %}
 
{% include 'tongji.html' %}
 
</body>
</html>
```

> 如果需要，写足够多的 block 以便继承的模板可以重写该部分，include 是包含其它文件的内容，就是把一些网页共用的部分拿出来，重复利用，改动的时候也方便一些，还可以把广告代码放在一个单独的html中，改动也方便一些，在用到的地方include进去。其它的页面继承自 base.html 就好了，继承后的模板也可以在 block 块中 include 其它的模板文件。比如我们的首页 home.html，继承或者说扩展(extends)原来的 base.html，可以简单这样写，重写部分代码（默认值的那一部分不用改）
```
{% extends 'base.html' %}
 
{% block title %}欢迎光临首页{% endblock %}
 
{% block content %}
{% include 'ad.html' %}
这里是首页，欢迎光临
{% endblock %}
```

> ** 注意：模板一般放在app下的templates中，Django会自动去这个文件夹中找。但 假如我们每个app的templates中都有一个 index.html，当我们在views.py中使用的时候，直接写一个 render(request, 'index.html')，Django 能不能找到当前 app 的 templates 文件夹中的 index.html 文件夹呢?（答案是不一定能，有可能找错）**

> ** Django 模板查找机制： Django 查找模板的过程是在每个 app 的 templates 文件夹中找（而不只是当前 app 中的代码只在当前的 app 的 templates 文件夹中找）。各个 app 的 templates 形成一个文件夹列表，Django 遍历这个列表，一个个文件夹进行查找，当在某一个文件夹找到的时候就停止，所有的都遍历完了还找不到指定的模板的时候就是 Template Not Found （过程类似于Python找包）。这样设计有利当然也有弊，有利是的地方是一个app可以用另一个app的模板文件，弊是有可能会找错了。所以我们使用的时候在 templates 中建立一个 app 同名的文件夹，这样就好了。这就需要把每个app中的 templates 文件夹中再建一个 app 的名称，仅和该app相关的模板放在 app/templates/app/ 目录下面。

例如：项目 zqxt 有两个 app，分别为 tutorial 和 tryit
```
zqxt
├── tutorial
│   ├── __init__.py
│   ├── admin.py
│   ├── models.py
│   ├── templates
│   │   └── tutorial
│   │       ├── index.html
│   │       └── search.html
│   ├── tests.py
│   └── views.py
├── tryit
│   ├── __init__.py
│   ├── admin.py
│   ├── models.py
│   ├── templates
│   │   └── tryit
│   │       ├── index.html
│   │       └── poll.html
│   ├── tests.py
│   └── views.py
├── manage.py
└── zqxt
    ├── __init__.py
    ├── settings.py
    ├── urls.py
    └── wsgi.py
```

这样，使用的时候，模板就是 "tutorial/index.html" 和 "tryit/index.html" 这样有app作为名称的一部分，就不会混淆。

模板中的一些循环，条件判断，标签，过滤器等使用请看下一节的内容。
***

### (9) 模版进阶
> 本节主要讲 Django模板中的循环，条件判断，常用的标签，过滤器的使用。
> 1. 列表，字典，类的实例的使用
> 2. 循环：迭代显示列表，字典等中的内容
> 3. 条件判断：判断是否显示该内容，比如判断是手机访问，还是电脑访问，给出不一样的代码。
> 4. 标签：for，if 这样的功能都是标签。
> 5. 过滤器：管道符号后面的功能，比如 {{ var|length }}，求变量长度的 length 就是一个过滤器。

如果需要将一个或多个变量共享给多个网页或者所有网页使用，比如在网页上显示来访者的IP，这个可以使用 Django 上下文渲染器 来做。

#### 实例1 : 显示一个基本的字符串在网页上
views.py
```
# -*- coding: utf-8 -*-
from django.shortcuts import render
 
 
def home(request):
    string = u"Github是全球最大的男性同性交友平台，可用它来进行一切开源在线协同管理！"
    return render(request, 'home.html', {'string': string})
```
在视图中我们传递了一个字符串名称是 string 到模板 home.html，在模板中这样使用它：
home.html
```
{{ string }}
```

#### 实例2 : 基本的 for 循环 和 List内容的显示
views.py
```
def home(request):
    TutorialList = ["HTML", "CSS", "jQuery", "Python", "Django"]
    return render(request, 'home.html', {'TutorialList': TutorialList})
```
在视图中我们传递了一个List到模板 home.html，在模板中这样使用它：

home.html
```
# 教程列表：
{% for i in TutorialList %}
{{ i }}
{% endfor %}
```
for 循环要有一个结束标记，上面的代码假如我们对应的是首页的网址（自己修改urls.py）
**简单总结一下**：一般的变量之类的用 {{ }}（变量），功能类的，比如循环，条件判断是用 {%  %}（标签）

#### 实例3 : 显示字典中内容：
views.py
```
def home(request):
    info_dict = {'site': u'产品客栈', 'content': u'各种产品经理干货分享'}
    return render(request, 'home.html', {'info_dict': info_dict})
```
home.html
```
站点：{{ info_dict.site }} 内容：{{ info_dict.content }}
```
在模板中取字典的键是用点info_dict.site，而不是Python中的 info_dict['site']

还可以这样遍历字典：
```
{% for key, value in info_dict.items %}
    {{ key }}: {{ value }}
{% endfor %}
```
其实就是遍历这样一个 ** List:  [('content', u'产品客栈'), ('site', u'各种产品经理干货分享')] **

#### 实例4 : 在模板进行 条件判断和 for 循环的详细操作：
views.py
```
def home(request):
    List = map(str, range(100))# 一个长度为100的 List
    return render(request, 'home.html', {'List': List})
```
假如我们想用逗号将这些元素连接起来：

home.html
```
{% for item in List %}
    {{ item }}, 
{% endfor %}
```
效果略

我们会发现最后一个元素后面也有一个逗号，这样肯定不爽，如果判断是不是遍历到了最后一个元素了呢？

用变量 forloop.last 这个变量，如果是最后一项其为真，否则为假，更改如下：

```
{% for item in List %}
    {{ item }}{% if not forloop.last %},{% endif %} 
{% endfor %}
```

** 在for循环中还有很多有用的东西，如下：**
| 变量 | 描述 |
|:-:|:-|
| forloop.counter | 索引从 1 开始算 |
| forloop.counter0 | 索引从 0 开始算 |
| forloop.revcounter | 索引从最大长度到 1 |
| forloop.revcounter0 | 索引从最大长度到 0 |
| forloop.first | 当遍历的元素为第一项时为真 |
| forloop.last | 当遍历的元素为最后一项时为真 |
| forloop.parentloop | 用在嵌套的 for 循环中， 获取上一层 for 循环的 forloop|

当列表中可能为空值时用 for  empty
```
<ul>
{% for athlete in athlete_list %}
    <li>{{ athlete.name }}</li>
{% empty %}
    <li>抱歉，列表为空</li>
{% endfor %}
</ul>
```

### 实例5 : 模板上得到视图对应的网址：
```
# views.py
def add(request, a, b):
    c = int(a) + int(b)
    return HttpResponse(str(c))
 
 
# urls.py
urlpatterns = patterns('',
    url(r'^add/(\d+)/(\d+)/$', 'app.views.add', name='add'),
)
 
 
# template html
{% url 'add' 4 5 %}
```
这样网址上就会显示出：/add/4/5/ 这个网址，假如我们以后修改 urls.py 中的 
```
r'^add/(\d+)/(\d+)/$'
```
这一部分，改成另的，比如：
```
r'^jiafa/(\d+)/(\d+)/$'
```
这样，我们不需要再次修改模板，当再次访问的时候，网址会自动变成 /jiafa/4/5/
> **注意**：如果是 Django 1.4 的话，需要在模板开头加上 {% load url from future %} (如果有 extends 的话，加在 extends 下面）
还可以使用 as 语句将内容取别名（相当于定义一个变量），多次使用（但视图名称到网址转换只进行了一次）
```
{% url 'some-url-name' arg arg2 as the_url %}
 
<a href="{{ the_url }}">链接到：{{ the_url }}</a>
```

### 实例6 : 模板中的逻辑操作：
> ==, !=, >=, <=, >, < 这些比较都可以在模板中使用，比如：
```
{% if var >= 90 %}
成绩优秀，自强学堂你没少去吧！学得不错
{% elif var >= 80 %}
成绩良好
{% elif var >= 70 %}
成绩一般
{% elif var >= 60 %}
需要努力
{% else %}
不及格啊，大哥！多去自强学堂学习啊！
{% endif %}
```
** and, or, not, in, not in 也可以在模板中使用 **

假如我们判断 num 是不是在 0 到 100 之间：
```
{% if num <= 100 and num >= 0 %}
num在0到100之间
{% else %}
数值不在范围之内！
{% endif %}
```
假如我们判断 'ziqiangxuetang' 在不在一个列表变量 List 中：
```
{% if 'ziqiangxuetang' in List %}
自强学堂在名单中
{% endif %}
```

### 实例7 : 模板中 获取当前网址，当前用户等：
如果不是在 views.py 中用的 render 函数，是 render_to_response 的话，需要将 request 加入到 上下文渲染器

Django 1.8 及以后 修改 settings.py 
```
TEMPLATES = [
    {
        'BACKEND': 'django.template.backends.django.DjangoTemplates',
        'DIRS': [],
        'APP_DIRS': True,
        'OPTIONS': {
            'context_processors': [
                ...
                'django.template.context_processors.request',
                ...
            ],
        },
    },
]
```
Django 1.7 及以前 修改 settings.py：

如果没有 ** TEMPLATE_CONTEXT_PROCESSORS ** 请自行添加下列默认值：
```
TEMPLATE_CONTEXT_PROCESSORS = (
    "django.contrib.auth.context_processors.auth",
    "django.core.context_processors.debug",
    "django.core.context_processors.i18n",
    "django.core.context_processors.media",
    "django.core.context_processors.static",
    "django.core.context_processors.tz",
    "django.contrib.messages.context_processors.messages",
)
```
然后再加上 ** django.core.context_processors.request **
```
TEMPLATE_CONTEXT_PROCESSORS = (
    ...
    "django.core.context_processors.request",
    ...
)
```
> 然后在 模板中我们就可以用 request 了。一般情况下，** 推荐用 render 而不是用 render_to_response **

#### (7.1) 获取当前用户：
```
{{ request.user }}
```
如果登陆就显示内容，不登陆就不显示内容：
```
{% if request.user.is_authenticated %}
    {{ request.user.username }}，您好！
{% else %}
    请登陆，这里放登陆链接
{% endif %}
```

#### (7.2.1)  获取当前网址：
```
{{ request.path }}
```

#### (7.2.2) 获取当前 GET 参数：
```
{{ request.GET.urlencode }}
```

#### (7.2.3) 合并到一起用的一个例子：
```
<a href="{{ request.path }}?{{ request.GET.urlencode }}&delete=1">当前网址加参数 delete</a>
```
比如我们可以判断 delete 参数是不是 1 来删除当前的页面内容。

完整的内容参考官方文档：https://docs.djangoproject.com/en/1.10/ref/templates/builtins/

## 07 Django 模型(数据库)
> Django 模型是与数据库相关的，与数据库相关的代码一般写在 models.py 中，Django 支持 sqlite3, MySQL, PostgreSQL等数据库，只需要在settings.py中配置即可，不用更改models.py中的代码，丰富的API极大的方便了使用。
按步骤开始操作:
```
django-admin.py startproject learn_models # 新建一个项目
cd learn_models # 进入到该项目的文件夹
django-admin.py startapp people # 新建一个 people 应用（app)
```
补充：新建app也可以用 python manage.py startapp people, 需要指出的是，django-admin.py 是安装Django后多出的一个命令，并不是指一个 django-admin.py 脚本在当前目录下。

那么project和app什么关系呢，一个项目一般包含多个应用，一个应用也可以用在多个项目中。

将我们新建的应用（people）添加到 settings.py 中的 INSTALLED_APPS中，也就是告诉Django有这么一个应用。
```
INSTALLED_APPS = (
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
 
    'people',
)
```
打开 people/models.py 文件，修改其中的代码如下：
```
from django.db import models
 
class Person(models.Model):
    name = models.CharField(max_length=30)
    age = models.IntegerField()
```
我们新建了一个Person类，继承自models.Model, 一个人有姓名和年龄。这里用到了两种Field，更多Field类型可以参考教程最后的链接。

我们来** 同步一下数据库（我们使用默认的数据库 SQLite3，无需配置）**
```
python manage.py syncdb # 进入 manage.py 所在的那个文件夹下输入这个命令
 
# 注意：Django 1.7 及以上的版本需要用以下命令
python manage.py makemigrations
python manage.py migrate
```
我们会看到，Django生成了一系列的表，也生成了我们新建的people_person这个表，那么如何使用这个表呢？

Django提供了丰富的API, 下面演示如何使用它。
```
$ python manage.py shell
 
>>> from people.models import Person
>>> Person.objects.create(name="WeizhongTu", age=24)
<Person: Person object>
>>>
```
我们新建了一个用户WeizhongTu 那么如何从数据库是查询到它呢？
```
>>> Person.objects.get(name="WeizhongTu")
<Person: Person object>
>>>
```

我们用了一个 .objects.get() 方法查询出来符合条件的对象，但是大家注意到了没有，查询结果中显示 < Person: **Person object** >，这里并没有显示出与WeizhongTu的相关信息，如果用户多了就无法知道查询出来的到底是谁，查询结果是否正确，我们重新修改一下 people/models.py

> name 和 age 等字段中不能有 \_\_ （双下划线，因为在Django QuerySet API中有特殊含义（用于关系，包含，不区分大小写，以什么开头或结尾，日期的大于小于，正则等）

> 也不能有Python中的关键字，name 是合法的，student_name 也合法，但是student\_\_name不合法，try, class, continue 也不合法，因为它是Python的关键字( ** import keyword; print(keyword.kwlist) 可以打出所有的关键字 ** )
```
from django.db import models

class Person(models.Model):
    name = models.CharField(max_length=30)
    age = models.IntegerField()
     
    def __unicode__(self):
    # 在Python3中使用 def __str__(self)
        return self.name
```
按CTRL + C退出当前的Python shell, 重复上面的操作。显示效果略。
- **新建一个对象的方法有以下几种：**
> 1. Person.objects.create(name=name,age=age)
> 2. p = Person(name="WZ", age=23)
     p.save()
> 3. p = Person(name="TWZ")
     p.age = 23
     p.save()
> 4. Person.objects.get_or_create(name="WZT", age=23) # 这种方法是防止重复很好的方法，但是速度要相对慢些，返回一个元组，第一个为Person对象，第二个为True或False, 新建时返回的是True, 已经存在时返回False.

- ** 获取对象有以下方法：**

> 1. Person.objects.all()
> 2. Person.objects.all()[:10] 切片操作，获取10个人，不支持负索引，切片可以节约内存
> 3. Person.objects.get(name=name)
     get是用来获取一个对象的，如果需要获取满足条件的一些人，就要用到filter
> 4. Person.objects.filter(name="abc") # 等于
     Person.objects.filter(name\_\_exact="abc") 名称严格等于 "abc" 的人
> 5. Person.objects.filter(name\_\_iexact="abc") # 名称为 abc 但是不区分大小写，可以找到 ABC, Abc, aBC，这些都符合条件
> 6. Person.objects.filter(name\_\_contains="abc") # 名称中包含 "abc"的人
> 7. Person.objects.filter(name\_\_icontains="abc") #名称中包含 "abc"，且abc不区分大小写
> 8. Person.objects.filter(name\_\_regex="^abc") # 正则表达式查询
> 9. Person.objects.filter(name\_\_iregex="^abc")# 正则表达式不区分大小写
**filter是找出满足条件的，当然也有排除符合某条件的 **
> 10. Person.objects.exclude(name\_\_contains="WZ") # 排除包含 WZ 的Person对象
> 11. Person.objects.filter(name\_\_contains="abc").exclude(age=23) # 找出名称含有abc, 但是排除年龄是23岁的

参考文档：

Django models 官方教程: https://docs.djangoproject.com/en/dev/topics/db/models/

Fields相关官方文档：https://docs.djangoproject.com/en/dev/ref/models/fields/

## 08 Django 自定义 Field
Django 的官方提供了很多的 Field，但是有时候还是不能满足我们的需求，不过Django提供了自定义 Field 的方法：

提示：如果现在用不到可以跳过这一节，不影响后面的学习，等用到的时候再来学习不迟。

来一个简单的例子吧。

1. 减少文本的长度，保存数据的时候压缩，读取的时候解压缩，如果发现压缩后更长，就用原文本直接存储：

Django 1.7 以下
```
from django.db import models
 
class CompressedTextField(models.TextField):
    """    model Fields for storing text in a compressed format (bz2 by default)    """
    __metaclass__ = models.SubfieldBase
 
    def to_python(self, value):
        if not value:
            return value
 
        try:
            return value.decode('base64').decode('bz2').decode('utf-8')
        except Exception:
            return value
 
    def get_prep_value(self, value):
        if not value:
            return value
 
        try:
            value.decode('base64')
            return value
        except Exception:
            try:
                tmp = value.encode('utf-8').encode('bz2').encode('base64')
            except Exception:
                return value
            else:
                if len(tmp) > len(value):
                    return value
 
                return tmp
```
** to_python 函数用于转化数据库中的字符到 Python的变量， get_prep_value 用于将Python变量处理后(此处为压缩）保存到数据库，使用和Django自带的 Field 一样。 **

Django 1.8 以上版本，可以用
```
#coding:utf-8
from django.db import models
 
 
class CompressedTextField(models.TextField):
    """
    model Fields for storing text in a compressed format (bz2 by default)
    """
 
    def from_db_value(self, value, expression, connection, context):
        if not value:
            return value
        try:
            return value.decode('base64').decode('bz2').decode('utf-8')
        except Exception:
            return value
 
    def to_python(self, value):
        if not value:
            return value
        try:
            return value.decode('base64').decode('bz2').decode('utf-8')
        except Exception:
            return value
 
    def get_prep_value(self, value):
        if not value:
            return value
        try:
            value.decode('base64')
            return value
        except Exception:
            try:
                return value.encode('utf-8').encode('bz2').encode('base64')
            except Exception:
                return value
```
Django 1.8及以上版本中，from_db_value ** 函数用于转化数据库中的字符到 Python的变量。 **

2. 比如我们想保存一个 列表到数据库中，在读取用的时候要是 Python的列表的形式，我们来自己写一个 ListField：

这个ListField继承自 TextField，代码如下：
```
from django.db import models
import ast
 
class ListField(models.TextField):
    __metaclass__ = models.SubfieldBase
    description = "Stores a python list"
 
    def __init__(self, *args, **kwargs):
        super(ListField, self).__init__(*args, **kwargs)
 
    def to_python(self, value):
        if not value:
            value = []
 
        if isinstance(value, list):
            return value
 
        return ast.literal_eval(value)
 
    def get_prep_value(self, value):
        if value is None:
            return value
 
        return unicode(value) # use str(value) in Python 3
 
    def value_to_string(self, obj):
        value = self._get_val_from_obj(obj)
        return self.get_db_prep_value(value)
```
使用它很简单，首先导入 ListField，像自带的 Field 一样使用：
```
class Article(models.Model):
    labels = ListField()
```
在终端上尝试（运行 python manage.py shell 进入）：
```
>>> from app.models import Article
>>> d = Article()
>>> d.labels
[]
>>> d.labels = ["Python", "Django"]
>>> d.labels
["Python", "Django"]
```
进入项目目录，输入 python manage.py shell 搞起
```
>>> from blog.models import Article
 
>>> a = Article()
>>> a.labels.append('Django')
>>> a.labels.append('custom fields')
 
>>> a.labels
['Django', 'custom fields']
 
>>> type(a.labels)
<type 'list'>
 
>>> a.content = u'我正在写一篇关于自定义Django Fields的教程'
>>> a.save()
```
参考网址：

https://djangosnippets.org/snippets/2014/

https://docs.djangoproject.com/en/dev/howto/custom-model-fields/

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
