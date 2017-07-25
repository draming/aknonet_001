[学习资料from廖雪峰的官方网站](https://www.liaoxuefeng.com/wiki/0014316089557264a6b348958f449949df42a6d3a2e542c000)

- 启动python解释器：在命令行下输入`python3`
- 退出python解释器：在命令行下输入`exit()`

- 运行python程序：进入.py文件所在目录，运行`python xx.py`命令

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
  

#### input 与 raw_input
这两个函数均能接收字符串 ，但raw_input() 直接读取控制台的输入（任何类型的输入它都可以接收）。
而对于input() ，它希望能够读取一个合法的 python 表达式，即你输入字符串的时候必须使用引号将它括起来，否则它会引发一个 SyntaxError 。

#为什么print输出时会出现单引号呢？？？待解决
```
name = raw_input('please input your name:')
print('hello,', name)
```
输出是这个样子的。。。
```
yuanyuandeMacBook-Pro:python nancyliao$ python hello.py
please input your name:nancy
('hello,', 'nancy')
```
