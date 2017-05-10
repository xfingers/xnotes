# HTML 笔记 - 传说中的闲人

## chapter01 HTML 教程

> 超文本标记语言（英语：HyperText Markup Language，简称：HTML）是一种用于创建网页的标准标记语言。您可以使用 HTML 来建立自己的 WEB 站点，HTML 运行在浏览器上，由浏览器来解析。在本教程中，您将学习如何使用 HTML 来创建站点。
HTML 很容易学习！相信您能很快学会它！

```
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>HTML教程</title>
</head>
<body>
    <h1>我的第一个标题</h1>
    <p>我的第一个段落。</p>
</body>
</html>
<!--注意：对于中文网页需要使用 <meta charset="utf-8"> 声明编码，否则会出现乱码。-->

```
HTML文档的后缀名
- .html
- .htm

以上两种后缀名没有区别，都可以使用。

## chapter02 HTML 简介

```
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>产品客栈(runoob.com)</title>
</head>
<body>
 
<h1>我的第一个标题</h1>
 
<p>我的第一个段落。</p>
 
</body>
</html>
```

### 实例解析

- ` <!DOCTYPE html> ` 声明为 HTML5 文档
- ` <html> ` 元素是 HTML 页面的根元素
- ` <head> ` 元素包含了文档的元（meta）数据
- ` <title> ` 元素描述了文档的标题
- ` <body> ` 元素包含了可见的页面内容
- ` <h1> ` 元素定义一个大标题
- ` <p> ` 元素定义一个段落

### 什么是HTML?
HTML 是用来描述网页的一种语言。
- HTML 指的是超文本标记语言: HyperText Markup Language
- HTML 不是一种编程语言，而是一种标记语言
- 标记语言是一套标记标签 (markup tag)
- HTML 使用标记标签来描述网页
- HTML 文档包含了HTML 标签及文本内容
- HTML文档也叫做 web 页面

### HTML 标签
HTML 标记标签通常被称为 HTML 标签 (HTML tag)。
- HTML 标签是由尖括号包围的关键词，比如 ` <html> ` 
- HTML 标签通常是成对出现的，比如 ` <b> ` 和  ` </b> `
- 标签对中的第一个标签是开始标签，第二个标签是结束标签
- 开始和结束标签也被称为 *开放标签*和 *闭合标签*
```
<标签>内容</标签>
```

### HTML 元素
"HTML 标签" 和 "HTML 元素" 通常都是描述同样的意思.
但是严格来讲, 一个 HTML 元素包含了开始标签与结束标签，如下实例:
HTML 元素:
```
<p>这是一个段落。</p>
```

### Web 浏览器
Web浏览器（如谷歌浏览器，Internet Explorer，Firefox，Safari）是用于读取HTML文件，并将其作为网页显示。
浏览器并不是直接显示的HTML标签，但可以使用标签来决定如何展现HTML页面的内容给用户

### HTML 网页结构
下面是一个可视化的HTML页面结构：

    <html>
        <head>
            <title>页面标题</title>
        </head>
        <body>
            <h1>这是一个标题</h1>
            <p>这是一个段落</p>
            <p>这是另外一个段落</p>
       </body>
    </html>

> 只有 <body> 区域 (白色部分) 才会在浏览器中显示。

### HTML 版本
| 版本 | 发布时间 |
| :- | :- |
| HTML | 1991 |
| HTML+ | 1993 |
| HTML2.0 | 1995 |
| HTML3.2 | 1997 |
| HTML4.01 | 1999 |
| XHTML1.0 | 2000 |
| HTML5 | 2012 |
| XHTML5 | 2013 |

### <!DOCTYPE>声明
<!DOCTYPE>声明有助于浏览器中正确显示网页。
网络上有很多不同的文件，如果能够正确声明HTML的版本，浏览器就能正确显示网页内容。
doctype 声明是不区分大小写的，以下方式均可：

```
<!DOCTYPE html> 

<!DOCTYPE HTML> 

<!doctype html> 

<!Doctype Html>
```

### 通用声明
* HTML5

```
<!DOCTYPE html>
```

* HTML4.01

```
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN"
"http://www.w3.org/TR/html4/loose.dtd">
```

* XHTML1.0

```
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN"
"http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
```

### 中文编码

目前在大部分浏览器中，直接输出中文会出现中文乱码的情况，这时候我们就需要在头部将字符声明为 UTF-8。

```
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>页面标题</title>
</head>
<body>
 
<h1>我的第一个标题</h1>
 
<p>我的第一个段落。</p>
 
</body>
</html>
```




## chapter03 HTML 编辑器

### HTML 编辑器推荐
可以使用专业的 HTML 编辑器来编辑 HTML，菜鸟教程为大家推荐几款常用的编辑器：
* Notepad++：https://notepad-plus-plus.org/
* Sublime Text：http://www.sublimetext.com/
* HBuilder：http://www.dcloud.io/

### 每一种操作系统都带有简单的文本编辑器：
 * Windows 用户可以使用记事本；
 * Linux 用户可以选择几种不同的文本编辑器，如 vi、vim 或者 emacs ；
 * Mac 用户可以使用 OS X 预装的 TextEdit。


## chapter04 HTML 基础

### HTML 标题
HTML 标题（Heading）是通过 ` <h1> - <h6> ` 标签来定义的.
```
<h1>这是一个标题</h1>
<h2>这是一个标题</h2>
<h3>这是一个标题</h3>
```

### HTML 段落

HTML 段落是通过标签 ` <p> ` 来定义的.

```
<p>这是一个段落。</p>
<p>这是另外一个段落。</p>
```


### HTML 链接

HTML 链接是通过标签 ` <a> ` 来定义的.

```
<a href="http://www.runoob.com">这是一个链接</a>
```
**提示**:在 href 属性中指定链接的地址。

### HTML 图像

HTML 图像是通过标签 ` <img> ` 来定义的.

```
<img src="/images/logo.png" width="258" height="39" />
```
**注意:**  图像的名称和尺寸是以属性的形式提供的。

## chapter05 HTML 元素
> HTML 文档由 HTML 元素定义。

### HTML 元素
| 开始标签` * ` | 元素内容 | 结束标签` * ` |
| :- | :- | :- |
| ` <p> ` | 这是一个段落 | ` </p> ` |
| ` <a href="default.htm"> ` | 这是一个链接 | ` </a> ` |
| ` <br> ` | 换行符 |  |

> ` * ` 开始标签常被称为**起始标签（opening tag）**，结束标签常称为**闭合标签（closing tag）**。

### 元素语法

- HTML 元素以开始标签起始
- HTML 元素以结束标签终止
- **元素的内容**是开始标签与结束标签之间的内容
- 某些 HTML 元素具有**空内容（empty content）**
- 空元素在**开始标签中进行关闭**（以开始标签的结束而结束）
- 大多数 HTML 元素可拥有**属性**

**注释:** 您将在本教程的下一章中学习更多有关属性的内容。

### 嵌套的 HTML 元素
HTML 文档由嵌套的 HTML 元素构成。
**HTML 文档实例**

```
<!DOCTYPE html>
<html>

<body>
<p>这是第一个段落。</p>
</body>

</html>

<!--以上实例包含了三个 HTML 元素。-->
```
### HTML 实例解析

**` <p> ` 元素:** 

```
<p>这是第一个段落。</p>
```
这个 ` <p> ` 元素定义了 HTML 文档中的一个段落。
这个元素拥有一个开始标签 ` <p> ` 以及一个结束标签 ` </p> ` .
元素内容是: 这是第一个段落。

**` <body> ` 元素:**

```
<body>
<p>这是第一个段落。</p>
</body>
```
` <body> ` 元素定义了 HTML 文档的主体。
这个元素拥有一个开始标签 ` <body> ` 以及一个结束标签 ` </body> `。
元素内容是另一个 HTML 元素（p 元素）。

** ` <html> `  元素:**

```
<html>

<body>
<p>这是第一个段落。</p>
</body>

</html>
```
` <html> ` 元素定义了整个 HTML 文档。
这个元素拥有一个开始标签 ` <html> ` ，以及一个结束标签 ` </html> ` .
元素内容是另一个 HTML 元素（body 元素）。

### 不要忘记结束标签

即使您忘记了使用结束标签，大多数浏览器也会正确地显示 HTML：
```
<p>这是一个段落
<p>这是一个段落
```
以上实例在浏览器中也能正常显示，因为关闭标签是可选的。
但不要依赖这种做法。忘记使用结束标签会产生不可预料的结果或错误。

### HTML 空元素
没有内容的 HTML 元素被称为空元素。空元素是在开始标签中关闭的。
` <br> ` 就是没有关闭标签的空元素（` <br> ` 标签定义换行）。
在 XHTML、XML 以及未来版本的 HTML 中，所有元素都必须被关闭。
在开始标签中添加斜杠，比如 ` <br /> `，是关闭空元素的正确方法，HTML、XHTML 和 XML 都接受这种方式。
即使 ` <br> ` 在所有浏览器中都是有效的，但使用 ` <br /> ` 其实是更长远的保障。

### HTML 提示：使用小写标签
HTML 标签对大小写不敏感：` <P> ` 等同于 ` <p> ` 。许多网站都使用大写的 HTML 标签。
本教程使用的是小写标签，因为万维网联盟（W3C）在 HTML 4 中推荐使用小写，而在未来 (X)HTML 版本中强制使用小写。

**笔记列表:**

1. 一些标签的使用，切记所有标签都需要闭合，不管是单体标签还是成对标签。（尽管目前浏览器是识别有些标签不闭合的情况，但是取的最好的保证兼容性，使用闭合）
2. 标签写法要用小写字母（有些版本对大小写可认为相同，而xhtml中强制使用小写）





## chapter06 HTML 属性




## chapter07 HTML 段落



## chapter08 HTML 文本格式化



## chapter09 HTML 链接


## chapter10 HTML 头部


## chapter11 HTML CSS



## chapter12 HTML 图像



## chapter13 HTML 表格



## chapter14 HTML 列表



## chapter15 HTML 区块


## chapter16 HTML 布局



## chapter17 HTML 表单



## chapter18 HTML 框架



## chapter19 HTML 颜色



## chapter20 HTML 颜色名



## chapter21 HTML 颜色值



## chapter22 HTML 脚本



## chapter23 HTML 字符实体



## chapter24 HTML URL



## chapter25 HTML 速查列表



## chapter26 HTML 总结



## chapter27 XHTML 简介
