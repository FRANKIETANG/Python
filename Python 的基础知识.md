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

## `whlie`，`break`，`continue`

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

