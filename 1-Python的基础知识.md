# Python 的基础知识

速度过一遍。

其实 Python 这门语言还挺简单，语言特性基本和 JavaScript 一个叼样，所以说那么简单我他妈还不如学Python，JavaScript 太烦了，ES6 / ES7 / ES8 那么多玩意还不如搞 Python 一劳永逸。

##  `print()` 是一个和 `console.log()` 一模一样的东西

通常，我们用 JavaScript 打印东西的时候，会用到 `console.log()` 。

```javascript
console.log('holy crap')
```

那用 Python 打印，是用 `print()` 。

```python
print('holy crap')
```

我的经验告诉我，`print()` 这个玩意和 `console.log()` 一样，是 debug 最好的办法。把觉得有问题的地方都打印一遍。

## 字符串和数字

```python
'holy crap'
123456
```

和 JavaScript 一样的逻辑。

## 变量

JavaScript 有 `var` / `const` / `let` 

现在看起来 Python 可以之间定义，只用赋值就可以了。

```python
people = 'frankietang'
print(people)
```

也是自上到下运行，重新定义的值会直接覆盖掉。

```python
salary = 3500
salary = 0
print('your salary:' + str(salary))
```

## `input()`

`input()` 是一个新玩意。就是可以把你在终端输入的东西给获取出来。类似事件？也不太像。

可以获取到用户输入的东西。

```python
happen = input('What\'s happening?')
print('Suggestions:' + happen)
```

## `str()` , `int()` , `float()` , `type()` , `len()`

字符串同样是要用 `\` 来转义，或者 `""` 

```python
test = 'What\'s happening?'
test = "What's happening"
```

| 转义字符    | 描述                                     |
| ----------- | ---------------------------------------- |
| \(在行尾时) | 续行符                                   |
| \\          | 反斜杠符号                               |
| \'          | 单引号                                   |
| \"          | 双引号                                   |
| \a          | 响铃                                     |
| \b          | 退格(Backspace)                          |
| \e          | 转义                                     |
| \000        | 空                                       |
| \n          | 换行                                     |
| \v          | 纵向制表符                               |
| \t          | 横向制表符                               |
| \r          | 回车                                     |
| \f          | 换页                                     |
| \oyy        | 八进制数yy代表的字符，例如：\o12代表换行 |
| \xyy        | 十进制数yy代表的字符，例如：\x0a代表换行 |
| \other      | 其它的字符以普通格式输出                 |

不会直接查，不用记。

`type()` 就是看属性的，也不用记。

```python
test = '123'
print(type(test)) # <type 'str'>
```

`len()` 看长度的。

```python
print(len('123')) # 3
```

整数是 `int()` ，没有小数点的那种。

浮点数是 `float()` ，有小数点的那种。

```python
play = str(int(input('你每天看片的时间？'))*7)
print('您一周玩手机' + play + '小时')
```

就是可以一直转类型，多少层都可以。

## 条件语句

就是 if 和 else，还有一个 elif

```python
num = 1
if num < 0 :
    print(num + 1)
else :
    print(num - 1)
    
# 0
x = 1
if x > 1:
    print ('x > 1')
elif x < 1:
    print('x < 1')
else:
    print('x = 1')

# 1
```

## 布尔值

就是 Ture 和 False

其中Python把 0 、空字符串 '' 和 None 看成 False，其他数值和非空字符串都看成 True 。

“与”“或”“非”三种运算
 **与运算**：只有两个布尔值都为 True 时，计算结果才为 True。
 **或运算**：只要有一个布尔值为 True，计算结果就是 True。
 **非运算**：把True变为False，或者把False变为True。

and 和 or 运算的一条重要法则：短路计算

```python
a = True
print a and 'a = T' or 'a = F'
#输出为“a = T”
```

1. 在计算 a and b 时， a 是 True，则整个计算结果必定取决与 b，因此返回 b。
2. 在计算 a or b 时， a 是 True，则根据或运算法则，整个计算结果必定为 True，因此返回 a。

所以 Python 解释器在做布尔运算时，只要能提前确定计算结果，它就不会往后算了，直接返回结果。

## `whlie`，`break`，`continue`，`exit()`

while 是循环，break 是结束，continue 是不再执行下面的语句，回到 while 。

```python
while True:
  a1=input('认罪吗？请回答认罪或者不认')
  a2=input('认罪吗？请回答认罪或者不认')
  if a1 == '认罪' and a2 == '认罪':
    print('两人都得判10年，唉')
  elif a1 == '不认' and a2 == '认罪':
    print('a1判20年，a2判1年，唉')
  elif a1 == '认罪' and a2 == '不认':
    print('a1判1年，a2判20年')
  else:
    print('都判3年，太棒了')
    break
    
# 认罪吗？请回答认罪或者不认不认
# 认罪吗？请回答认罪或者不认认罪
# a1判20年，a2判1年，唉
# 认罪吗？请回答认罪或者不认认罪
# 认罪吗？请回答认罪或者不认认罪
# 两人都得判10年，唉
# 认罪吗？请回答认罪或者不认认罪
# 认罪吗？请回答认罪或者不认不认
# a1判1年，a2判20年
# 认罪吗？请回答认罪或者不认不认
# 认罪吗？请回答认罪或者不认不认
# 都判3年，太棒了
```

`exit()` 也可以结束循环

```python
a = 0
while True:
    a = a + 1
    if a == 2:
        exit()
print(a)
```

## 列表

举个例子

```python
list = [1,2,3,[4,5],6]
print(list[1]) # 2
print(list[3][1]) # 5
print(list[-1]) # 6
print(list[0:4]) # [1, 2, 3, [4, 5]]
print(list[1:3]) # [2, 3]
print(list[1:]) # [2, 3, [4, 5], 6]
print(list[:2]) # [1, 2]
```

插入数据用 `append()`

```python
list = [1,2,3,[4,5],6]
list.append(7)
print(list) # [1, 2, 3, [4, 5], 6, 7]
```

## 字典

其实就是 key 和 value 的意思。

举个例子，这个是字典包列表

```python
dict = {a:['甲','乙','丙'],b:['A','B','C']}
print(dict[1][0]) # 甲
print(dict[1]) # ['甲','乙','丙']
```

还有列表包字典

```python
list = [{1:'甲'},{2:'乙'},{3:'丙'}]
print(list[1][2]) # 乙
print(list[1]) # {2: '乙'}
```

## for 循环

和 JavaScript 同理

```python
a = [1,2,3]
for i in a:
    print(i) # 123
```

其实就是等于

```python
a = [1,2,3]
i = a[0]       #把列表a里面的第0个数据放到i里面
print(i)
i = a[1]       #把列表a里面的第1个数据放到i里面
print(i)
i = a[2]       #把列表a里面的第2个数据放到i里面
print(i)
```

如果要从字典里面取值，用下面这种操作

```python
dict = {'a':1,'b':2,'c':3,'d':4}
for i in dict :
    print(i+':'+str(dict[i]))

# a:1
# b:2
# c:3
# d:4
```

还有一个叫 `range()` 可以生成整数数列

```python
for i in range(3):
    print(i) # 012

for i in range(13,17):
    print(i) # 13，14，15，16

for i in range(3):
    print('a') # aaa
```

## 函数

和 `funtion()` 同理

```python
def people(name):
    print(name+'早上好')

people('邓嘉麟')
```

`return()` 也不太难理解，例如下面这个例子，就是返回了一个字符串

```python
def age(i):
    if i < 12:
        return '是小朋友啊'
    elif i < 18:
        return '是少年啊'
    else:
        return '嗯，永远18岁'

n = age(30)
print(n)
```

这里同样也有作用域这个概念，这里就不多加叙述了。其实可以理解为，外部是公交车，人人可以上，内部是私家车，私人可以上。

## try...except...

看一个例子

```python
num = [0,1,2,3]
for x in num:
    try:
    #尝试执行下列代码
        print (6/x)
        #使用6除以num中的元素，并输出
    except ZeroDivisionError:
    #除非发生ZeroDivisionError报错，执行下列代码：
        print('0是不能做除数的！')
        #打印“0是不能做除数的！”
        
# 0是不能做除数的！
# 6.0
# 3.0
# 2.0
```

就是错误后也运行，不过会抛出自己的写的异常。

还有一个 pass，就是直接跳过，执行下一轮循环。

```python
num = [0,1,2,3]
for x in num:
    try:
        print (6/x)
    except :
        pass

# 6.0
# 3.0
# 2.0
```

1. except后面什么也不跟，直接加冒号。意味着，只要报错就执行下面的代码，不管是什么错误类型。
2. 报错后执行的代码，你也可以只写一个'pass'，'pass'的意思就是：什么都不做。'pass'的存在意义是占个位，维护格式完整。比如except语句后面要求你要执行点什么报错后的程序，但你又什么都不想执行，那就pass好了。

## `encode()` , `decode()` , `ord()` , `chr()`

decode 的作用是将其他编码的字符串转换成 unicode 编码，如`str1.decode('gb2312')`，表示将 gb2312 编码的字符串转换成 unicode 编码。

encode 的作用是将 unicode 编码转换成其他编码的字符串，如`str2.encode('gb2312')`，表示将 unicode 编码的字符串转换成 gb2312 编码。  

`ord()`函数主要用来返回对应字符的 ascii 码，`chr()`主要用来表示 ascii 码对应的字符他的输入时数字，可以用十进制，也可以用十六进制。

```python
print('邓嘉麟'.encode('gbk'))
print(b'\xb5\xcb\xbc\xce\xf7\xeb'.decode('gbk'))
print(ord('麟'))
print(chr(40607))
```

## `open()` 方法

Python open() 方法用于打开一个文件，并返回文件对象，在对文件进行处理过程都需要使用到这个函数，如果该文件无法被打开，会抛出 OSError。

**注意：**使用 open() 方法一定要保证关闭文件对象，即调用 close() 方法。

open() 函数常用形式是接收两个参数：文件名(file)和模式(mode)。

```
open(file, mode='r')
```

完整的语法格式为：

```
open(file, mode='r', buffering=-1, encoding=None, errors=None, newline=None, closefd=True, opener=None)
```

参数说明:

- file: 必需，文件路径（相对或者绝对路径）。
- mode: 可选，文件打开模式
- buffering: 设置缓冲
- encoding: 一般使用utf8
- errors: 报错级别
- newline: 区分换行符
- closefd: 传入的file参数类型
- opener:

mode 参数有：

| 模式 | 描述                                                         |
| ---- | ------------------------------------------------------------ |
| t    | 文本模式 (默认)。                                            |
| x    | 写模式，新建一个文件，如果该文件已存在则会报错。             |
| b    | 二进制模式。                                                 |
| +    | 打开一个文件进行更新(可读可写)。                             |
| U    | 通用换行模式（不推荐）。                                     |
| r    | 以只读方式打开文件。文件的指针将会放在文件的开头。这是默认模式。 |
| rb   | 以二进制格式打开一个文件用于只读。文件指针将会放在文件的开头。这是默认模式。一般用于非文本文件如图片等。 |
| r+   | 打开一个文件用于读写。文件指针将会放在文件的开头。           |
| rb+  | 以二进制格式打开一个文件用于读写。文件指针将会放在文件的开头。一般用于非文本文件如图片等。 |
| w    | 打开一个文件只用于写入。如果该文件已存在则打开文件，并从开头开始编辑，即原有内容会被删除。如果该文件不存在，创建新文件。 |
| wb   | 以二进制格式打开一个文件只用于写入。如果该文件已存在则打开文件，并从开头开始编辑，即原有内容会被删除。如果该文件不存在，创建新文件。一般用于非文本文件如图片等。 |
| w+   | 打开一个文件用于读写。如果该文件已存在则打开文件，并从开头开始编辑，即原有内容会被删除。如果该文件不存在，创建新文件。 |
| wb+  | 以二进制格式打开一个文件用于读写。如果该文件已存在则打开文件，并从开头开始编辑，即原有内容会被删除。如果该文件不存在，创建新文件。一般用于非文本文件如图片等。 |
| a    | 打开一个文件用于追加。如果该文件已存在，文件指针将会放在文件的结尾。也就是说，新的内容将会被写入到已有内容之后。如果该文件不存在，创建新文件进行写入。 |
| ab   | 以二进制格式打开一个文件用于追加。如果该文件已存在，文件指针将会放在文件的结尾。也就是说，新的内容将会被写入到已有内容之后。如果该文件不存在，创建新文件进行写入。 |
| a+   | 打开一个文件用于读写。如果该文件已存在，文件指针将会放在文件的结尾。文件打开时会是追加模式。如果该文件不存在，创建新文件用于读写。 |
| ab+  | 以二进制格式打开一个文件用于追加。如果该文件已存在，文件指针将会放在文件的结尾。如果该文件不存在，创建新文件用于读写。 |

默认为文本模式，如果要以二进制模式打开，加上 b 。

### file 对象

file 对象使用 open 函数来创建，下表列出了 file 对象常用的函数：

| 序号 | 方法及描述                                                   |
| ---- | ------------------------------------------------------------ |
| 1    | [file.close()](http://www.runoob.com/python/file-close.html)关闭文件。关闭后文件不能再进行读写操作。 |
| 2    | [file.flush()](http://www.runoob.com/python/file-flush.html)刷新文件内部缓冲，直接把内部缓冲区的数据立刻写入文件, 而不是被动的等待输出缓冲区写入。 |
| 3    | [file.fileno()](http://www.runoob.com/python/file-fileno.html)返回一个整型的文件描述符(file descriptor FD 整型), 可以用在如os模块的read方法等一些底层操作上。 |
| 4    | [file.isatty()](http://www.runoob.com/python/file-isatty.html)如果文件连接到一个终端设备返回 True，否则返回 False。 |
| 5    | [file.next()](http://www.runoob.com/python/file-next.html)返回文件下一行。 |
| 6    | [file.read([size\])](http://www.runoob.com/python/python-file-read.html)从文件读取指定的字节数，如果未给定或为负则读取所有。 |
| 7    | [file.readline([size\])](http://www.runoob.com/python/file-readline.html)读取整行，包括 "\n" 字符。 |
| 8    | [file.readlines([sizeint\])](http://www.runoob.com/python/file-readlines.html)读取所有行并返回列表，若给定sizeint>0，则是设置一次读多少字节，这是为了减轻读取压力。 |
| 9    | [file.seek(offset[, whence\])](http://www.runoob.com/python/file-seek.html)设置文件当前位置 |
| 10   | [file.tell()](http://www.runoob.com/python/file-tell.html)返回文件当前位置。 |
| 11   | [file.truncate([size\])](http://www.runoob.com/python/file-truncate.html)截取文件，截取的字节通过size指定，默认为当前文件位置。 |
| 12   | [file.write(str)](http://www.runoob.com/python/python-file-write.html)将字符串写入文件，返回的是写入的字符长度。 |
| 13   | [file.writelines(sequence)](http://www.runoob.com/python/file-writelines.html)向文件写入一个序列字符串列表，如果需要换行则要自己加入每行的换行符。 |

举个例子

```python
# -*- coding: UTF-8 -*-

# file1 = open('./abc.txt','r') # 只读
# filecontent = file1.read()
# print(filecontent)
# file1.close()

# file1 = open('./abc.txt','w') # 覆盖
# file1.write('张无忌\n')
# file1.write('宋青书\n')

file1 = open('./abc.txt','a') # 添加
file1.write('张无忌\n')
file1.write('宋青书\n')
file1.close()
```

abc.txt 就长这个样子

```
周芷若
赵敏
张无忌
宋青书
```

## `split()` 和 `join()`

`join()` 链接字符串

`split()` 拆分字符串

```python
test1=['a','b','c']
print('-'.join(test1)) # a-b-c
test2='a b c'
print(test2.split(' ')) # ['a','b','c']
```
