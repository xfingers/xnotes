# Python 3 笔记 - 传说中的闲人
## 01 Python3 概述
> Python 的 3.0 版本，常被称为 Python 3000，或简称 Py3k。相对于 Python 的早期版本，这是一个较大的升级。为了不带入过多的累赘，Python 3.0 在设计的时候没有考虑向下兼容。

### 1.1 查看 Python 版本 : 
```
  $ python -V 
```
以上命令执行结果如下: 
```
  $ Python 3.6.0
```
### 1.2 进入 Python 交互式编程模式：`$ python ` 或 `$ ipython `
### 1.3 第一个 Python3 程序
```
  #!/usr/bin/python3
  print("Hello, Python!")
```
将以上代码保存在 hello.py 文件中，并使用 python 命令执行该脚本文件
```
  $ python hello.py
```
以上命令输出结果为：
```
  Hello, Python!
```
## 02 Python3 基础语法
### 2.1 编码
默认情况下，Python3 源码文件以 UTF-8 编码，所有字符串都是 unicode 字符串。也可以为源码文件指定不同的编码:
```
  # -*- coding: cp-1252 -*-
```
### 2.2 标识符
- 第一个字符必须是字母表中子目或下划线“ _ ”。
- 标识符的其他的部分由字母、数字和下划线组成。
- 标识符对大小写敏感。

在 Python3 中，非 -ASCII 标识符也是允许的。
### 2.3 Python 保留字
保留字即关键字，不能把它们用作任何标识符名称。Python 的标准库提供了一个 keyword module，可以输出当前版本的所有关键字：
```
>>> import keyword
>>> keyword.kwlist
['False', 'None', 'True', 'and', 'as', 'assert', 'break', 'class', 'continue', 'def', 'del', 'elif', 'else', 'except', 'finally', 'for', 'from', 'global', 'if', 'import', 'in', 'is', 'lambda', 'nonlocal', 'not', 'or', 'pass', 'raise', 'return', 'try', 'while', 'with', 'yield']
```
### 2.4 注释
Python 中单行注释以 # 开头，多行注释用三个单引号 (''') 或者三个双引号（"""）将注释括起来。
### 2.5 行与缩进
Python 最具特色的就是使用缩进来表示代码块。缩进的空格数是可变的，但是同一个代码块的语句必须包含相同的缩进空格数。通常建议使用**四个连续的空格**。
### 2.6 数据类型
Python 中的数有四种类型：整数、长整数、浮点数和复数。
- 整数，如 11
- 长整数，是比较大的整数
- 浮点数，如 1.23、3E-2
- 复数，如 1+2j、1.1 + 2.2j
### 2.7 字符串
- Python 中单引号和双引号使用完全相同。
- 使用三引号 ( ''' 或 """ ) 可以指定一个多行字符串。
- 转义符 '\'
- 自然字符串，通过在字符串前加 r 或 R 。如 r"This is a Python line with \n"则 \n 会显示，并不是换行。
- Python 允许处理unicode字符串，加前缀 u 或 U，如 u"This is an unicode string"。
- 字符串是不可变的。
- 按字面意义级联字符串，如 "this ""is ""string "会被自动转换为 this is string。
## 03 Python3 基本数据类型
Python 中的变量不需要声明。每个变量在使用前都必须赋值，变量赋值以后该变量才会被创建。在 Python 中，变量就是变量，它没有类型，我们所说的“类型”是变量所指的内存中对象的类型。
Python 3 中有六个标准的数据类型：
- Numbers (数字)
- String (字符串)
- List (列表)
- Tuple (元组)
- Sets (集合)
- Dictionaries (字典)
***
### 3.1 Numbers (数字)
Python 3 支持 int、float、bool、complex(复数)。
数字类型的赋值和计算都是很直观的，就像大多数语言一样。内置的type()函数可以用来查询变量所指的对象类型。
```
>>> a, b, c, d = 77, 12.8, False, 11 + 11j
>>> print(type(a), type(b), type(c), type(d))
<class 'int'> <class 'float'> <class 'bool'> <class 'complex'>
```
数值运算：
```
>>> 7 + 11 # 加法
18
>>> 12.8 - 2 # 减法
10.8
>>> 7 * 11 # 乘法
77
>>> 4 / 8 # 除法，得到一个浮点数
0.5
>>> 4 // 8 # 地板除，得到一个整数
0
>>> 29 % 3 # 取余
2
>>> 2 ** 6 # 乘方
64
```
**注意 :**
1. Python 可以同时为多个变量赋值，如 x, y = 7, 8
2. 一个变量可以通过赋值指向不同类型的对象。
3. 数值的除法(/)总是返回一个浮点数，要获取整数使用 // 操作符
4. 在混合计算时，Python 会把整型转换成为浮点数
### 3.2 String (字符串)
### 3.3 List (列表)
### 3.4 Tuple (元组)
### 3.5 Sets (集合)
### 3.6 Dictionaries (字典)

## 04 Python3 解释器
## 05 Python3 注释
## 06 Python3 数字运算
## 07 Python3 字符串
## 08 Python3 列表
## 09 Python3 编程第一步
## 10 Python3 条件控制
## 11 Python3 循环
## 12 Python3 函数
## 13 Python3 数据结构
## 14 Python3 模块
## 15 Python3 输入和输出
## 16 Python3 错误和异常
## 17 Python3 类
## 18 Python3 标准库概览
