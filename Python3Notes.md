# Python 3 笔记 - 传说中的闲人
## Chapter01 Python3 概述
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
## Chapter02 Python3 基础语法
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
## Chapter03 Python3 基本数据类型
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
## Chapter04 Python3 解释器
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
## Chapter05 Python3 注释
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
## Chapter06 Python3 数字运算
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

此处,  _  变量应被用户视为只读变量。不要显式地给它赋值——这样您将会创建一个具有相同名称的独立的本地变量，并且屏蔽了这个内置变量的功能。

## Chapter07 Python3 字符串
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
## Chapter08 Python3 列表
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
## Chapter09 Python3 编程第一步
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
## Chapter10 Python3 条件控制：if 语句
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
## Chapter11 Python3 循环
Python中的循环语句有 for 和 while。
### 11.1 while 循环
以下实例使用了 while 来计算 1 到 100 的总和：
```
#!/usr/bin/env python3
 
n = 100
 
sum = 0
counter = 1
while counter <= n:
    sum = sum + counter
    counter += 1
 
print("Sum of 1 until %d: %d" % (n,sum))
```
执行结果如下：
```
Sum of 1 until 100: 5050
```
### 11.2 for 语句
Python for循环可以遍历任何序列的项目，如一个列表或者一个字符串。
for循环的一般格式如下：
```
for <variable> in <sequence>:
    <statements>
else:
    <statements>
```
Python loop循环实例：
```
>>> languages = ["C", "C++", "Perl", "Python"] 
>>> for x in languages:
...     print(x)
... 
C
C++
Perl
Python
>>>
```
以下实例for实例中使用了 break语句，break语句用于跳出当前循环体：
```
#!/usr/bin/env python3
edibles = ["ham", "spam","eggs","nuts"]
for food in edibles:
    if food == "spam":
        print("No more spam please!")
        break
    print("Great, delicious " + food)
else:
    print("I am so glad: No spam!")
print("Finally, I finished stuffing myself")
```
执行脚本后，在循环到 "spam"时会跳出循环体：
```
Great, delicious ham
No more spam please!
Finally, I finished stuffing myself
```
### 11.3 range() 函数
如果你需要遍历数字序列，可以使用内置range()函数。它会生成数列，例如:
```
>>> for i in range(5):
...     print(i)
...
0
1
2
3
4
```
你也可以使用range指定区间的值：
```
>>> for i in range(5,9) :
    print(i)
 
     
5
6
7
8
>>>
```
也可以使range以指定数字开始并指定不同的增量(甚至可以是负数;有时这也叫做'步长'):
```
>>> for i in range(0, 10, 3) :
    print(i)
 
     
0
3
6
9
>>>
```
负数：
```
>>> for i in range(-10, -100, -30) :
    print(i)
-10
-40
-70
>>>
```
您可以结合range()和len()函数以遍历一个序列的索引,如下所示:
```
>>> a = ['Mary', 'had', 'a', 'little', 'lamb']
>>> for i in range(len(a)):
...     print(i, a[i])
...
0 Mary
1 had
2 a
3 little
4 lamb
```
还可以使用range()函数来创建一个列表：
```
>>> list(range(5))
[0, 1, 2, 3, 4]
>>>
```
### 11.4 break和continue语句及循环中的else子句
break语句可以跳出for和while的循环体。如果你从for或while循环中终止，任何对应的循环else块将不执行。
continue语句被用来告诉Python跳过当前循环块中的剩余语句，然后继续进行下一轮循环。
循环语句可以有else子句;它在穷尽列表(以for循环)或条件变为假(以while循环)循环终止时被执行,但循环被break终止时不执行.如下查寻质数的循环例子:
```
>>> for n in range(2, 10):
...     for x in range(2, n):
...         if n % x == 0:
...             print(n, 'equals', x, '*', n//x)
...             break
...     else:
...         # 循环中没有找到元素
...         print(n, 'is a prime number')
...
2 is a prime number
3 is a prime number
4 equals 2 * 2
5 is a prime number
6 equals 2 * 3
7 is a prime number
8 equals 2 * 4
9 equals 3 * 3
```
### 11.5 pass语句
pass语句什么都不做。它只在语法上需要一条语句但程序不需要任何操作时使用.例如:
```
>>> while True:
...     pass  # 等待键盘中断 (Ctrl+C)
```
最小的类:
```
>>> class MyEmptyClass:
...     pass
```
## Chapter12 Python3 函数
Python 定义函数使用 def 关键字，一般格式如下：
```
def  函数名（参数列表）：
    函数体
```
让我们使用函数来输出"Hello World！"：
```
>>> def hello() :
    print("Hello World!")
>>> hello()
Hello World!
>>>
```
更复杂点的应用，函数中带上参数变量:
```
def area(width, height):
    return width * height
  
def print_welcome(name):
    print("Welcome", name)
 
print_welcome("Fred")
w = 4
h = 5
print("width =", w, " height =", h, " area =", area(w, h))
```
以上实例输出结果：
```
Welcome Fred
width = 4  height = 5  area = 20
```
### 12.1 函数变量作用域
定义在函数内部的变量拥有一个局部作用域，定义在函数外的拥有全局作用域。
通过以下实例，你可以清楚了解Python函数变量的作用域：
```
#!/usr/bin/env python3
a = 4  # 全局变量
  
def print_func1():
    a = 17 # 局部变量
    print("in print_func a = ", a)
def print_func2():  
    print("in print_func a = ", a)
print_func1()
print_func2()
print("a = ", a)
```
以上实例运行结果如下：
```
in print_func a =  17
in print_func a =  4
a =  4
```
### 12.2 关键字参数
函数也可以使用 kwarg=value 的关键字参数形式被调用.例如,以下函数:
```
def parrot(voltage, state='a stiff', action='voom', type='Norwegian Blue'):
    print("-- This parrot wouldn't", action, end=' ')
    print("if you put", voltage, "volts through it.")
    print("-- Lovely plumage, the", type)
    print("-- It's", state, "!")
```
可以以下几种方式被调用:
```
parrot(1000)                                          # 1 positional argument
parrot(voltage=1000)                                  # 1 keyword argument
parrot(voltage=1000000, action='VOOOOOM')             # 2 keyword arguments
parrot(action='VOOOOOM', voltage=1000000)             # 2 keyword arguments
parrot('a million', 'bereft of life', 'jump')         # 3 positional arguments
parrot('a thousand', state='pushing up the daisies')  # 1 positional, 1 keyword
```
以下为错误调用方法：
```
parrot()                     # required argument missing
parrot(voltage=5.0, 'dead')  # non-keyword argument after a keyword argument
parrot(110, voltage=220)     # duplicate value for the same argument
parrot(actor='John Cleese')  # unknown keyword argument
```
### 12.3 返回值
Python的函数的返回值使用return语句，可以将函数作为一个值赋值给指定变量：
```
def return_sum(x,y):
    c = x + y
    return c
 
res = return_sum(4,5)
print(res)
```
也可以让函数返回空值：
```
def empty_return(x,y):
    c = x + y
    return
 
res = empty_return(4,5)
print(res)
```
### 12.4 可变参数列表
最后,一个最不常用的选择是可以让函数调用可变个数的参数.这些参数被包装进一个元组(查看元组和序列).在这些可变个数的参数之前,可以有零到多个普通的参数:
```
def arithmetic_mean(*args):
    sum = 0
    for x in args:
        sum += x
    return sum
 
print(arithmetic_mean(45,32,89,78))
print(arithmetic_mean(8989.8,78787.78,3453,78778.73))
print(arithmetic_mean(45,32))
print(arithmetic_mean(45))
print(arithmetic_mean())
```
以上实例输出结果为：
```
244
170009.31
77
45
0
```
## Chapter13 Python3 数据结构
### 13.1 列表
Python中列表是可变的，这是它区别于字符串和元组的最重要的特点，一句话概括即：列表可以修改，而字符串和元组不能。
以下是 Python 中列表的方法：

| 方法 | 描述 |
|:-:|:-|
| list.append(x) | 把一个元素添加到列表的结尾，相当于 a[len(a):] = [x]。 |
| list.extend(L) | 通过添加指定列表的所有元素来扩充列表，相当于 a[len(a):] = L。 |
| list.insert(i, x) | 在指定位置插入一个元素。第一个参数是准备插入到其前面的那个元素的索引，例如 a.insert(0, x) 会插入到整个列表之前，而 a.insert(len(a), x) 相当于 a.append(x) 。 |
| list.remove(x) | 删除列表中值为 x 的第一个元素。如果没有这样的元素，就会返回一个错误。 |
| list.pop([i]) | 从列表的指定位置删除元素，并将其返回。如果没有指定索引，a.pop()返回最后一个元素。元素随即从列表中被删除。（方法中 i 两边的方括号表示这个参数是可选的，而不是要求你输入一对方括号，你会经常在 Python 库参考手册中遇到这样的标记。） |
| list.clear() | 移除列表中的所有项，等于del a[:]。 |
| list.index(x) | 返回列表中第一个值为 x 的元素的索引。如果没有匹配的元素就会返回一个错误。 |
| list.count(x) | 返回 x 在列表中出现的次数。 |
| list.sort() | 对列表中的元素进行排序。 |
| list.reverse() | 倒排列表中的元素。 |
| list.copy() | 返回列表的浅复制，等于a[:]。 |

下面示例演示了列表的大部分方法：
```
>>> a = [66.25, 333, 333, 1, 1234.5]
>>> print(a.count(333), a.count(66.25), a.count('x'))
2 1 0
>>> a.insert(2, -1)
>>> a.append(333)
>>> a
[66.25, 333, -1, 333, 1, 1234.5, 333]
>>> a.index(333)
1
>>> a.remove(333)
>>> a
[66.25, -1, 333, 1, 1234.5, 333]
>>> a.reverse()
>>> a
[333, 1234.5, 1, 333, -1, 66.25]
>>> a.sort()
>>> a
[-1, 1, 66.25, 333, 333, 1234.5]
```
> 注意：类似 insert, remove 或 sort 等修改列表的方法没有返回值。
### 13.2 将列表当做堆栈使用
列表方法使得列表可以很方便的作为一个堆栈来使用，堆栈作为特定的数据结构，最先进入的元素最后一个被释放（后进先出）。用 append() 方法可以把一个元素添加到堆栈顶。用不指定索引的 pop() 方法可以把一个元素从堆栈顶释放出来。例如：
```
>>> stack = [3, 4, 5]
>>> stack.append(6)
>>> stack.append(7)
>>> stack
[3, 4, 5, 6, 7]
>>> stack.pop()
7
>>> stack
[3, 4, 5, 6]
>>> stack.pop()
6
>>> stack.pop()
5
>>> stack
[3, 4]
```
### 13.3 将列表当作队列使用
也可以把列表当做队列用，只是在队列里第一加入的元素，第一个取出来；但是拿列表用作这样的目的效率不高。在列表的最后添加或者弹出元素速度快，然而在列表里插入或者从头部弹出速度却不快（因为所有其他的元素都得一个一个地移动）。
```
>>> from collections import deque
>>> queue = deque(["Eric", "John", "Michael"])
>>> queue.append("Terry")           # Terry arrives
>>> queue.append("Graham")          # Graham arrives
>>> queue.popleft()                 # The first to arrive now leaves
'Eric'
>>> queue.popleft()                 # The second to arrive now leaves
'John'
>>> queue                           # Remaining queue in order of arrival
deque(['Michael', 'Terry', 'Graham'])
```
### 13.4 列表推导式
列表推导式提供了从序列创建列表的简单途径。通常应用程序将一些操作应用于某个序列的每个元素，用其获得的结果作为生成新列表的元素，或者根据确定的判定条件创建子序列。
每个列表推导式都在 for 之后跟一个表达式，然后有零到多个 for 或 if 子句。返回结果是一个根据表达从其后的 for 和 if 上下文环境中生成出来的列表。如果希望表达式推导出一个元组，就必须使用括号。
这里我们将列表中每个数值乘三，获得一个新的列表：
```
>>> vec = [2, 4, 6]
>>> [3*x for x in vec]
[6, 12, 18]
```
现在我们玩一点小花样：
```
>>> [[x, x**2] for x in vec]
[[2, 4], [4, 16], [6, 36]]
```
这里我们对序列里每一个元素逐个调用某方法：
```
>>> vec = [2, 4, 6]
>>> [3*x for x in vec]
[6, 12, 18]
```
现在我们玩一点小花样：
```
>>> [[x, x**2] for x in vec]
[[2, 4], [4, 16], [6, 36]]
```
这里我们对序列里每一个元素逐个调用某方法：
```
>>> freshfruit = ['  banana', '  loganberry ', 'passion fruit  ']
>>> [weapon.strip() for weapon in freshfruit]
['banana', 'loganberry', 'passion fruit']
```
我们可以用 if 子句作为过滤器：
```
>>> [3*x for x in vec if x > 3]
[12, 18]
>>> [3*x for x in vec if x < 2]
[]
```
以下是一些关于循环和其它技巧的演示：
```
>>> vec1 = [2, 4, 6]
>>> vec2 = [4, 3, -9]
>>> [x*y for x in vec1 for y in vec2]
[8, 6, -18, 16, 12, -36, 24, 18, -54]
>>> [x+y for x in vec1 for y in vec2]
[6, 5, -7, 8, 7, -5, 10, 9, -3]
>>> [vec1[i]*vec2[i] for i in range(len(vec1))]
[8, 12, -54]
```
列表推导式可以使用复杂表达式或嵌套函数：
```
>>> [str(round(355/113, i)) for i in range(1, 6)]
['3.1', '3.14', '3.142', '3.1416', '3.14159']
```
### 13.5 嵌套列表解析
Python的列表还可以嵌套。
以下实例展示了3X4的矩阵列表：
```
>>> matrix = [
...     [1, 2, 3, 4],
...     [5, 6, 7, 8],
...     [9, 10, 11, 12],
... ]
```
以下实例将3X4的矩阵列表转换为4X3列表：
```
>>> [[row[i] for row in matrix] for i in range(4)]
[[1, 5, 9], [2, 6, 10], [3, 7, 11], [4, 8, 12]]
```
以下实例也可以使用以下方法来实现：
```
>>> transposed = []
>>> for i in range(4):
...     transposed.append([row[i] for row in matrix])
...
>>> transposed
[[1, 5, 9], [2, 6, 10], [3, 7, 11], [4, 8, 12]]
```
另外一种实现方法：
```
>>> transposed = []
>>> for i in range(4):
...     # the following 3 lines implement the nested listcomp
...     transposed_row = []
...     for row in matrix:
...         transposed_row.append(row[i])
...     transposed.append(transposed_row)
...
>>> transposed
[[1, 5, 9], [2, 6, 10], [3, 7, 11], [4, 8, 12]]
```
### 13.6 del 语句
使用 del 语句可以从一个列表中依索引而不是值来删除一个元素。这与使用 pop() 返回一个值不同。可以用 del 语句从列表中删除一个切割，或清空整个列表（我们以前介绍的方法是给该切割赋一个空列表）。例如：
```
>>> a = [-1, 1, 66.25, 333, 333, 1234.5]
>>> del a[0]
>>> a
[1, 66.25, 333, 333, 1234.5]
>>> del a[2:4]
>>> a
[1, 66.25, 1234.5]
>>> del a[:]
>>> a
[]
```
也可以用 del 删除实体变量：
```
>>> del a
```
### 13.7 元组和序列
元组由若干逗号分隔的值组成，例如：
```
>>> t = 12345, 54321, 'hello!'
>>> t[0]
12345
>>> t
(12345, 54321, 'hello!')
>>> # Tuples may be nested:
... u = t, (1, 2, 3, 4, 5)
>>> u
((12345, 54321, 'hello!'), (1, 2, 3, 4, 5))
```
如你所见，元组在输出时总是有括号的，以便于正确表达嵌套结构。在输入时可能有或没有括号， 不过括号通常是必须的（如果元组是更大的表达式的一部分）。
### 13.8 集合
集合是一个无序不重复元素的集。基本功能包括关系测试和消除重复元素。
可以用大括号({})创建集合。注意：如果要创建一个空集合，你必须用 set() 而不是 {} ；后者创建一个空的字典，下一节我们会介绍这个数据结构。
以下是一个简单的演示：
```
>>> basket = {'apple', 'orange', 'apple', 'pear', 'orange', 'banana'}
>>> print(basket)                      # show that duplicates have been removed
{'orange', 'banana', 'pear', 'apple'}
>>> 'orange' in basket                 # fast membership testing
True
>>> 'crabgrass' in basket
False
 
>>> # Demonstrate set operations on unique letters from two words
...
>>> a = set('abracadabra')
>>> b = set('alacazam')
>>> a                                  # unique letters in a
{'a', 'r', 'b', 'c', 'd'}
>>> a - b                              # letters in a but not in b
{'r', 'd', 'b'}
>>> a | b                              # letters in either a or b
{'a', 'c', 'r', 'd', 'b', 'm', 'z', 'l'}
>>> a & b                              # letters in both a and b
{'a', 'c'}
>>> a ^ b                              # letters in a or b but not both
{'r', 'd', 'b', 'm', 'z', 'l'}>>> basket = {'apple', 'orange', 'apple', 'pear', 'orange', 'banana'}
>>> print(basket)                      # show that duplicates have been removed
{'orange', 'banana', 'pear', 'apple'}
>>> 'orange' in basket                 # fast membership testing
True
>>> 'crabgrass' in basket
False
 
>>> # Demonstrate set operations on unique letters from two words
...
>>> a = set('abracadabra')
>>> b = set('alacazam')9
>>> a                                  # unique letters in a
{'a', 'r', 'b', 'c', 'd'}
>>> a - b                              # letters in a but not in b
{'r', 'd', 'b'}
>>> a | b                              # letters in either a or b
{'a', 'c', 'r', 'd', 'b', 'm', 'z', 'l'}
>>> a & b                              # letters in both a and b
{'a', 'c'}
>>> a ^ b                              # letters in a or b but not both
{'r', 'd', 'b', 'm', 'z', 'l'}
```
集合也支持推导式：
```
>>> a = {x for x in 'abracadabra' if x not in 'abc'}
>>> a
{'r', 'd'}
```
### 13.9 字典
另一个非常有用的 Python 内建数据类型是字典。
序列是以连续的整数为索引，与此不同的是，字典以关键字为索引，关键字可以是任意不可变类型，通常用字符串或数值。
理解字典的最佳方式是把它看做无序的键=>值对集合。在同一个字典之内，关键字必须是互不相同。
一对大括号创建一个空的字典：{}。
这是一个字典运用的简单例子：
```
>>> tel = {'jack': 4098, 'sape': 4139}
>>> tel['guido'] = 4127
>>> tel
{'sape': 4139, 'guido': 4127, 'jack': 4098}
>>> tel['jack']
4098
>>> del tel['sape']
>>> tel['irv'] = 4127
>>> tel
{'guido': 4127, 'irv': 4127, 'jack': 4098}
>>> list(tel.keys())
['irv', 'guido', 'jack']
>>> sorted(tel.keys())
['guido', 'irv', 'jack']
>>> 'guido' in tel
True
>>> 'jack' not in tel
False
```
构造函数 dict() 直接从键值对元组列表中构建字典。如果有固定的模式，列表推导式指定特定的键值对：
```
>>> dict([('sape', 4139), ('guido', 4127), ('jack', 4098)])
{'sape': 4139, 'jack': 4098, 'guido': 4127}
```
此外，字典推导可以用来创建任意键和值的表达式词典：
```
>>> {x: x**2 for x in (2, 4, 6)}
{2: 4, 4: 16, 6: 36}
```
如果关键字只是简单的字符串，使用关键字参数指定键值对有时候更方便：
```
>>> dict(sape=4139, guido=4127, jack=4098)
{'sape': 4139, 'jack': 4098, 'guido': 4127}
```
### 13.10 遍历技巧
在字典中遍历时，关键字和对应的值可以使用 items() 方法同时解读出来：
```
>>> knights = {'gallahad': 'the pure', 'robin': 'the brave'}
>>> for k, v in knights.items():
...     print(k, v)
...
gallahad the pure
robin the brave
```
在序列中遍历时，索引位置和对应值可以使用 enumerate() 函数同时得到：
```
>>> for i, v in enumerate(['tic', 'tac', 'toe']):
...     print(i, v)
...
0 tic
1 tac
2 toe
```
同时遍历两个或更多的序列，可以使用 zip() 组合：
```
>>> questions = ['name', 'quest', 'favorite color']
>>> answers = ['lancelot', 'the holy grail', 'blue']
>>> for q, a in zip(questions, answers):
...     print('What is your {0}?  It is {1}.'.format(q, a))
...
What is your name?  It is lancelot.
What is your quest?  It is the holy grail.
What is your favorite color?  It is blue.
```
要反向遍历一个序列，首先指定这个序列，然后调用 reversesd() 函数：
```
>>> for i in reversed(range(1, 10, 2)):
...     print(i)
...
9
7
5
3
1
```
要按顺序遍历一个序列，使用 sorted() 函数返回一个已排序的序列，并不修改原值：
```
>>> basket = ['apple', 'orange', 'apple', 'pear', 'orange', 'banana']
>>> for f in sorted(set(basket)):
...     print(f)
...
apple
banana
orange
pear
```
## Chapter14 Python3 模块
在前面的几个章节中我们脚本上是用python解释器来编程，如果你从Python解释器退出再进入，那么你定义的所有的方法和变量就都消失了。
为此 Python 提供了一个办法，把这些定义存放在文件中，为一些脚本或者交互式的解释器实例使用，这个文件被称为模块。
模块是一个包含所有你定义的函数和变量的文件，其后缀名是.py。模块可以被别的程序引入，以使用该模块中的函数等功能。这也是使用python标准库的方法。下面是一个使用python标准库中模块的例子。
```
#!/usr/bin/python3
# Filename: using_sys.py
 
import sys
 
print('命令行参数如下:')
for i in sys.argv:
    print(i)
 
print('/n/nThe PYTHONPATH is', sys.path, '/n')
```
执行结果如下所示：
```
D:\python36\src>python using_sys.py 参数1 参数2
命令行参数如下:
using_sys.py
参数1
参数2
/n/nThe PYTHONPATH is ['E:\\python33\\src', 'C:\\Windows\\system32\\python33.zip
', 'E:\\python33\\DLLs', 'E:\\python33\\lib', 'E:\\python33', 'E:\\python33\\lib
\\site-packages'] /n
```
- 1、import sys引入python标准库中的sys.py模块；这是引入某一模块的方法。
- 2、sys.argv是一个包含命令行参数的列表。
- 3、sys.path包含了一个Python解释器自动查找所需模块的路径的列表。
当我们使用import语句的时候，Python解释器是怎样找到对应的文件的呢？
这就涉及到Python的搜索路径，搜索路径是由一系列目录名组成的，Python解释器就依次从这些目录中去寻找锁引入的模块。
这看起来很像环境变量，事实上，也可以通过定义环境变量的方式来确定搜索路径。
搜索路径是在Python编译或安装的时候确定的，安装新的库应该也会修改。搜索路径被存储在sys模块中的path变量，做一个简单的实验，在交互式解释器中，输入以下代码：
```
import sys
sys.path
```
输出结果：
```
>>> sys.path
['', 'E:\\python33\\Lib\\idlelib', 'C:\\Windows\\system32\\python33.zip', 'E:\\python33\\DLLs', 'E:\\python33\\lib', 'E:\\python33', 'E:\\python33\\lib\\site-packages']
```
sys.path输出是一个列表，其中第一项是空串''，代表当前目录（若是从一个脚本中打印出来的话，可以更清楚地看出是哪个目录），亦即我们执行python解释器的目录（对于脚本的话就是运行的脚本所在的目录）。
因此若像我一样在当前目录下存在与要引入模块同名的文件，就会把要引入的模块屏蔽掉。
了解了搜索路径的概念，就可以在脚本中修改sys.path来引入一些不在搜索路径中的模块。
现在，在解释器的当前目录或者sys.path中的一个目录里面来创建一个fibo.py的文件，代码如下：
```
# Fibonacci numbers module
 
def fib(n):    # write Fibonacci series up to n
    a, b = 0, 1
    while b < n:
        print(b, end=' ')
        a, b = b, a+b
    print()
 
def fib2(n): # return Fibonacci series up to n
    result = []
    a, b = 0, 1
    while b < n:
        result.append(b)
        a, b = b, a+b
    return result
```
然后进入Python解释器，使用下面的命令导入这个模块：
```
>>> import fibo
```
这样做并没有把直接定义在fibo中的函数名称写入到当前符号表里，只是把模块fibo的名字写到了那里。
可以使用模块名称来访问函数：
```
>>> fibo.fib(1000)
1 1 2 3 5 8 13 21 34 55 89 144 233 377 610 987
>>> fibo.fib2(100)
[1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89]
>>> fibo.__name__
'fibo'
```
如果你打算经常使用一个函数，你可以把它赋给一个本地的名称：
```
>>> fib = fibo.fib
>>> fib(500)
1 1 2 3 5 8 13 21 34 55 89 144 233 377
```
### 14.1 深入模块
模块除了方法定义，还可以包括可执行的代码。这些代码一般用来初始化这个模块。这些代码只有在第一次被导入时才会被执行。
每个模块有各自独立的符号表，在模块内部为所有的函数当作全局符号表来使用。
所以，模块的作者可以放心大胆的在模块内部使用这些全局变量，而不用担心把其他用户的全局变量搞花。
从另一个方面，当你确实知道你在做什么的话，你也可以通过 modname.itemname 这样的表示法来访问模块内的函数。
模块是可以导入其他模块的。在一个模块（或者脚本，或者其他地方）的最前面使用 import 来导入一个模块，当然这只是一个惯例，而不是强制的。被导入的模块的名称将被放入当前操作的模块的符号表中。
还有一种导入的方法，可以使用 import 直接把模块内（函数，变量的）名称导入到当前操作模块。比如:
```
>>> from fibo import fib, fib2
>>> fib(500)
1 1 2 3 5 8 13 21 34 55 89 144 233 377
```
这种导入的方法不会把被导入的模块的名称放在当前的字符表中（所以在这个例子里面，fibo 这个名称是没有定义的）。
这还有一种方法，可以一次性的把模块中的所有（函数，变量）名称都导入到当前模块的字符表:
```
>>> from fibo import *
>>> fib(500)
1 1 2 3 5 8 13 21 34 55 89 144 233 377
```
这将把所有的名字都导入进来，但是那些由单一下划线（ _ ）开头的名字不在此例。大多数情况， Python程序员不使用这种方法，因为引入的其它来源的命名，很可能覆盖了已有的定义。
### 14.2 __name__属性
一个模块被另一个程序第一次引入时，其主程序将运行。如果我们想在模块被引入时，模块中的某一程序块不执行，我们可以用__name__属性来使该程序块仅在该模块自身运行时执行。
```
#!/usr/bin/python3
# Filename: using_name.py
 
if __name__ == '__main__':
    print('程序自身在运行')
else:
    print('我来自另一模块')
```
运行输出如下：
```
$ python using_name.py
```
程序自身在运行
```
$ python
>>> import using_name
我来自另一模块
>>>
```
** 说明 **： 每个模块都有一个__name__属性，当其值是'__main__'时，表明该模块自身在运行，否则是被引入。
### 14.3 dir() 函数
内置的函数 dir() 可以找到模块内定义的所有名称。以一个字符串列表的形式返回:
```
>>> import fibo, sys
>>> dir(fibo)
['__name__', 'fib', 'fib2']
>>> dir(sys) 
['__displayhook__', '__doc__', '__excepthook__', '__loader__', '__name__',
 '__package__', '__stderr__', '__stdin__', '__stdout__',
 '_clear_type_cache', '_current_frames', '_debugmallocstats', '_getframe',
 '_home', '_mercurial', '_xoptions', 'abiflags', 'api_version', 'argv',
 'base_exec_prefix', 'base_prefix', 'builtin_module_names', 'byteorder',
 'call_tracing', 'callstats', 'copyright', 'displayhook',
 'dont_write_bytecode', 'exc_info', 'excepthook', 'exec_prefix',
 'executable', 'exit', 'flags', 'float_info', 'float_repr_style',
 'getcheckinterval', 'getdefaultencoding', 'getdlopenflags',
 'getfilesystemencoding', 'getobjects', 'getprofile', 'getrecursionlimit',
 'getrefcount', 'getsizeof', 'getswitchinterval', 'gettotalrefcount',
 'gettrace', 'hash_info', 'hexversion', 'implementation', 'int_info',
 'intern', 'maxsize', 'maxunicode', 'meta_path', 'modules', 'path',
 'path_hooks', 'path_importer_cache', 'platform', 'prefix', 'ps1',
 'setcheckinterval', 'setdlopenflags', 'setprofile', 'setrecursionlimit',
 'setswitchinterval', 'settrace', 'stderr', 'stdin', 'stdout',
 'thread_info', 'version', 'version_info', 'warnoptions']
```
如果没有给定参数，那么 dir() 函数会罗列出当前定义的所有名称:
```
>>> a = [1, 2, 3, 4, 5]
>>> import fibo
>>> fib = fibo.fib
>>> dir() # 得到一个当前模块中定义的属性列表
['__builtins__', '__name__', 'a', 'fib', 'fibo', 'sys']
>>> a = 5 # 建立一个新的变量 'a'
>>> dir()
['__builtins__', '__doc__', '__name__', 'a', 'sys']
>>>
>>> del a # 删除变量名a
>>>
>>> dir()
['__builtins__', '__doc__', '__name__', 'sys']
>>>
```
### 14.4 标准模块
Python 本身带着一些标准的模块库，在 Python 库参考文档中将会介绍到（就是后面的"库参考文档"）。
有些模块直接被构建在解析器里，这些虽然不是一些语言内置的功能，但是他却能很高效的使用，甚至是系统级调用也没问题。
这些组件会根据不同的操作系统进行不同形式的配置，比如 winreg 这个模块就只会提供给 Windows 系统。
应该注意到这有一个特别的模块 sys ，它内置在每一个 Python 解析器中。变量 sys.ps1 和 sys.ps2 定义了主提示符和副提示符所对应的字符串:
```
>>> import sys
>>> sys.ps1
'>>> '
>>> sys.ps2
'... '
>>> sys.ps1 = 'C> '
C> print('Yuck!')
Yuck!
C>
```
### 14.5 包
包是一种管理 Python 模块命名空间的形式，采用"点模块名称"。
比如一个模块的名称是 A.B， 那么他表示一个包 A中的子模块 B 。
就好像使用模块的时候，你不用担心不同模块之间的全局变量相互影响一样，采用点模块名称这种形式也不用担心不同库之间的模块重名的情况。
这样不同的作者都可以提供 NumPy 模块，或者是 Python 图形库。
不妨假设你想设计一套统一处理声音文件和数据的模块（或者称之为一个"包"）。
现存很多种不同的音频文件格式（基本上都是通过后缀名区分的，例如： .wav，:file:.aiff，:file:.au，），所以你需要有一组不断增加的模块，用来在不同的格式之间转换。
并且针对这些音频数据，还有很多不同的操作（比如混音，添加回声，增加均衡器功能，创建人造立体声效果），所你还需要一组怎么也写不完的模块来处理这些操作。
这里给出了一种可能的包结构（在分层的文件系统中）:
```
sound/                          Top-level package
      __init__.py               Initialize the sound package
      formats/                  Subpackage for file format conversions
              __init__.py
              wavread.py
              wavwrite.py
              aiffread.py
              aiffwrite.py
              auread.py
              auwrite.py
              ...
      effects/                  Subpackage for sound effects
              __init__.py
              echo.py
              surround.py
              reverse.py
              ...
      filters/                  Subpackage for filters
              __init__.py
              equalizer.py
              vocoder.py
              karaoke.py
              ...
```
在导入一个包的时候，Python 会根据 sys.path 中的目录来寻找这个包中包含的子目录。
目录只有包含一个叫做 __init__.py 的文件才会被认作是一个包，主要是为了避免一些滥俗的名字（比如叫做 string）不小心的影响搜索路径中的有效模块。
最简单的情况，放一个空的 :file:__init__.py就可以了。当然这个文件中也可以包含一些初始化代码或者为（将在后面介绍的） __all__变量赋值。
用户可以每次只导入一个包里面的特定模块，比如:
```
import sound.effects.echo
```
这将会导入子模块:mod:song.effects.echo。 他必须使用全名去访问:
```
sound.effects.echo.echofilter(input, output, delay=0.7, atten=4)
```
还有一种导入子模块的方法是:
```
from sound.effects import echo
```
这同样会导入子模块:mod:echo，并且他不需要那些冗长的前缀，所以他可以这样使用:
```
echo.echofilter(input, output, delay=0.7, atten=4)
```
还有一种变化就是直接导入一个函数或者变量:
```
from sound.effects.echo import echofilter
```
同样的，这种方法会导入子模块:mod:echo，并且可以直接使用他的:func:echofilter函数:
echofilter(input, output, delay=0.7, atten=4)
注意当使用from package import item这种形式的时候，对应的item既可以是包里面的子模块（子包），或者包里面定义的其他名称，比如函数，类或者变量。
import语法会首先把item当作一个包定义的名称，如果没找到，再试图按照一个模块去导入。如果还没找到，恭喜，一个:exc:ImportError 异常被抛出了。
反之，如果使用形如import item.subitem.subsubitem这种导入形式，除了最后一项，都必须是包，而最后一项则可以是模块或者是包，但是不可以是类，函数或者变量的名字。
### 14.6 从一个包中导入*
设想一下，如果我们使用 from sound.effects import * 会发生什么？
Python 会进入文件系统，找到这个包里面所有的子模块，一个一个的把它们都导入进来。
但是很不幸，这个方法在 Windows平台上工作的就不是非常好，因为Windows是一个大小写不区分的系统。
在这类平台上，没有人敢担保一个叫做 ECHO.py 的文件导入为模块:mod:echo还是:mod:Echo甚至:mod:ECHO。
（例如，Windows 95就很讨厌的把每一个文件的首字母大写显示）而且 DOS 的 8+3 命名规则对长模块名称的处理会把问题搞得更纠结。
为了解决这个问题，只能烦劳包作者提供一个精确的包的索引了。
导入语句遵循如下规则：如果包定义文件 __init__.py 存在一个叫做 __all__ 的列表变量，那么在使用 from package import * 的时候就把这个列表中的所有名字作为包内容导入。
作为包的作者，可别忘了在更新包之后保证 __all__ 也更新了啊。你说我就不这么做，我就不使用导入 * 这种用法，好吧，没问题，谁让你是老板呢。这里有一个例子，在: file : sounds/effects/__init__.py"中包含如下代码:
```
__all__ = ["echo", "surround", "reverse"]
```
这表示当你使用from sound.effects import * 这种用法时，你只会导入包里面这三个子模块。
如果__all__真的而没有定义，那么使用from sound.effects import * 这种语法的时候，就 * 不会 * 导入包:mod:sound.effects里的任何子模块。他只是把包:mod:sound.effects和它里面定义的所有内容导入进来（可能运行:file:__init__.py里定义的初始化代码）。
这会把 :file:__init__.py里面定义的所有名字导入进来。并且他不会破坏掉我们在这句话之前导入的所有明确指定的模块。看下这部分代码:
```
import sound.effects.echo
import sound.effects.surround
from sound.effects import *
```
这个例子中，在执行from...import前，包:mod:sound.effects中的echo和surround模块都被导入到当前的命名空间中了。（当然如果定义了__all__就更没问题了）
通常我们并不主张使用 * 这种方法来导入模块，因为这种方法经常会导致代码的可读性降低。不过这样倒的确是可以省去不少敲键的功夫，而且一些模块都设计成了只能通过特定的方法导入。
记住，使用from Package import specific_submodule这种方法永远不会有错。事实上，这也是推荐的方法。除非是你要导入的子模块有可能和其他包的子模块重名。
如果在结构中包是一个子包（比如这个例子中对于包:mod:sound来说），而你又想导入兄弟包（同级别的包）你就得使用导入绝对的路径来导入。比如，如果模块:mod:sound.filters.vocoder 要使用包:mod:sound.effects中的模块:mod:echo，你就要写成 from sound.effects import echo。
```
from . import echo
from .. import formats
from ..filters import equalizer
```
无论是隐式的还是显式的相对导入都是从当前模块开始的。主模块的名字永远是"__main__"，一个Python应用程序的主模块，应当总是使用绝对路径引用。
包还提供一个额外的属性，:attr:__path__。这是一个目录列表，里面每一个包含的目录都有为这个包服务的:file:__init__.py，你得在其他:file:__init__.py被执行前定义哦。可以修改这个变量，用来影响包含在包里面的模块和子包。
这个功能并不常用，一般用来扩展包里面的模块。
## Chapter15 Python3 输入和输出
在前面几个章节中，我们其实已经接触了 Python 的输入输出的功能。本章节我们将具体介绍 Python 的输入输出。
### 15.1 输出格式美化
Python两种输出值的方式: 表达式语句 和 print() 函数。(第三种方式是使用文件对象的 write() 方法; 标准输出文件可以用 sys.stdout 引用。)
如果你希望输出的形式更加多样，可以使用 str.format() 函数来格式化输出值。
如果你希望将输出的值转成字符串，可以使用 repr() 或 str() 函数来实现。
str() 函数返回一个用户易读的表达形式。
repr() 产生一个解释器易读的表达形式。
** 例如 **
```
>>> s = 'Hello, world.'
>>> str(s)
'Hello, world.'
>>> repr(s)
"'Hello, world.'"
>>> str(1/7)
'0.14285714285714285'
>>> x = 10 * 3.25
>>> y = 200 * 200
>>> s = 'The value of x is ' + repr(x) + ', and y is ' + repr(y) + '...'
>>> print(s)
The value of x is 32.5, and y is 40000...
>>> # The repr() of a string adds string quotes and backslashes:
... hello = 'hello, world\n'
>>> hellos = repr(hello)
>>> print(hellos)
'hello, world\n'
>>> # The argument to repr() may be any Python object:
... repr((x, y, ('spam', 'eggs')))
"(32.5, 40000, ('spam', 'eggs'))"
```
这里有两种方式输出一个平方与立方的表:
```
>>> for x in range(1, 11):
...     print(repr(x).rjust(2), repr(x*x).rjust(3), end=' ')
...     # Note use of 'end' on previous line 注意前一行 'end' 的使用
...     print(repr(x*x*x).rjust(4))
...
 1   1    1
 2   4    8
 3   9   27
 4  16   64
 5  25  125
 6  36  216
 7  49  343
 8  64  512
 9  81  729
10 100 1000
 
>>> for x in range(1, 11):
...     print('{0:2d} {1:3d} {2:4d}'.format(x, x*x, x*x*x))
...
 1   1    1
 2   4    8
 3   9   27
 4  16   64
 5  25  125
 6  36  216
 7  49  343
 8  64  512
 9  81  729
10 100 1000
```
注意：在第一个例子中, 每列间的空格由 print() 添加。
这个例子展示了字符串对象的 rjust() 方法, 它可以将字符串靠右, 并在左边填充空格。
还有类似的方法, 如 ljust() 和 center()。 这些方法并不会写任何东西, 它们仅仅返回新的字符串。
另一个方法 zfill(), 它会在数字的左边填充 0，如下所示：
```
>>> '12'.zfill(5)
'00012'
>>> '-3.14'.zfill(7)
'-003.14'
>>> '3.14159265359'.zfill(5)
'3.14159265359'
```
str.format() 的基本使用如下:
```
>>> print('We are the {} who say "{}!"'.format('knights', 'Ni'))
We are the knights who say "Ni!"
```
括号及其里面的字符 (称作格式化字段) 将会被 format() 中的参数替换。
在括号中的数字用于指向传入对象在 format() 中的位置，如下所示：
```
>>> print('{0} and {1}'.format('spam', 'eggs'))
spam and eggs
>>> print('{1} and {0}'.format('spam', 'eggs'))
eggs and spam
```
如果在 format() 中使用了关键字参数, 那么它们的值会指向使用该名字的参数。
```
>>> print('This {food} is {adjective}.'.format(
...       food='spam', adjective='absolutely horrible'))
This spam is absolutely horrible.
```
位置及关键字参数可以任意的结合:
```
>>> print('The story of {0}, {1}, and {other}.'.format('Bill', 'Manfred', other='Georg'))
The story of Bill, Manfred, and Georg.
```
'!a' (使用 ascii()), '!s' (使用 str()) 和 '!r' (使用 repr()) 可以用于在格式化某个值之前对其进行转化:
```
>>> import math
>>> print('The value of PI is approximately {}.'.format(math.pi))
The value of PI is approximately 3.14159265359.
>>> print('The value of PI is approximately {!r}.'.format(math.pi))
The value of PI is approximately 3.141592653589793.
```
可选项 ':' 和格式标识符可以跟着字段名。 这就允许对值进行更好的格式化。 下面的例子将 Pi 保留到小数点后三位：
```
>>> import math
>>> print('The value of PI is approximately {0:.3f}.'.format(math.pi))
The value of PI is approximately 3.142.
```
在 ':' 后传入一个整数, 可以保证该域至少有这么多的宽度。 用于美化表格时很有用。
```
>>> table = {'Sjoerd': 4127, 'Jack': 4098, 'Dcab': 7678}
>>> for name, phone in table.items():
...     print('{0:10} ==> {1:10d}'.format(name, phone))
...
Jack       ==>       4098
Dcab       ==>       7678
Sjoerd     ==>       4127
```
如果你有一个很长的格式化字符串, 而你不想将它们分开, 那么在格式化时通过变量名而非位置会是很好的事情。
最简单的就是传入一个字典, 然后使用方括号 '[]' 来访问键值 :
```
>>> table = {'Sjoerd': 4127, 'Jack': 4098, 'Dcab': 8637678}
>>> print('Jack: {0[Jack]:d}; Sjoerd: {0[Sjoerd]:d}; '
          'Dcab: {0[Dcab]:d}'.format(table))
Jack: 4098; Sjoerd: 4127; Dcab: 8637678
```
也可以通过在 table 变量前使用 '*/* ' 来实现相同的功能：
```
>>> table = {'Sjoerd': 4127, 'Jack': 4098, 'Dcab': 8637678}
>>> print('Jack: {Jack:d}; Sjoerd: {Sjoerd:d}; Dcab: {Dcab:d}'.format(**table))
Jack: 4098; Sjoerd: 4127; Dcab: 8637678
```
### 15.2 旧式字符串格式化
% 操作符也可以实现字符串格式化。 它将左边的参数作为类似 sprintf() 式的格式化字符串, 而将右边的代入, 然后返回格式化后的字符串. 例如:
```
>>> import math
>>> print('The value of PI is approximately %5.3f.' % math.pi)
The value of PI is approximately 3.142.
```
因为 str.format() 比较新的函数， 大多数的 Python 代码仍然使用 % 操作符。但是因为这种旧式的格式化最终会从该语言中移除, 应该更多的使用 str.format().
### 15.3 读和写文件
open() 将会返回一个 file 对象，基本语法格式如下:
```
open(filename, mode)
```
实例:
```
>>> f = open('/tmp/workfile', 'w')
```
- 第一个参数为要打开的文件名。
- 第二个参数描述文件如何使用的字符。 mode 可以是 'r' 如果文件只读, 'w' 只用于写 (如果存在同名文件则将被删除), 和 'a' 用于追加文件内容; 所写的任何数据都会被自动增加到末尾. 'r+' 同时用于读写。 mode 参数是可选的; 'r' 将是默认值。
### 15.4 文件对象的方法
本节中剩下的例子假设已经创建了一个称为 f 的文件对象。
#### f.read()
为了读取一个文件的内容，调用 f.read(size), 这将读取一定数目的数据, 然后作为字符串或字节对象返回。
size 是一个可选的数字类型的参数。 当 size 被忽略了或者为负, 那么该文件的所有内容都将被读取并且返回。
```
>>> f.read()
'This is the entire file.\n'
>>> f.read()
''
```
#### f.readline()
f.readline() 会从文件中读取单独的一行。换行符为 '\n'。f.readline() 如果返回一个空字符串, 说明已经已经读取到最后一行。
```
>>> f.readline()
'This is the first line of the file.\n'
>>> f.readline()
'Second line of the file\n'
>>> f.readline()
''
```
#### f.readlines()
f.readlines() 将返回该文件中包含的所有行。
如果设置可选参数 sizehint, 则读取指定长度的字节, 并且将这些字节按行分割。
```
>>> f.readlines()
['This is the first line of the file.\n', 'Second line of the file\n']
```
另一种方式是迭代一个文件对象然后读取每行:
```
>>> for line in f:
...     print(line, end='')
...
This is the first line of the file.
Second line of the file
```
这个方法很简单, 但是并没有提供一个很好的控制。 因为两者的处理机制不同, 最好不要混用。
#### f.write()
f.write(string) 将 string 写入到文件中, 然后返回写入的字符数。
```
>>> f.write('This is a test\n')
15
```
如果要写入一些不是字符串的东西, 那么将需要先进行转换:
```
>>> value = ('the answer', 42)
>>> s = str(value)
>>> f.write(s)
18
```
#### f.tell()
f.tell() 返回文件对象当前所处的位置, 它是从文件开头开始算起的字节数。
#### f.seek()
如果要改变文件当前的位置, 可以使用 f.seek(offset, from_what)函数， from_what 表示开始读取的位置，offset表示从from_what再移动一定量的距离，比如f.seek(10, 3)表示定位到第三个字符并再后移10个字符。
from_what值为0时表示文件的开始，它也可以省略，缺省是0即文件开头。下面给出一个完整的例子：
```
>>> f = open('/tmp/workfile', 'rb+')
>>> f.write(b'0123456789abcdef')
16
>>> f.seek(5)     # 移动到文件的第六个字节
5
>>> f.read(1)
b'5'
>>> f.seek(-3, 2) # 移动到文件的倒数第三字节
13
>>> f.read(1)
b'd'
```
#### f.close()
在文本文件中 (那些打开文件的模式下没有 b 的), 只会相对于文件起始位置进行定位。
当你处理完一个文件后, 调用 f.close() 来关闭文件并释放系统的资源，如果尝试再调用该文件，则会抛出异常。
```
>>> f.close()
>>> f.read()
Traceback (most recent call last):
  File "<stdin>", line 1, in ?
ValueError: I/O operation on closed file
<pre>
<p>
当处理一个文件对象时, 使用 with 关键字是非常好的方式。在结束后, 它会帮你正确的关闭文件。 而且写起来也比 try - finally 语句块要简短:</p>
<pre>
>>> with open('/tmp/workfile', 'r') as f:
...     read_data = f.read()
>>> f.closed
True
```
文件对象还有其他方法, 如 isatty() 和 trucate(), 但这些通常比较少用。
### 15.5 pickle 模块
python的pickle模块实现了基本的数据序列和反序列化。
通过pickle模块的序列化操作我们能够将程序中运行的对象信息保存到文件中去，永久存储。
通过pickle模块的反序列化操作，我们能够从文件中创建上一次程序保存的对象。
基本接口：
```
pickle.dump(obj, file, [,protocol])
```
有了 pickle 这个对象, 就能对 file 以读取的形式打开:
```
x = pickle.load(file)
```
**注解**：从 file 中读取一个字符串，并将它重构为原来的python对象。
**file**: 类文件对象，有read()和readline()接口。
实例1：
```
#使用pickle模块将数据对象保存到文件
 
import pickle
 
data1 = {'a': [1, 2.0, 3, 4+6j],
         'b': ('string', u'Unicode string'),
         'c': None}
 
selfref_list = [1, 2, 3]
selfref_list.append(selfref_list)
 
output = open('data.pkl', 'wb')
 
# Pickle dictionary using protocol 0.
pickle.dump(data1, output)
 
# Pickle the list using the highest protocol available.
pickle.dump(selfref_list, output, -1)
 
output.close()
```
实例2：
```
#使用pickle模块从文件中重构python对象
 
import pprint, pickle
 
pkl_file = open('data.pkl', 'rb')
 
data1 = pickle.load(pkl_file)
pprint.pprint(data1)
 
data2 = pickle.load(pkl_file)
pprint.pprint(data2)
 
pkl_file.close()
```
## Chapter16 Python3 错误和异常
作为Python初学者，在刚学习Python编程时，经常会看到一些报错信息，在前面我们没有提及，这章节我们会专门介绍。
Python有两种错误很容易辨认：语法错误和异常。
### 16.1 语法错误
Python 的语法错误或者称之为解析错，是初学者经常碰到的，如下实例
```
>>> while True print('Hello world')
  File "<stdin>", line 1, in ?
    while True print('Hello world')
                   ^
SyntaxError: invalid syntax
```
这个例子中，函数 print() 被检查到有错误，是它前面缺少了一个冒号（:）。
语法分析器指出了出错的一行，并且在最先找到的错误的位置标记了一个小小的箭头。
### 16.2 异常
即便Python程序的语法是正确的，在运行它的时候，也有可能发生错误。运行期检测到的错误被称为异常。
大多数的异常都不会被程序处理，都以错误信息的形式展现在这里:
```
>>> 10 * (1/0)
Traceback (most recent call last):
  File "<stdin>", line 1, in ?
ZeroDivisionError: division by zero
>>> 4 + spam*3
Traceback (most recent call last):
  File "<stdin>", line 1, in ?
NameError: name 'spam' is not defined
>>> '2' + 2
Traceback (most recent call last):
  File "<stdin>", line 1, in ?
TypeError: Can't convert 'int' object to str implicitly
```
异常以不同的类型出现，这些类型都作为信息的一部分打印出来: 例子中的类型有 ZeroDivisionError，NameError 和 TypeError。
错误信息的前面部分显示了异常发生的上下文，并以调用栈的形式显示具体信息。
### 16.3 异常处理
以下例子中，让用户输入一个合法的整数，但是允许用户中断这个程序（使用 Control-C 或者操作系统提供的方法）。用户中断的信息会引发一个 KeyboardInterrupt 异常。
```
>>> while True:
        try:
            x = int(input("Please enter a number: "))
            break
        except ValueError:
            print("Oops!  That was no valid number.  Try again   ")
```
try语句按照如下方式工作；
- 首先，执行try子句（在关键字try和关键字except之间的语句）
- 如果没有异常发生，忽略except子句，try子句执行后结束。
- 如果在执行try子句的过程中发生了异常，那么try子句余下的部分将被忽略。如果异常的类型和 except 之后的名称相符，那么对应的except子句将被执行。最后执行 try 语句之后的代码。
- 如果一个异常没有与任何的except匹配，那么这个异常将会传递给上层的try中。
一个 try 语句可能包含多个except子句，分别来处理不同的特定的异常。最多只有一个分支会被执行。
处理程序将只针对对应的try子句中的异常进行处理，而不是其他的 try 的处理程序中的异常。
一个except子句可以同时处理多个异常，这些异常将被放在一个括号里成为一个元组，例如:
```
except (RuntimeError, TypeError, NameError):
    pass
```
最后一个except子句可以忽略异常的名称，它将被当作通配符使用。你可以使用这种方法打印一个错误信息，然后再次把异常抛出。
```
import sys
 
try:
    f = open('myfile.txt')
    s = f.readline()
    i = int(s.strip())
except OSError as err:
    print("OS error: {0}".format(err))
except ValueError:
    print("Could not convert data to an integer.")
except:
    print("Unexpected error:", sys.exc_info()[0])
    raise
```
try except 语句还有一个可选的else子句，如果使用这个子句，那么必须放在所有的except子句之后。这个子句将在try子句没有发生任何异常的时候执行。例如:
```
for arg in sys.argv[1:]:
    try:
        f = open(arg, 'r')
    except IOError:
        print('cannot open', arg)
    else:
        print(arg, 'has', len(f.readlines()), 'lines')
        f.close()
```
使用 else 子句比把所有的语句都放在 try 子句里面要好，这样可以避免一些意想不到的、而except又没有捕获的异常。
异常处理并不仅仅处理那些直接发生在try子句中的异常，而且还能处理子句中调用的函数（甚至间接调用的函数）里抛出的异常。例如:
```
>>> def this_fails():
        x = 1/0
    
>>> try:
        this_fails()
    except ZeroDivisionError as err:
        print('Handling run-time error:', err)
    
Handling run-time error: int division or modulo by zero
```
### 16.4 抛出异常
Python 使用 raise 语句抛出一个指定的异常。例如:
```
>>> raise NameError('HiThere')
Traceback (most recent call last):
  File "<stdin>", line 1, in ?
NameError: HiThere
```
raise 唯一的一个参数指定了要被抛出的异常。它必须是一个异常的实例或者是异常的类（也就是 Exception 的子类）。
如果你只想知道这是否抛出了一个异常，并不想去处理它，那么一个简单的 raise 语句就可以再次把它抛出。
```
>>> try:
        raise NameError('HiThere')
    except NameError:
        print('An exception flew by!')
        raise
    
An exception flew by!
Traceback (most recent call last):
  File "<stdin>", line 2, in ?
NameError: HiThere
```
### 16.5 用户自定义异常
你可以通过创建一个新的exception类来拥有自己的异常。异常应该继承自 Exception 类，或者直接继承，或者间接继承，例如:
```
>>> class MyError(Exception):
        def __init__(self, value):
            self.value = value
        def __str__(self):
            return repr(self.value)
    
>>> try:
        raise MyError(2*2)
    except MyError as e:
        print('My exception occurred, value:', e.value)
    
My exception occurred, value: 4
>>> raise MyError('oops!')
Traceback (most recent call last):
  File "<stdin>", line 1, in ?
__main__.MyError: 'oops!'
```
在这个例子中，类 Exception 默认的 __init__() 被覆盖。
当创建一个模块有可能抛出多种不同的异常时，一种通常的做法是为这个包建立一个基础异常类，然后基于这个基础类为不同的错误情况创建不同的子类:
```
class Error(Exception):
    """Base class for exceptions in this module."""
    pass
 
class InputError(Error):
    """Exception raised for errors in the input.
 
    Attributes:
        expression -- input expression in which the error occurred
        message -- explanation of the error
    """
 
    def __init__(self, expression, message):
        self.expression = expression
        self.message = message
 
class TransitionError(Error):
    """Raised when an operation attempts a state transition that's not
    allowed.
 
    Attributes:
        previous -- state at beginning of transition
        next -- attempted new state
        message -- explanation of why the specific transition is not allowed
    """
 
    def __init__(self, previous, next, message):
        self.previous = previous
        self.next = next
        self.message = message
```
大多数的异常的名字都以"Error"结尾，就跟标准的异常命名一样。
### 16.6 定义清理行为
try 语句还有另外一个可选的子句，它定义了无论在任何情况下都会执行的清理行为。 例如:
```
>>> try:
        raise KeyboardInterrupt
    finally:
        print('Goodbye, world!')
    
Goodbye, world!
KeyboardInterrupt
```
以上例子洪不管try子句里面有没有发生异常，finally子句都会执行。
如果一个异常在 try 子句里（或者在 except 和 else 子句里）被抛出，而又没有任何的 except 把它截住，那么这个异常会在 finally 子句执行后再次被抛出。
下面是一个更加复杂的例子（在同一个 try 语句里包含 except 和 finally 子句）:
```
>>> def divide(x, y):
        try:
            result = x / y
        except ZeroDivisionError:
            print("division by zero!")
        else:
            print("result is", result)
        finally:
            print("executing finally clause")
    
>>> divide(2, 1)
result is 2.0
executing finally clause
>>> divide(2, 0)
division by zero!
executing finally clause
>>> divide("2", "1")
executing finally clause
Traceback (most recent call last):
  File "<stdin>", line 1, in ?
  File "<stdin>", line 3, in divide
TypeError: unsupported operand type(s) for /: 'str' and 'str'
```
### 16.7 预定义的清理行为
一些对象定义了标准的清理行为，无论系统是否成功的使用了它，一旦不需要它了，那么这个标准的清理行为就会执行。
这面这个例子展示了尝试打开一个文件，然后把内容打印到屏幕上:
```
for line in open("myfile.txt"):
    print(line, end="")
```
以上这段代码的问题是，当执行完毕后，文件会保持打开状态，并没有被关闭。
关键词 with 语句就可以保证诸如文件之类的对象在使用完之后一定会正确的执行他的清理方法:
```
with open("myfile.txt") as f:
    for line in f:
        print(line, end="")
```
以上这段代码执行完毕后，就算在处理过程中出问题了，文件 f 总是会关闭。
## Chapter17 Python3 类
和其它编程语言相比，Python 在尽可能不增加新的语法和语义的情况下加入了类机制。
Python中的类提供了面向对象编程的所有基本功能：类的继承机制允许多个基类，派生类可以覆盖基类中的任何方法，方法中可以调用基类中的同名方法。
对象可以包含任意数量和类型的数据。
### 17.1 类定义
语法格式如下：
```
class ClassName:
    <statement-1>
    .
    .
    .
    <statement-N>
```
类实例化后，可以使用其属性，实际上，创建一个类之后，可以通过类名访问其属性。
### 17.2 类对象
类对象支持两种操作：属性引用和实例化。
属性引用使用和 Python 中所有的属性引用一样的标准语法：obj.name。
类对象创建后，类命名空间中所有的命名都是有效属性名。所以如果类定义是这样:
```
class MyClass:
    """A simple example class"""
    i = 12345
    def f(self):
        return 'hello world'
```
实例化类：
```
x = MyClass()
```
以上创建了一个新的类实例并将该对象赋给局部变量 x，x 为空的对象。
很多类都倾向于将对象创建为有初始状态的。因此类可能会定义一个名为 __init__() 的特殊方法（构造方法），像下面这样：
```
def __init__(self):
    self.data = []
```
类定义了 __init__() 方法的话，类的实例化操作会自动调用 __init__() 方法。所以在下例中，可以这样创建一个新的实例:
```
x = MyClass()
```
当然， __init__() 方法可以有参数，参数通过 __init__() 传递到类的实例化操作上。例如:
```
>>> class Complex:
...     def __init__(self, realpart, imagpart):
...         self.r = realpart
...         self.i = imagpart
...
>>> x = Complex(3.0, -4.5)
>>> x.r, x.i
(3.0, -4.5)
```
### 17.3 类的方法
在类地内部，使用def关键字可以为类定义一个方法，与一般函数定义不同，类方法必须包含参数self,且为第一个参数:
```
#类定义
class people:
    #定义基本属性
    name = ''
    age = 0
    #定义私有属性,私有属性在类外部无法直接进行访问
    __weight = 0
    #定义构造方法
    def __init__(self,n,a,w):
        self.name = n
        self.age = a
        self.__weight = w
    def speak(self):
        print("%s is speaking: I am %d years old" %(self.name,self.age))
 
 
p = people('tom',10,30)
p.speak()
```
### 17.4 继承
Python 同样支持类的继承，如果一种语言不支持继承就，类就没有什么意义。派生类的定义如下所示:
```
class DerivedClassName(BaseClassName1):
    <statement-1>
    .
    .
    .
    <statement-N>
```
需要注意圆括号中基类的顺序，若是基类中有相同的方法名，而在子类使用时未指定，python从左至右搜索 即方法在子类中未找到时，从左到右查找基类中是否包含方法。
BaseClassName（示例中的基类名）必须与派生类定义在一个作用域内。除了类，还可以用表达式，基类定义在另一个模块中时这一点非常有用:
```
class DerivedClassName(modname.BaseClassName):
```
**实例**
```
#单继承示例
class student(people):
    grade = ''
    def __init__(self,n,a,w,g):
        #调用父类的构函
        people.__init__(self,n,a,w)
        self.grade = g
    #覆写父类的方法
    def speak(self):
        print("%s is speaking: I am %d years old,and I am in grade %d"%(self.name,self.age,self.grade))
s = student('ken',20,60,3)
s.speak()
```
### 17.5 多重继承
Python同样有限的支持多继承形式。多继承的类定义形如下例:
```
class DerivedClassName(Base1, Base2, Base3):
    <statement-1>
    .
    .
    .
    <statement-N>
```
需要注意圆括号中父类的顺序，若是父类中有相同的方法名，而在子类使用时未指定，python从左至右搜索 即方法在子类中未找到时，从左到右查找父类中是否包含方法。
```
#另一个类，多重继承之前的准备
class speaker():
    topic = ''
    name = ''
    def __init__(self,n,t):
        self.name = n
        self.topic = t
    def speak(self):
        print("I am %s,I am a speaker!My topic is %s"%(self.name,self.topic))
 
#多重继承
class sample(speaker,student):
    a =''
    def __init__(self,n,a,w,g,t):
        student.__init__(self,n,a,w,g)
        speaker.__init__(self,n,t)
 
test = sample("Tim",25,80,4,"Python")
test.speak()#方法名同，默认调用的是在括号中排前地父类的方法
```
### 17.6 类私有方法
 __private_method 两个下划线开头，声明该方法为私有方法，不能在类地外部调用。
 
在类的内部调用slef.__private_methods。

类的专有方法：

- __init__ 构造函数，在生成对象时调用
- __del__ 析构函数，释放对象时使用
- __repr__ 打印，转换
- __setitem__按照索引赋值
- __getitem__按照索引获取值
- __len__获得长度
- __cmp__比较运算
- __call__函数调用
- __add__加运算
- __sub__减运算
- __mul__乘运算
- __div__除运算
- __mod__求余运算
- __pow__称方
## Chapter18 Python3 标准库概览
### 18.1 操作系统接口
os模块提供了不少与操作系统相关联的函数。
```
>>> import os
>>> os.getcwd()      # 返回当前的工作目录
'C:\\Python34'
>>> os.chdir('/server/accesslogs')   # 修改当前的工作目录
>>> os.system('mkdir today')   # 执行系统命令 mkdir 
0
```
建议使用 "import os" 风格而非 "from os import * "。这样可以保证随操作系统不同而有所变化的 os.open() 不会覆盖内置函数 open()。
在使用 os 这样的大型模块时内置的 dir() 和 help() 函数非常有用:
```
>>> import os
>>> dir(os)
<returns a list of all module functions>
>>> help(os)
<returns an extensive manual page created from the module's docstrings>
```
针对日常的文件和目录管理任务，:mod:shutil 模块提供了一个易于使用的高级接口:
```
>>> import shutil
>>> shutil.copyfile('data.db', 'archive.db')
>>> shutil.move('/build/executables', 'installdir')
```
### 18.2 文件通配符
glob模块提供了一个函数用于从目录通配符搜索中生成文件列表:
```
>>> import glob
>>> glob.glob('*.py')
['primes.py', 'random.py', 'quote.py']
```
### 18.3 命令行参数
通用工具脚本经常调用命令行参数。这些命令行参数以链表形式存储于 sys 模块的 argv 变量。例如在命令行中执行 "python demo.py one two three" 后可以得到以下输出结果:
```
>>> import sys
>>> print(sys.argv)
['demo.py', 'one', 'two', 'three']
```
### 18.4 错误输出重定向和程序终止
sys 还有 stdin，stdout 和 stderr 属性，即使在 stdout 被重定向时，后者也可以用于显示警告和错误信息。
```
>>> sys.stderr.write('Warning, log file not found starting a new one\n')
Warning, log file not found starting a new one
```
大多脚本的定向终止都使用 "sys.exit()"。
### 18.5 字符串正则匹配
re模块为高级字符串处理提供了正则表达式工具。对于复杂的匹配和处理，正则表达式提供了简洁、优化的解决方案:
```
>>> import re
>>> re.findall(r'\bf[a-z]*', 'which foot or hand fell fastest')
['foot', 'fell', 'fastest']
>>> re.sub(r'(\b[a-z]+) \1', r'\1', 'cat in the the hat')
'cat in the hat'
```
如果只需要简单的功能，应该首先考虑字符串方法，因为它们非常简单，易于阅读和调试:
>>> 'tea for too'.replace('too', 'two')
'tea for two'
### 18.6 数学
math模块为浮点运算提供了对底层C函数库的访问:
```
>>> import math
>>> math.cos(math.pi / 4)
0.70710678118654757
>>> math.log(1024, 2)
10.0
```
random提供了生成随机数的工具。
```
>>> import random
>>> random.choice(['apple', 'pear', 'banana'])
'apple'
>>> random.sample(range(100), 10)   # sampling without replacement
[30, 83, 16, 4, 8, 81, 41, 50, 18, 33]
>>> random.random()    # random float
0.17970987693706186
>>> random.randrange(6)    # random integer chosen from range(6)
4
```
### 18.7 访问互联网
有几个模块用于访问互联网以及处理网络通信协议。其中最简单的两个是用于处理从 urls 接收的数据的 urllib.request 以及用于发送电子邮件的 smtplib:
```
>>> from urllib.request import urlopen
>>> for line in urlopen('http://tycho.usno.navy.mil/cgi-bin/timer.pl'):
...     line = line.decode('utf-8')  # Decoding the binary data to text.
...     if 'EST' in line or 'EDT' in line:  # look for Eastern Time
...         print(line)
 
<BR>Nov. 25, 09:43:32 PM EST
 
>>> import smtplib
>>> server = smtplib.SMTP('localhost')
>>> server.sendmail('soothsayer@example.org', 'jcaesar@example.org',
... """To: jcaesar@example.org
... From: soothsayer@example.org
...
... Beware the Ides of March.
... """)
>>> server.quit()
```
注意第二个例子需要本地有一个在运行的邮件服务器。
### 18.8 日期和时间
datetime模块为日期和时间处理同时提供了简单和复杂的方法。
支持日期和时间算法的同时，实现的重点放在更有效的处理和格式化输出。
该模块还支持时区处理:
```
>>> # dates are easily constructed and formatted
>>> from datetime import date
>>> now = date.today()
>>> now
datetime.date(2003, 12, 2)
>>> now.strftime("%m-%d-%y. %d %b %Y is a %A on the %d day of %B.")
'12-02-03. 02 Dec 2003 is a Tuesday on the 02 day of December.'
 
>>> # dates support calendar arithmetic
>>> birthday = date(1964, 7, 31)
>>> age = now - birthday
>>> age.days
14368
```
### 18.9 数据压缩
以下模块直接支持通用的数据打包和压缩格式：zlib，gzip，bz2，zipfile，以及 tarfile。
```
>>> import zlib
>>> s = b'witch which has which witches wrist watch'
>>> len(s)
41
>>> t = zlib.compress(s)
>>> len(t)
37
>>> zlib.decompress(t)
b'witch which has which witches wrist watch'
>>> zlib.crc32(s)
226805979
```
### 18.10 性能度量
有些用户对了解解决同一问题的不同方法之间的性能差异很感兴趣。Python 提供了一个度量工具，为这些问题提供了直接答案。
例如，使用元组封装和拆封来交换元素看起来要比使用传统的方法要诱人的多,timeit 证明了现代的方法更快一些。
```
>>> from timeit import Timer
>>> Timer('t=a; a=b; b=t', 'a=1; b=2').timeit()
0.57535828626024577
>>> Timer('a,b = b,a', 'a=1; b=2').timeit()
0.54962537085770791
```
相对于 timeit 的细粒度，:mod:profile 和 pstats 模块提供了针对更大代码块的时间度量工具。
### 18.11 测试模块
开发高质量软件的方法之一是为每一个函数开发测试代码，并且在开发过程中经常进行测试
doctest模块提供了一个工具，扫描模块并根据程序中内嵌的文档字符串执行测试。
测试构造如同简单的将它的输出结果剪切并粘贴到文档字符串中。
通过用户提供的例子，它强化了文档，允许 doctest 模块确认代码的结果是否与文档一致:
```
def average(values):
    """Computes the arithmetic mean of a list of numbers.
 
    >>> print(average([20, 30, 70]))
    40.0
    """
    return sum(values) / len(values)
 
import doctest
doctest.testmod()   # 自动验证嵌入测试
```
unittest模块不像 doctest模块那么容易使用，不过它可以在一个独立的文件里提供一个更全面的测试集:
```
import unittest
 
class TestStatisticalFunctions(unittest.TestCase):
 
    def test_average(self):
        self.assertEqual(average([20, 30, 70]), 40.0)
        self.assertEqual(round(average([1, 5, 7]), 1), 4.3)
        self.assertRaises(ZeroDivisionError, average, [])
        self.assertRaises(TypeError, average, 20, 30, 70)
 
unittest.main() # Calling from the command line invokes all tests
```
