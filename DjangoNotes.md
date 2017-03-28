# Django 笔记 - 传说中的闲人
# 基础
## 01 Django 概述
Django 是由 Python 开发的一个免费的开源网站框架，可以用于快速搭建高性能、优雅的网站！Django 中提供了开发网站经常用到的模块，常见的代码都为你写好了，通过减少重复的代码，Django 使你能够专注于 web 应用上有 趣的关键性的东西。为了达到这个目标，Django 提供了通用Web开发模式的高度抽象，提供了频繁进行的编程作业的快速解决方法，以及为“如何解决问题”提供了清晰明了的约定。Django的理念是DRY(Don't Repeat Yourself)来鼓励快速开发！

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
> ** templates 文件夹 **: views.py 中的函数渲染templates中的Html模板，得到动态内容的网页，当然可以用缓存来提高速度。
- admin.py : 后台，可以用很少量的代码就拥有一个强大的后台。
- settings.py : Django 的设置，配置文件，比如 DEBUG 的开关，静态文件的位置等。

## 02 Django 环境搭建
### 版本选择
Django 1.5.x 支持 Python 2.6.5 Python 2.7, Python 3.2 和 3.3.
Django 1.6.x 支持 Python 2.6.X, 2.7.X, 3.2.X 和 3.3.X
Django 1.7.x 支持 Python 2.7, 3.2, 3.3, 和 3.4 （注意：Python 2.6 不支持了）
** Django 1.8.x 支持 Python 2.7, 3.2, 3.3, 3.4 和 3.5.  （长期支持版本 LTS) **
Django 1.9.x 支持 Python 2.7, 3.4 和 3.5. 不支持 3.3 了
Django 1.10.x 支持 Python 2.7, 3.4 和 3.5. 
** Django 1.11.x 下一个长期支持版本，将于2017年4月发布 **
一般来说，选择长期支持版本比较好。
使用最新版本的问题就是，可能要用到的一些第三方插件没有及时更新，无法正常使用这些三方包。
当然如果需要新版本的功能也可以使用新版本，毕竟 Django 1.9 以后admin界面还是更漂亮些 
### 安装 Django

## 03 Django 基本命令
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
