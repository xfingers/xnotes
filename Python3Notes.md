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
1. Python 可以同时为多个变量赋值，如 x, y = 7, 8 。
2. 一个变量可以通过赋值指向不同类型的对象。
3. 数值的除法(/)总是返回一个浮点数，要获取整数使用 // 操作符。
4. 在混合计算时，Python 会把整型转换成为浮点数。
### 3.2 String (字符串)
Python 中的字符串 str 用单引号('')或双引号("")括起来，同时使用反斜杠(\)转义特殊字符。
```
>>> s = 'Yes,he doesn\'t'
>>> print(s, type(s), len(s))
Yes,he doesn\'t <class 'str'> 14
```
如果不想让反斜杠发生转义，可以在字符串前面添加一个 r，表示原始字符串：
```
>>> print('C:\some\name')
C:\some
ame
>>> print(r'C:\some\name')
C:\some\name
```
另外，反斜杠可以作为续行符，表示下一行是上一行的延续。还可以使用"""..."""或者'''...'''跨越多行。
字符串可以使用 + 运算符串连接在一起，或者用 * 运算符重复：
```
>>> print('str'+'ing', 'my'*3)
string mymymy
```
Python中的字符串有两种索引方式，第一种是从左往右，从0开始依次增加；第二种是从右往左，从-1开始依次减少。
注意，没有单独的字符类型，一个字符就是长度为1的字符串。
```
>>> word = 'Python'
>>> print(word[0], word[5])
P n
>>> print(word[-1], word[-6])
n P
```
还可以对字符串进行切片，获取一段子串。用冒号分隔两个索引，形式为变量[头下标:尾下标]。
截取的范围是前闭后开的，并且两个索引都可以省略：
```
>>> word = 'ilovepython'
>>> word[1:5]
'love'
>>> word[:]
'ilovepython'
>>> word[5:]
'python'
>>> word[-10:-6]
'love'
```
与C字符串不同的是，Python字符串不能被改变。向一个索引位置赋值，比如word[0] = 'm'会导致错误。
**注意：**

1. 反斜杠可以用来转义，使用r可以让反斜杠不发生转义。
2. 字符串可以用 " + " 运算符连接在一起，用 " * " 运算符重复。
3. Python中的字符串有两种索引方式，从左往右以0开始，从右往左以-1开始。
4. Python中的字符串不能改变。
### 3.3 List (列表)
List（列表） 是 Python 中使用最频繁的数据类型。
列表是写在方括号之间、用逗号分隔开的元素列表。列表中元素的类型可以不相同：
```
>>> a = ['him', 25, 100, 'her']
>>> print(a)
['him', 25, 100, 'her']
```
和字符串一样，列表同样可以被索引和切片，列表被切片后返回一个包含所需元素的新列表。详细的在这里就不赘述了。
列表还支持串联操作，使用+操作符：
```
>>> a = [1, 2, 3, 4, 5]
>>> a + [6, 7, 8]
[1, 2, 3, 4, 5, 6, 7, 8]
```
与Python字符串不一样的是，列表中的元素是可以改变的：
```
>>> a = [1, 2, 3, 4, 5, 6]
>>> a[0] = 9
>>> a[2:5] = [13, 14, 15]
>>> a
[9, 2, 13, 14, 15, 6]
>>> a[2:5] = []   # 删除
>>> a
[9, 2, 6]
```
List内置了有很多方法，例如append()、pop()等等，这在后面会讲到。
**注意：**
1. List写在方括号之间，元素用逗号隔开。
2. 和字符串一样，list可以被索引和切片。
3. List可以使用+操作符进行拼接。
4. List中的元素是可以改变的。
### 3.4 Tuple (元组)
元组（tuple）与列表类似，不同之处在于元组的元素不能修改。元组写在小括号里，元素之间用逗号隔开。
元组中的元素类型也可以不相同：
```
>>> a = (1991, 2014, 'physics', 'math')
>>> print(a, type(a), len(a))
(1991, 2014, 'physics', 'math') <class 'tuple'> 4
```
元组与字符串类似，可以被索引且下标索引从0开始，也可以进行截取/切片（看上面，这里不再赘述）。
其实，可以把字符串看作一种特殊的元组。
```
>>> tup = (1, 2, 3, 4, 5, 6)
>>> print(tup[0], tup[1:5])
1 (2, 3, 4, 5)
>>> tup[0] = 11  # 修改元组元素的操作是非法的
```
虽然tuple的元素不可改变，但它可以包含可变的对象，比如list列表。
构造包含0个或1个元素的tuple是个特殊的问题，所以有一些额外的语法规则：
```
tup1 = () # 空元组
tup2 = (20,) # 一个元素，需要在元素后添加逗号
```
另外，元组也支持用+操作符：
```
>>> tup1, tup2 = (1, 2, 3), (4, 5, 6)
>>> print(tup1+tup2)
(1, 2, 3, 4, 5, 6)
```
string、list和tuple都属于sequence（序列）。
**注意：**
1. 与字符串一样，元组的元素不能修改。
2. 元组也可以被索引和切片，方法一样。
3. 注意构造包含0或1个元素的元组的特殊语法规则。
4. 元组也可以使用+操作符进行拼接。
### 3.5 Sets (集合)
集合（set）是一个无序不重复元素的集。
基本功能是进行成员关系测试和消除重复元素。
可以使用大括号 或者 set()函数创建set集合，注意：创建一个空集合必须用 set() 而不是 { }，因为{ }是用来创建一个空字典。
```
>>> student = {'Tom', 'Jim', 'Mary', 'Tom', 'Jack', 'Rose'}
>>> print(student)   # 重复的元素被自动去掉
{'Jim', 'Jack', 'Mary', 'Tom', 'Rose'}
>>> 'Rose' in student  # membership testing（成员测试）
True
>>> # set可以进行集合运算
...
>>> a = set('abracadabra')
>>> b = set('alacazam')
>>> a
{'a', 'b', 'c', 'd', 'r'}
>>> a - b     # a和b的差集
{'b', 'd', 'r'}
>>> a | b     # a和b的并集
{'l', 'm', 'a', 'b', 'c', 'd', 'z', 'r'}
>>> a & b     # a和b的交集
{'a', 'c'}
>>> a ^ b     # a和b中不同时存在的元素
{'l', 'm', 'b', 'd', 'z', 'r'}
```
### 3.6 Dictionaries (字典)
字典（dictionary）是Python中另一个非常有用的内置数据类型。
字典是一种映射类型（mapping type），它是一个无序的键 : 值对集合。
关键字必须使用不可变类型，也就是说list和包含可变类型的tuple不能做关键字。
在同一个字典中，关键字还必须互不相同。
```
>>> dic = {}  # 创建空字典
>>> tel = {'Jack':1557, 'Tom':1320, 'Rose':1886}
>>> tel
{'Tom': 1320, 'Jack': 1557, 'Rose': 1886}
>>> tel['Jack']   # 主要的操作：通过key查询
1557
>>> del tel['Rose']  # 删除一个键值对
>>> tel['Mary'] = 4127  # 添加一个键值对
>>> tel
{'Tom': 1320, 'Jack': 1557, 'Mary': 4127}
>>> list(tel.keys())  # 返回所有key组成的list
['Tom', 'Jack', 'Mary']
>>> sorted(tel.keys()) # 按key排序
['Jack', 'Mary', 'Tom']
>>> 'Tom' in tel       # 成员测试
True
>>> 'Mary' not in tel  # 成员测试
False
```
构造函数 dict() 直接从键值对sequence中构建字典，当然也可以进行推导，如下：
```
>>> dict([('sape', 4139), ('guido', 4127), ('jack', 4098)])
{'jack': 4098, 'sape': 4139, 'guido': 4127}
 
>>> {x: x**2 for x in (2, 4, 6)}
{2: 4, 4: 16, 6: 36}
 
>>> dict(sape=4139, guido=4127, jack=4098)
{'jack': 4098, 'sape': 4139, 'guido': 4127}
```
另外，字典类型也有一些内置的函数，例如clear()、keys()、values()等。
**注意：**
1. 字典是一种映射类型，它的元素是键值对。
2. 字典的关键字必须为不可变类型，且不能重复。
3. 创建空字典使用{ }。
## 04 Python3 解释器
Linux/Unix的系统上，Python解释器通常被安装在 /usr/local/bin/python3.6 这样的有效路径（目录）里。
可以将路径 /usr/local/bin 添加到 Linux/Unix 操作系统的环境变量中，这样就可以通过 shell 终端输入下面的命令来启动 Python 。
```
  $ Python 3.6.0
```
在Window系统下你可以通过以下命令来设置Python的环境变量，假设你的Python安装在 C:\Python36 下:
```
set path=%path%;C:\python36
```
### 4.1 交互式编程
我们可以在命令提示符中输入 "python" 命令来启动 Python 解释器：
```
$ python
Python 3.6 (default, Mar 27 2017, 09:25:04)
[GCC 4.8.2] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>>
```
在 python 提示符中输入以下语句，然后按回车键查看运行效果：
```
>>> print ("Hello, Python!")
Hello, Python!
```
当键入一个多行结构时，续行是必须的。我们可以看下如下 if 语句：
```
>>> the_world_is_flat = True
>>> if the_world_is_flat:
...     print("Be careful not to fall off!")
...
Be careful not to fall off!
```
### 4.2 脚本式编程
将如下代码拷贝至hello.py文件中：
```
#!/usr/bin/python3
# -*- coding: utf-8 -*-
print ("Hello, Python!");
```
通过以下命令执行该脚本：
```
python hello.py
```
输出结果为：
```
Hello, Python!
```
在Linux/Unix系统中，你可以在脚本顶部添加以下命令让Python脚本可以像SHELL脚本一样可直接执行：
```
#! /usr/bin/env python3.6
```
然后修改脚本权限，**使其有执行权限**，命令如下：
```
$ chmod +x hello.py
```
执行以下命令：
```
./hello.py
```
输出结果为：
```
Hello, Python!
```
## 05 Python3 注释
确保对模块, 函数, 方法和行内注释使用正确的风格
Python中的注释有单行注释和多行注释：
Python中单行注释以#开头，例如：
```
# 这是一个注释
print("Hello, World!")
```
多行注释用三个单引号（'''）或者三个双引号（"""）将注释括起来，例如:
1. 单引号(''')
```
#!/usr/bin/python3 
'''
这是多行注释，用三个单引号
这是多行注释，用三个单引号 
这是多行注释，用三个单引号
'''
print("Hello, World!")
```
2. 双引号(""")
```
#!/usr/bin/python3 
"""
这是多行注释，用三个双引号
这是多行注释，用三个双引号 
这是多行注释，用三个双引号
"""
print("Hello, World!")
```
## 06 Python3 数字运算
Python 解释器可以作为一个简单的计算器：您可以在解释器里输入一个表达式，它将输出表达式的值。
表达式的语法很直白： +, -, * 和/ 和在许多其它语言（如Pascal或C）里一样；括号可以用来为运算分组。例如：
```
>>> 2 + 2
4
>>> 50 - 5*6
20
>>> (50 - 5*6) / 4
5.0
>>> 8 / 5  # 总是返回一个浮点数
1.6
```
注意：在不同的机器上浮点运算的结果可能会不一样。之后我们会介绍有关控制浮点运算输出结果的内容。
在整数除法中，除法（/）总是返回一个浮点数，如果只想得到整数的结果，丢弃可能的分数部分，可以使用运算符 // ：
```
>>> 17 / 3  # 整数除法返回浮点型
5.666666666666667
>>>
>>> 17 // 3  # 整数除法返回向下取整后的结果
5
>>> 17 % 3  # ％操作符返回除法的余数
2
>>> 5 * 3 + 2
17
```
等号（'='）用于给变量赋值。赋值之后，除了下一个提示符，解释器不会显示任何结果。
```
>>> width = 20
>>> height = 5*9
>>> width * height
900
```
Python 可以使用**操作来进行幂运算：
```
>>> 5 ** 2  # 5 的平方
25
>>> 2 ** 7  # 2的7次方
128
```
变量在使用前必须先"定义"（即赋予变量一个值），否则会出现错误：
```
>>> # 尝试访问一个未定义的变量
... n
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'n' is not defined
```
浮点数得到完全的支持；不同类型的数混合运算时会将整数转换为浮点数：
```
>>> 3 * 3.75 / 1.5
7.5
>>> 7.0 / 2
3.5
```
在交互模式中，最后被输出的表达式结果被赋值给变量 _ 。这能使您在把Python作为一个桌面计算器使用时使后续计算更方便，例如：
```
>>> tax = 12.5 / 100
>>> price = 100.50
>>> price * tax
12.5625
>>> price + _
113.0625
>>> round(_, 2)
113.06
```
此处， _ 变量应被用户视为只读变量。不要显式地给它赋值——这样您将会创建一个具有相同名称的独立的本地变量，并且屏蔽了这个内置变量的功能。
## 07 Python3 字符串
除了数字，Python也能操作字符串。字符串有几种表达方式，可以使用单引号或双引号括起来：
```
>>> 'spam eggs'
'spam eggs'
>>> 'doesn\'t'
"doesn't"
>>> "doesn't"
"doesn't"
>>> '"Yes," he said.'
'"Yes," he said.'
>>> "\"Yes,\" he said."
'"Yes," he said.'
>>> '"Isn\'t," she said.'
'"Isn\'t," she said.'
```
Python中使用反斜杠转义引号和其它特殊字符来准确地表示。
如果字符串包含有单引号但不含双引号，则字符串会用双引号括起来，否则用单引号括起来。对于这样的输入字符串，print() 函数会产生更易读的输出。
跨行的字面字符串可用以下几种方法表示。使用续行符，即在每行最后一个字符后使用反斜线来说明下一行是上一行逻辑上的延续：
以下使用 \n 来添加新行：
```
>>> '"Isn\'t," she said.'
'"Isn\'t," she said.'
>>> print('"Isn\'t," she said.')
"Isn't," she said.
>>> s = 'First line.\nSecond line.'  # \n 意味着新行
>>> s  # 不使用 print(), \n 包含在输出中
'First line.\nSecond line.'
>>> print(s)  # 使用 print(), \n 输出一个新行
First line.
Second line.
```
以下使用 反斜线（\） 来续行：
```
hello = "This is a rather long string containing\n\
several lines of text just as you would do in C.\n\
    Note that whitespace at the beginning of the line is\
 significant."
 
print(hello)
```
注意，其中的换行符仍然要使用 \n 表示——反斜杠后的换行符被丢弃了。以上例子将如下输出：
```
This is a rather long string containing
several lines of text just as you would do in C.
    Note that whitespace at the beginning of the line is significant.
```
或者，字符串可以被 """ （三个双引号）或者 ''' （三个单引号）括起来。使用三引号时，换行符不需要转义，它们会包含在字符串中。以下的例子使用了一个转义符，避免在最开始产生一个不需要的空行。
```
print("""\
Usage: thingy [OPTIONS]
     -h                        Display this usage message
     -H hostname               Hostname to connect to
""")
```
其输出如下：
```
Usage: thingy [OPTIONS]
     -h                        Display this usage message
     -H hostname               Hostname to connect to
```
如果我们使用"原始"字符串，那么 \n 不会被转换成换行，行末的的反斜杠，以及源码中的换行符，都将作为数据包含在字符串内。例如：
```
hello = r"This is a rather long string containing\n\
several lines of text much as you would do in C."
 
print(hello)
```
将会输出：
```
This is a rather long string containing\n\
several lines of text much as you would do in C.
```
字符串可以使用 + 运算符串连接在一起，或者用 * 运算符重复：
```
>>> word = 'Help' + 'A'
>>> word
'HelpA'
>>> '<' + word*5 + '>'
'<HelpAHelpAHelpAHelpAHelpA>'
```
两个紧邻的字面字符串将自动被串连；上例的第一行也可以写成 word = 'Help' 'A' ；这样的操作只在两个字面值间有效，不能随意用于字符串表达式中：
```
>>> 'str' 'ing'                   #  <-  这样操作正确
'string'
>>> 'str'.strip() + 'ing'   #  <-  这样操作正确
'string'
>>> 'str'.strip() 'ing'     #  <-  这样操作错误
  File "<stdin>", line 1, in ?
    'str'.strip() 'ing'
                      ^
SyntaxError: invalid syntax
```
字符串可以被索引；就像 C 语言一样，字符串的第一个字符的索引为 0。没有单独的字符类型；一个字符就是长度为一的字符串。就像Icon编程语言一样，子字符串可以使用分切符来指定：用冒号分隔的两个索引。
```
>>> word[4]
'A'
>>> word[0:2]
'Hl'
>>> word[2:4]
'ep'
```
默认的分切索引很有用：默认的第一个索引为零，第二个索引默认为字符串可以被分切的长度。
```
>>> word[:2]    # 前两个字符
'He'
>>> word[2:]    # 除了前两个字符之外，其后的所有字符
'lpA'
```
不同于C字符串的是，Python字符串不能被改变。向一个索引位置赋值会导致错误：
```
>>> word[0] = 'x'
Traceback (most recent call last):
  File "<stdin>", line 1, in ?
TypeError: 'str' object does not support item assignment
>>> word[:1] = 'Splat'
Traceback (most recent call last):
  File "<stdin>", line 1, in ?
TypeError: 'str' object does not support slice assignment
```
然而，用组合内容的方法来创建新的字符串是简单高效的：
```
>>> 'x' + word[1:]
'xelpA'
>>> 'Splat' + word[4]
'SplatA'
在分切操作字符串时，有一个很有用的规律： s[:i] + s[i:] 等于 s.
 
>>> word[:2] + word[2:]
'HelpA'
>>> word[:3] + word[3:]
'HelpA'
```
对于有偏差的分切索引的处理方式也很优雅：一个过大的索引将被字符串的大小取代，上限值小于下限值将返回一个空字符串。
```
>>> word[1:100]
'elpA'
>>> word[10:]
 
>>> word[2:1]
```
在索引中可以使用负数，这将会从右往左计数。例如：
```
>>> word[-1]     # 最后一个字符
'A'
>>> word[-2]     # 倒数第二个字符
'p'
>>> word[-2:]    # 最后两个字符
'pA'
>>> word[:-2]    # 除了最后两个字符之外，其前面的所有字符
'Hel'
但要注意， -0 和 0 完全一样，所以 -0 不会从右开始计数！
 
>>> word[-0]     # (既然 -0 等于 0)
'H'
```
超出范围的负数索引会被截去多余部分，但不要尝试在一个单元素索引（非分切索引）里使用：
```
>>> word[-100:]
'HelpA'
>>> word[-10]    # 错误
Traceback (most recent call last):
  File "<stdin>", line 1, in ?
IndexError: string index out of range
```
有一个方法可以让您记住分切索引的工作方式，想像索引是指向字符之间，第一个字符左边的数字是 0。接着，有n个字符的字符串最后一个字符的右边是索引n，例如：
```
+---+---+---+---+---+
 | H | e | l | p | A |
 +---+---+---+---+---+
 0   1   2   3   4   5
-5  -4  -3  -2  -1
```
第一行的数字 0...5 给出了字符串中索引的位置；第二行给出了相应的负数索引。分切部分从 i 到 j 分别由在边缘被标记为 i 和 j 的全部字符组成。
对于非负数分切部分，如果索引都在有效范围内，分切部分的长度就是索引的差值。例如， word[1:3] 的长度是2。
内置的函数 len() 用于返回一个字符串的长度：
```
>>> s = 'supercalifragilisticexpialidocious'
>>> len(s)
34
```
## 08 Python3 列表
Python囊括了大量的复合数据类型，用于组织其它数值。最有用的是列表，即写在方括号之间、用逗号分隔开的数值列表。列表内的项目不必全是相同的类型。
```
>>> a = ['spam', 'eggs', 100, 1234]
>>> a
['spam', 'eggs', 100, 1234]
>>> squares = [1, 4, 9, 16, 25]
>>> squares
[1, 4, 9, 16, 25]
```
像字符串一样，列表可以被索引和切片：
```
<pre>
>>> squares[0]  # 索引返回的指定项
1
>>> squares[-1]
25
>>> squares[-3:]  # 切割列表并返回新的列表
[9, 16, 25]
```
所有的分切操作返回一个包含有所需元素的新列表。如下例中，分切将返回列表 squares 的一个拷贝：
```
>>> squares[:]
[1, 4, 9, 16, 25]
```
列表还支持拼接操作：
```
>>> squares + [36, 49, 64, 81, 100]
[1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
```
Python 字符串是固定的，列表可以改变其中的元素：
```
>>> cubes = [1, 8, 27, 65, 125]   
>>> 4 ** 3  
64
>>> cubes[3] = 64  # 修改列表值
>>> cubes
[1, 8, 27, 64, 125]
```
也可以通过使用append()方法在列表的末尾添加新项：
```
>>> cubes.append(216)  # cube列表中添加新值
>>> cubes.append(7 ** 3)  #  cube列表中添加第七个值
>>> cubes
[1, 8, 27, 64, 125, 216, 343]
```
也可以修改指定区间的列表值：
```
>>> letters = ['a', 'b', 'c', 'd', 'e', 'f', 'g']
>>> letters
['a', 'b', 'c', 'd', 'e', 'f', 'g']
>>> # 替换一些值
>>> letters[2:5] = ['C', 'D', 'E']
>>> letters
['a', 'b', 'C', 'D', 'E', 'f', 'g']
>>> # 移除值
>>> letters[2:5] = []
>>> letters
['a', 'b', 'f', 'g']
>>> # 清除列表
>>> letters[:] = []
>>> letters
[]
```
内置函数 len() 用于统计列表：
```
>>> letters = ['a', 'b', 'c', 'd']
>>> len(letters)
4
```
也可以使用嵌套列表（在列表里创建其它列表），例如：
```
>>> a = ['a', 'b', 'c']
>>> n = [1, 2, 3]
>>> x = [a, n]
>>> x
[['a', 'b', 'c'], [1, 2, 3]]
>>> x[0]
['a', 'b', 'c']
>>> x[0][1]
'b'
```
## 09 Python3 编程第一步
现在，我们能使用Python完成比 2+2 更复杂的工作。在下例里，我们能写出一个初步的斐波纳契数列如下：
```
>>> # Fibonacci series: 斐波纳契数列
... # 两个元素的总和确定了下一个数
... a, b = 0, 1
>>> while b < 10:
...     print(b)
...     a, b = b, a+b
...
1
1
2
3
5
8
```
这个例子介绍了几个新特征。
- 第一行包含了一个复合赋值：变量 a 和 b 同时得到新值 0 和 1。最后一行再次使用了同样的方法，可以看到，右边的表达式会在赋值变动之前执行。右边表达式的执行顺序是从左往右的。
```
>>> i = 256*256
>>> print('The value of i is', i)
The value of i is 65536
```
关键字end可以被用于防止输出新的一行，或者在输出的末尾添加不同的字符：
```
>>> a, b = 0, 1
>>> while b < 1000:
...     print(b, end=',')
...     a, b = b, a+b
...
1,1,2,3,5,8,13,21,34,55,89,144,233,377,610,987,
```
## 10 Python3 条件控制：if 语句
Python中if语句的一般形式如下所示：
```
if condition_1:
    statement_block_1
elif condition_2:
    statement_block_2
else:
    statement_block_3
```
如果 "condition_1" 为 True 将执行 "statement_block_1" 块语句，如果 "condition_1" 为False，将判断 "condition_2"，如果"condition_2" 为 True 将执行 "statement_block_2" 块语句，如果 "condition_2" 为False，将执行"statement_block_3"块语句。
#### 实例
以下实例演示了狗的年龄计算判断：
```
age = int(input("Age of the dog: "))
print()
if age < 0:
    print("This can hardly be true!")
elif age == 1:
    print("about 14 human years")
elif age == 2:
    print("about 22 human years")
elif age > 2:
    human = 22 + (age -2)*5
    print("Human years: ", human)
input('press Return>')
```
将以上脚本保存在dog.py文件中，并执行该脚本：
```
python dog.py
Age of the dog: 1
 
about 14 human years
```
以下为if中常用的操作运算符:
| 操作符 | 描述 |
|:-:|:-|
| < | 小于 |
| <= | 小于或等于 |
| > | 大于 |
| >= | 大于或等于 |
| == | 等于，比较对象是否相等 |
| != | 不等于 |
#### 实例
```
# 程序演示了 == 操作符
# 使用数字
print(5 == 6)
# 使用变量
x = 5
y = 8
print(x == y)
```
以上实例输出结果：
```
False
False
```
high_low.py文件：
```
#!/usr/bin/python3
# 该实例演示了数字猜谜游戏
number = 7
guess = -1
print("Guess the number!")
while guess != number:
    guess = int(input("Is it... "))
  
    if guess == number:
        print("Hooray! You guessed it right!")
    elif guess < number:
        print("It's bigger...")
    elif guess > number:
        print("It's not so big.")
```
## 11 Python3 循环
## 12 Python3 函数
## 13 Python3 数据结构
## 14 Python3 模块
## 15 Python3 输入和输出
## 16 Python3 错误和异常
## 17 Python3 类
## 18 Python3 标准库概览
