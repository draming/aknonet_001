[学习参考资料——廖雪峰的官方网站](https://www.liaoxuefeng.com/wiki/0014316089557264a6b348958f449949df42a6d3a2e542c000)

[python内置函数](https://docs.python.org/3/library/functions.html)

#### 基础

- 启动python解释器：在命令行下输入`python3`
- 退出python解释器：在命令行下输入`exit()`

- 运行python程序：进入.py文件所在目录，运行`python xx.py`命令  
  **特别注意，如果要运行python3，则需要使用`python3 xx.py`命令，否则已然是系统预装的python2.x，在运行结果上有差异，比如除法结果2只取整数，3才是浮点数**

- 直接运行.py文件：windows上不可以，mac和linux可以，方法如下：
  1. 在.py文件开头增加特殊的注释`#!usr/bin/env python3` 
  
  系统看到时，先到env设置里查找python的安装路径，再调用对应路径下的解释器程序完成操作。
  
  2. 通过命令`chmod a+x xx.py`给文件以权限
  
  chmod：文件/目录权限设置命令，其语法格式为：chmod [who] [opt] [mode] 文件/目录名 
  u：表示文件所有者 
  g：表示同组用户 
  o：表示其它用户 
  a：表示所有用户 
  opt则是代表操作，可以为： 
  +：添加某个权限 
  -：取消某个权限 
  =：赋予给定的权限，并取消原有的权限 
  而mode则代表权限： 
  r：可读 
  w：可写 
  x：可执行 
  
  3. 通过命令`./xx.py`运行
  
----

#### input 与 raw_input
这两个函数均能接收字符串 ，但raw_input() 直接读取控制台的输入（任何类型的输入它都可以接收）。
而对于input() ，它希望能够读取一个合法的 python 表达式，即你输入字符串的时候必须使用引号将它括起来，否则它会引发一个 SyntaxError 。
**后来发现，上述问题是python2下的问题，python3里压根没有raw_input**

----

#### 代码文件里面有中文时，需要在文件开头加上如下代码
```
#!/usr/bin/env python3   
# -*- coding: utf-8 -*-
```
- 第一行注释是为了告诉Linux/OS X系统，这是一个Python可执行程序，Windows系统会忽略这个注释；
- 第二行注释是为了告诉Python解释器，按照UTF-8编码读取源代码，否则，你在源代码中写的中文输出可能会有乱码。
- 申明了UTF-8编码并不意味着你的.py文件就是UTF-8编码的，必须并且要确保文本编辑器正在使用UTF-8 without BOM编码

----

#### 转义符
- 转义字符\，比如\n表示换行，\t表示制表符，字符\本身也要转义，所以\\表示的字符就是\
- 如果字符串里面有很多字符都需要转义，就需要加很多\，为了简化，Python还允许用r''表示''内部的字符串默认不转义
  `print(r'\\\t\\')`
  
  输出`\\\t\\`
- '''...'''的格式表示多行内容
  ```
  print('''line1
  line2
  line3''')
  ```
  
    输出
    ```
    line1
    line2
    line3
    ```

----


#### 大小写敏感，切忌切忌～～～

----

#### 关于除法

- “/”的结果为浮点数，哪怕是两个整数相除
- “//”只取结果的整数部分
- “%”得到两个整数相除的余数

----

#### 如果提示str和int类型不匹配，用int()将string转为int类型

----

#### 格式化
- 用%来格式化字符串，在字符串内部，%s表示用字符串替换，%d表示用整数替换，有几个%?占位符，后面就跟几个变量或者值，顺序要对应好。如果只有一个%?，括号可以省略。
  1. %d	整数；  %05d表示总长度为5且长度不足5的在前面补0；%5d表示总长度为5前面不补0；如果总长度超过5则全部显示
  2. %f	浮点数； %.2f表示保留小数后2位，如果原本是整数则在小数点后补2个0
  3. %s	字符串
  4. %x	十六进制整数
  5. %% 表示一个%
```
s1 = input('please input last year score:')
s2 = input('please input this year score:')
s1 = int(s1)
s2 = int(s2)
s = (s2-s1)*100/s1
s = '成绩增长百分比为：%.2f%%' % s
print(s)

a = 's1 is %.3f, s2 is %04d' % (s1, s2)
print(a)
```
输出：
```
please input last year score:72
please input this year score:85
成绩增长百分比为：18.06%
s1 is 72.000, s2 is 0085
```

#### list & tuple
- list: 
```
classmates = ['Michael', 'Bob', 'Tracy']
#返回list的元素个数
len(classmates)  
#返回list的某个元素的值，从0开始，最后一个元素也可以表示为-1，倒数第二个-2，依次类推
classmates[0]
#在list最后追加一个元素
classmates.append('Adam')
#把元素插入到指定的位置，比如索引号为1的位置
classmates.insert(1, 'Jack')
返回['Michael', 'Jack', 'Bob', 'Tracy', 'Adam']
#要删除list末尾的元素
classmates.pop()
#要删除指定位置的元素，用pop(i)方法，其中i是索引位置
#要把某个元素替换成别的元素，可以直接赋值给对应的索引位置
classmates[1] = 'Sarah'

```
list元素也可以是另一个list，借以实现二维数组，类似的还可以实现三维、思维数组等，不过较少用到

- tuple:
和list非常类似，但是tuple一旦初始化就不能修改;因为tuple不可变，所以代码更安全。如果可能，能用tuple代替list就尽量用tuple。
```
classmates = ('Michael', 'Bob', 'Tracy')
```

#### python没有&&和||运算符，取而代之的是英文and和or～～～

#### for...in循环和while循环。break语句可以在循环过程中直接退出循环，而continue语句可以提前结束本轮循环，并直接开始下一轮循环。

#### 死循环时可以用Ctrl+C退出程序，或者强制结束Python进程。

-----

#### dict
- dict格式，数据初始化方式  a = {'key1':value1, 'key2':value2}  就是key:value的方式存储
- 还可以通过key放入 a['key1'] = value1
- 判断key是否存在的2种方法：1）'key1' in a 返回True或False；2）a.get('key1') 不存在返回None
- 删除一个key，对应的value也同时被删除 a.pop('key1')
- dict查找和插入的速度极快，不会随着key的增加而变慢；需要占用大量的内存，内存浪费多。list刚好相反。dict是用空间来换取时间的一种方法。
- dict的key必须是不可变对象。这是因为dict根据key来计算value的存储位置，如果每次计算相同的key得出的结果不同，那dict内部就完全混乱了。这个通过key计算位置的算法称为哈希算法（Hash）。
- **请务必注意，dict内部存放的顺序和key放入的顺序是没有关系的。**


#### set
- 和dict类似，也是一组key的集合，但不存储value。由于key不能重复，所以，在set中，没有重复的key。
- 要创建一个set，需要提供一个list作为输入集合：s = set(['a', 'b', 'c'])
- **请务必注意，set是无序的。例如上例，输出是b c a的顺序**
- 重复元素在set中自动被过滤
- 通过add增加元素，remove移除元素
- set可以看成数学意义上的无序和无重复元素的集合，因此，两个set可以做数学意义上的交集(&)、并集(|)等操作


#### 函数
- 内置函数isinstance用来判断变量类型，例如：isinstance(a,(int,str))，返回True或False
- 可以定义可变参数，参数可以是多个甚至0个，在参数名前面加＊，参数接收到后组装成一个tuple，在list或tuple前面加＊作为参数则意味着把list或tuple所有元素传入
- 可以定义关键字参数，在参数名前面加＊＊，参数接收到后组装成一个dict，反过来，在dict名前面加＊＊作为参数传入则意味着把所有dict元素传入
- 在Python中定义函数，可以用必选参数、默认参数、可变参数、关键字参数和命名关键字参数，这5种参数都可以组合使用。但是请注意，参数定义的顺序必须是：必选参数、默认参数、可变参数、命名关键字参数和关键字参数。





