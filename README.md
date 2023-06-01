# python-basics
python conclution
# 一.总结python语法不同点

## 1.1 三元表达式的不同 a if a > b else b

````python
a, b = 5, 6
print(a if a > b else b)
````

## 1.2 取整数不同 // 

```python
a, b = 5, 6
print(a // b)
```

## 1.3 True == 1  False == 0

```python
print(True, False)
```

## 1.4 && 用 and || 用 or ! 用 not 

```python
print(not 1 == 2 and 2 > 3 or 3 != 4)
```

## 1.5 循环只有 while 和 for 循环

## 1.6 for 循环的用法与 js 的forin 及其类似 

```python
for i in range(101):
    print(i)
```

## 			1.7 python 会使用切片

​			

```python
string = 'abajncdjnc'

# 语法 起始 结束 步长 含头不含尾
print(string[1])
print(string[1:6])
print(string[::6])
print(string[1:2:2])
```

## 1.8 python类型转换会使用函数转换

```python
a = 1

type(a)
str(a)
int(a)
tuple(a)
list(a)
# 万金油
eval(a)
# ......

```

## 1.9 python 中变量 列表 元祖等 可以存 不同类型的数据 

# 二 . python 的常用操作 或 常用 函数

## 2.1 字符串

### 2.1.1 编码解码

```python
a = '测试'
print(a)
a1 = a.encode()
print(a1)
a2 = a1.decode()
print(a2)
```

### 2.1.2 常见操作

```python
# find() 寻找、检测：检测字符是否包含在字符串中，如果是的话就会返回开始位置所在的下标\索引值，否则返回-1
# def find(self, sub, start=None, end=None):
a = 'hello world'
print(a.find('d'))  # 10  返回的下标开始位置
print(a.find('a'))  # -1  找不到
print(a.find('l', 5))  # 9  指定从哪个下标开始寻找

# count():返回字符在字符串中出现的次数
# def count(self, sub, start=None, end=None):
a = 'ziyi ziyi'
print(a.count('i'))  # 2次
print(a.count('z'))  # 1次
print(a.count('z', 3))  # 1次 指定从哪个下标开始寻找

# replace()替换：将字符串中的旧的内容换成新的内容，并且还可以指定替换次数。
# replace(旧的内容，新的内容，替换次数)
# def replace(self, *args, **kwargs):
a = 'hello python'
print(a.replace('l', '&'))  # he&&o python
print(a.replace('l', '&', 1))  # he&lo python  1代表替换次数

# split()分割:以指定的字符去切割字符串,如果有指定分割次数，只分割指定的次数，并把后面的字符串作为一个整体分割
# def split(self, *args, **kwargs):
a = 'hel,lo,py,th,on'
print(a.split(','))  # ['hel', 'lo', 'py', 'th', 'on']
print(a.split(',', 1))  # ['hel', 'lo', 'py,th,on']

# index():和find作用一样，找得到就会返回开始位置得下标，找不到会报错
a = 'hello python'
# def index(self, sub, start=None, end=None):
print(a.index('t'))  # 8
print(a.index('t', 9))  # 找不到报错

# capitalize():把字符串第一个字符大写
a = 'ziyi'
print(a.capitalize())  # Ziyi

# startswith():是否以某字符开头,是就返回True 不是返回False
a = 'hello'
print(a.startswith('he'))  # False

# endswith()是否以某字符结束，是就返回True 不是返回False
a = 'world'
print(a.endswith('w'))  # False
print(a.endswith('d'))  # True

# lower():将字符串中的大写转为小写
# upper():将字符串中的小写转为大写
a = 'ziyi HELLO'
print(a.lower())
print(a.upper())


str1 = '哈哈#嘻嘻#嘿嘿#咳咳'
print(str1.split('#'))
```



## 2.2 列表 

### 2.2.1列表的 定义 

```python
print(list([1, 2, 3]))
lis = [1, 2, 3]
print(lis)
```

### 2.2.2 列表常用方法

```python
# 1、添加元素：
# append():整体添加
# extend():分散添加
# insert():在指定的位置前插入
li = ['a', 'b', 'c']
li.append([1, 2, 3])
li.append('123')  # ['a', 'b', 'c', '123']
li.extend('123')  # ['a', 'b', 'c', '1', '2', '3']
li.insert(2, 'ziyi')  # ['a', 'b', 'ziyi', 'c']
print(li)

# 2、修改元素：
# 通过下标修改
li = ['a', 'b', 'c']
print(li[0])
li[0] = '恣意'  # 通过下标修改了值
print(li)


# 3、查找元素：
# in:如果存在返回True
# not in：如果不存在返回True
# index()  count() 和字符串里面的用法一模一样
li = [1, 'a', 'b', '2', 1, 1]
print('a' in li)  # True
print('a' not in li)  # False
print(li.index('3'))
print(li.count(1))  # 3

# 4、删除元素：
# del
# pop()
# remove()
# clear()
li = [1, 'a', 'b', '2', 1, 1]
# print(li)
del li[0]  # 根据下标删除，0是下标
del li  # 删除了整个列表
li.pop()  # 删除最后一个元素
li.pop(2)  # 删除下标为2的元素
li.remove('a')  # 根据元素值来删除
li.clear()  # 清空了列表中的所有元素
print(li)

# 5、排序：
# sort():默认从小到大排序  参数：reverse=True改边顺序
li = [1, 3, 2, 5, 4]
print('之前的:', li)
# li.sort()
li.sort(reverse=True)  # 从小到大的逆置
print('之后的：', li)

# reverse():将列表的元素逆置
li = [1, 3, 2, 5, 4]
print(li)
li.reverse()
print(li)


# 列表推导式
# [表达式 for 变量 in 列表]
li = []
for i in range(1, 6):
    li.append(i)
print(li)

print([i for i in range(1, 6)])


# [表达式 for 变量 in 列表 if 条件]
li = []
for i in range(1, 6):
    if i % 2 == 0:
        li.append(i)
print(li)

print([i for i in range(1, 6) if i % 2 == 0])
#
li1 = [i for i in range(1, 6) if i % 2 == 0]
print(li1)
```

## 2.3 元祖

### 	2.3.1 元祖的定义

```python
tu = ()
tu = (1, 2, 3)

string = 'abc'
tuple(string)

tu[0]

```



### 	2.3.2 元祖的常用操作

```python
# 元组的相关操作 
# index：检测元素是否存在元组中，存在就返回第一个匹配的下标，不存在就报错
'''
解释说明 元祖初始化后 数据为常量 不支持改动操作 
当然 可以理解 为java 或者 C++/C# 的 enum 枚举类即可
'''
tu = ('a', 'b', 'c', 'd')
print(tu)
print(tu.index('c'))  # 2下标
print(tu.index('c', 3))  # 找不到就会报错
# count:统计元素出现的次数
tu = ('a', 'b', 'c', 'd', 'd', 'd')
print(tu.count('a'))  # 1次
print(tu.count('d'))  # 3次
```



## 2.4 字典 

### 	2.4.1 字典的定义 

```python
dic = {'key': 'value', 1: 123}
li = [(1, 2), ('q', '9')]
dict(li)
```

### 	2.4.2 字典的常用操作

```python
# 字典的键是具有唯一性，不可以重复
# 值可以重复
# dic = {'name': '恣意', 'name1': '恣意'}  # name就是键   '恣意'值
# print(dic)

# dic = {'name1': '恣意', 'name2': '林非'}
# print(dic[0])  # 报错  字典不能通过下标来访问元素

# 字典是通过键名来访问元素的
# print(dic['name1'])  # 恣意
# print(dic['name2'])  # 林非
# print(dic['name3'])  # 访问的如果是不存在键，就会报错


# 当你不确定某个键是不是存在的时候，但是又想获取
# dic = {'name1': '恣意', 'name2': '林非'}
# print(dic.get('age'))  # None --- 不存在

# ad = dic.get('age', '不存在')
# print(ad)

# 查看元素
# dic = {'name1': '恣意', 'name2': '林非'}
# # 变量名[键名]
# print(dic['name1'])
# # 变量名.get(键名)
# print(dic.get('name2'))

# 修改元素
# dic = {'name1': '恣意', 'name2': '林非'}
# print(dic['name1'])  # 通过key找到元素
# dic['name1'] = '晚汐'
# dic['name2'] = '楸.'
# print(dic)

# 添加元素
# 变量名['键'] = 数据  --- 不存在则新增
# dic = {'name1': '恣意', 'name2': '林非'}
# dic['age'] = '张三'  # 键存在就修改，如果键不存在就新增
# print(dic)


# 删除元素
# del删除指定的元素
# clear()清空整个字典
# dic = {'name1': '恣意', 'name2': '林非', 'age': '张三'}
# del dic  # 删除整个字典
# dic.clear()  # {} 清空了字典
# print(dic)

# len():返回键值对的个数
# dic = {'name1': '恣意', 'name2': '林非'}
# print(len(dic))  # 2对

# keys():返回一个字典中包含的所有的key键的列表
# dic = {'name1': '恣意', 'name2': '林非', 'age': 18, 'sex': '女'}
# print(dic.keys())  # ['name1', 'name2', 'age', 'sex']

# values():返回包含字典所有value值的列表
# dic = {'name1': '恣意', 'name2': '林非', 'age': 18, 'sex': '女'}
# print(dic.values())  # ['恣意', '林非', 18, '女']

# items():返回包含所有（键，值)元组的列表
# dic = {'name1': '恣意', 'name2': '林非', 'age': 18, 'sex': '女'}
# print(dic.items())  # [('name1', '恣意'), ('name2', '林非'), ('age', 18), ('sex', '女')]
# print(dic)

```



## 2.5 集合 	

### 	2.5.1 集合的定义 

```python
# 集合
# a = {1, 2, 3, 4}
# print(a)

# b = {}  # 空的代表的是字典
# print(type(a))  # <class 'set'> 集合
# print(type(b))  # <class 'dict'> 字典

# 集合的元素具有唯一性 --- 具有去重功能
# a = {1, 2, 3, 4, 2, 3, 4}
# print(a)  # {1, 2, 3, 4}

# 去重、集合还是无序的
# a = {1, 2, 'a', 1.5, '恣意', 'a', '恣意'}
# print(a)
# print(type(a))  # <class 'set'>

str1 = 'abcdefg'
print(set(str1))
```



### 	2.5.2 集合的常用操作 

```python
# 1、添加元素：
# add:整体添加-----append整体
# update：拆分添加-----extend拆分
# a = {2, 4, 3, 5, 1}
# print(a)  # 自动排序---从小到大
# # a.add(6)
# a.add('abd')
# a.update('cef')
# print(a)

# 2、删除元素：
# remove
# pop
# discard
# a = {'a', 'b', 'c'}
# print(a)
# a.remove('a')  # 指定元素移除
# a.pop()  # pop会先对集合无序排列，然后删除左边第一个元素
# a.discard('3')  # 和remove方法用法完全相同
# print(a)

# set1 = {1, 2, 3}
# set2 = {3, 4, 5}
# # 交集&：取两个集合公共的元素
# # 并集|：取两个集合全部的元素
# print(set1 & set2)  # {3}
# print(set1 | set2)  # {1, 2, 3, 4, 5}
```



## 2.6 小总结

2.6.1列表 可看做数组

2.6.2字典 可看做 哈希表

2.6.3集合 可看做 只有 key 没 value 的哈希表 

​	集合 的 交集 与集  用 | 和 & 

2.6.4元祖可看做 一个 常量数组 

2.6.5深浅拷贝 使用的是 copy 函数库 copy（） 和 deepcopy（）

​	与vue 的深度 监视 有异曲同工之妙

# 三. 一个py文件搞定函数

## 3.1 函数定义 

```python
def a():
    pass
```



## 3.2 函数的参数 

```python
# 返回值
def a():
    return 2

def b():
    return  # 返回none


# 参数
def c(a, b):
    print(a + b)
    
def c(a=1, b=3): # 默认值
    print(a + b)

# 不定长参数
def e(a, *args):
    print(a)
    # args 为元祖
    print(args)

 # 2.关键字参数：**kwargs：接受所有的关键字参数然后将其转换成一个字典赋值给kwargs这个形参
def fun1(**kwargs):
    print(kwargs)
    print(type(kwargs))


fun1(name='张三', age=18)  # <class 'dict'>   


# 函数嵌套 
def f():
    e(1, 123)

# 函数变量作用域
def g():
    global a # 这里将a定于为全局变量
    a = 10
    b = 3
    def h ():
        nonlocal b # 这里使用的是外层函数的变量
        b = 9
        print(b)
    h()
    print(a)
    print(b)
 
# 匿名函数
# lambda 形参 : 返回值
i = lambda a, b: a ** b

print(i(1, 2))

# 查看所有的内置函数
import builtins
print(dir(builtins))

# zip():把几个数组对齐,然后按列输出---元组的形式
# 按符合条件的数组输出,多出的元素就不匹配
a = [1, 2, 3, 4]
b = ['a', 'b', 'c']
print(list(zip(a, b)))  # [(1, 'a'), (2, 'b'), (3, 'c')]

# reduce():对参数序列中元素进行累积
# reduce(函数地址, 可迭代对象)
from functools import reduce
def funa(x, y):
    return x + y


res = reduce(funa, [1, 2, 3, 4])
print(res)

# res = reduce(lambda x, y: x+y, [1, 2, 3, 4])
# print(res)


# 函数拆包
'''
拆包: 对于函数中的多个返回数据, 去掉元组, 列表 或者字典 直接获取里面数据的过程。
下面为例子

每个迭代的值 =  可迭代对象

'''
a, b, c = (10, 20, 30)
print(a)
print(b)
print(c)

def test.txt():
     a = 1
     b = 2
     c = 3
     return a, b, c
 print(test.txt())  # (1, 2, 3)
 a, b, c = test.txt()
 print(a)
 print(b)
 print(c)


# 拆包时需要注意的是,需要拆包的数据个数要和变量的个数相同,否则就会报错
tu = (1, 2, 3)
a, b, c= tu
print(a)
print(b)

li = [1, 2, 3, 4, 5, 6]
a, *b = li
print(a)
print(b)

dic = {'name': '张三', 'age': 18, 'sex': '男'}
a, *b = dic
print(a, b)
# 字典拆包获取的是key值,而不是value值
```

## 3.3 包的使用

```python
# 语法1
import 包名.模块名 as xxx

包名.模块名.方法 即可

xxx.方法也可

# 语法2

from 包 import 模块/* #引入全部 或单个 模块

# from  包名  import  *
# 模块名 . 目标
# __all__变量：是一个列表，可以在模块中和__init__中用的
# __all__变量是配合 form  包名  import  * 语法来用的，  用来控制*要引入的东西
# 语法：__all__ = ['模块名']
# from package01 import *
# class01.fun1()
# class02.fun1()

# 在包的__init__.py 文件中定义 __all__ = ['class01', 'class02']

```

## 3.4 异常的处理

```python
try:
    1 == 2 # 业务代码执行
except Exception as e:
    print(e) # 异常代码执行 
else:
    print("无问题") # 没异此处代码执行 可不要 
finally:
    print("结束") # 最终代码执行 可不要 可以和
    
    # except finally 最少取一个 
    # 但是 不要 except 就不能要 else 
```



## 3.5 递归函数

```python
# 递归函数的特性：
# 1.必须要有一个结束的条件
# 2.每次进入更深一层的递归的时候，问题规模都要比前一次有所减少
# 3.相邻的两次递归之间会有紧密的联系，前一次都要为后一次做打算
# 4.递归的层次超过了最大的深度就会报错

def a(n):
    if n == 1:
        return 1
    return n + a(n - 1)


print(a(10))
```

## 3.6 闭包 +回调函数搞定  装饰器



```python
# 闭包的构成条件：
# 1.函数中嵌套一个函数
# 2.内层嵌套函数对外部作用域有一个非全局变量的引用
# 3.外层函数的返回值是内层函数的函数名
# 作用：保存局部信息不被销毁，保准数据安全

def a():
    b = 3

    def c():
        d = b + 1
        print(d)

    return c


# c() = 调用a函数获得c函数地址在进行调用
a()()


# 回调函数：
# 自身就是一个函数，只是被传到了其它的函数供其调用

def funa(func):
    print(func(2))
    print('回调函数的使用')


funa(lambda a: a + 1)

# 装饰器

def a(b):
    def c():
        print("进入到c啦")
        print(b("q"), "b函数被调用了")
        print("这里是C哦")

    return c


a(lambda q: "b")()


def f(b):
    def g(k):
        print(f"收到函数{k}")
        print("进入到g啦")
        print(b("q"), "b函数被调用了")
        print("这里是g哦")

    return g


@f
def h(q):  # 这里是 调用 形参的b函数 (业务增强代码) 
    return "收到q"


h(1)  # 这里是 是调用g
```





