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



# 四. 面向对象编程



## 4.1 类的定义

```python
'''
此处要注意 ，类名要遵循驼峰命名法还有命名规则
class A():
	pass
'''
```



## 4.2 对象属性的查看、定义和删除

```python
# 在类的外部添加
class B():
    
    def(self):
        print("什么也不做")
b = B()
b.f = 9
b.c = "......"

# 获取属性
print(b.f,b.c)

# 在类的内部添加
class A(object):

    def __init__(self):
        self.q = None

    def B(self):
        self.q = '.....'

# init 理解为类的构造方法即可

# 删除对象属性可以用del

# 对象查询所有的对象中的属性：对象.__dict__
        
```

## 4.3 对象的部分魔法方法

```python
# def __XXXX__(self):
class A(object):

    def __init__(self):
        self.q = None
        print("在类初始化的时候调用")

    def __del__(self):
        print("在类被删除的时候调用")

    def __str__(self):
        print("打印对象信息,理解为toString()即可")
```



## 4.4 类的继承

```python
# 单继承
class Parent(object):

    def P(self):
        print("这是父类")


class Son(Parent):

    def S(self):
        print("这是子类")


s = Son()
s.P()
s.S()
print("============以上单继承================")


# 多继承

class Grandson(Son, Parent):
    pass


gs = Grandson()

gs.P()
gs.S()
print("============以上多继承================")
```



## 4.5 类的私有属性，私有方法的使用

```
class Person(object):
    name = '张三'
    _age = 18
    __sex = '男'  # 私有静态属性

    def __pri(self):
        print("私有的方法")

    def d(self):
        self.__pri()
        print(self.__sex)
        print("调用类的私有方法和私有熟悉")


p = Person()

print(p.name)

# 访问私有属性
print(p._age)
# 这样访问会报错
# print(p.__sex)
print(p._Person__sex)

# 访问私有方法,在类中写一个方法供人调用即可
p.d()

```





## 4.6 重写父类方法

```python
# 定义师傅类
class Master(object):
    def __init__(self):
        self.gongfu = '师傅的功夫'

    def make_cake(self):
        print(f'{self.gongfu}顶呱呱')


# 学校类
class School(object):
    def __init__(self):
        self.gongfu = '学校的功夫'

    def make_cake(self):
        print(f'{self.gongfu}顶呱呱')


# 徒弟类:继承了师傅类和学校类
class Student(School, Master):
    def __init__(self):
        super().__init__()
        self.gongfu = '自己的功夫'

    def make_cake(self):
        self.__init__()
        print(f'{self.gongfu}顶呱呱')

    def make_master_cake(self):
        Master.__init__(self)
        Master.make_cake(self)

    def make_school_cake(self):
        School.__init__(self)
        School.make_cake(self)


# 子类创建对象
ziji = Student()
ziji.make_cake()
ziji.make_master_cake()
ziji.make_school_cake()
```



## 4.7 类的多态

```python
# 多态实现步骤：
# 定义⽗类，并提供公共⽅法
# 定义⼦类，并重写⽗类⽅法
# 传递⼦类对象给调⽤者，可以看到不同⼦类执⾏效果不同

# 需求：警务人员和警犬一起工作，警犬分两种：追击敌人和追查毒品，携带不同的警犬，执行不同的工作。
"""
1.定义父类,提供公共方法： 警犬 和 人
2.定义子类，子类重写父类的方法：定义2种不同的类代表不同的警犬
3.创建对象，调用不同的功能，传入不同的对象，观察执行的结果
"""


class Dog(object):  # 警犬
    def work(self):  # 父类提供公共方法，哪怕是空方法
        pass


class ArmyDog(Dog):  # 继承了Dog
    def work(self):  # 重写了父类同名方法
        print('追击敌人')


class DrugDog(Dog):  # 继承了Dog
    def work(self):  # 重写了父类同名方法
        print('追查毒品')


# 定义人类
class Person(object):
    def wrok_with_dog(self, dog):  # 传入不同的对象，执行不同的代码，--不同的work()
        # 调用的逻辑都一样，执行结果不同
        dog.work()


ad = ArmyDog()
# ad.work()
dd = DrugDog()
# dd.work()

p = Person()
p.wrok_with_dog(ad)
p.wrok_with_dog(dd)

# 多态性：定义统一的接口，一个接口，多种实现

```



## 4.8 类的静态方法和类方法

```python
# 类方法：针对类对象定义的方法
class Person(object):
    __age = 18

    # 类方法
    @classmethod
    def print_info(cls):
        print(cls.__age)


p = Person()
p.print_info()
Person.print_info()


class Person(object):
    age = 18

    # 类方法
    @classmethod
    def get_age(cls):
        return cls.age

    @classmethod
    def set_age(cls, age):
        cls.age = age


p = Person()
print(p.get_age())
print(Person.get_age())

p.set_age(20)
print(p.get_age())
print(Person.get_age())



###################################静态方法####################################
class Dog(object):
    @staticmethod
    def info():
        # 不需要访问实例对象也不需要访问类对象
        return '这是一个狗类'
```

## 4.9 方法的总结

>1. 实例的方法，方法需要去访问实例属性
>2. 类方法，方法内部只需要访问类属性
>3. 静态方法，方法内部不需要访问类和实例属性



## 4.10 单例模式

```py
class Aa(object):
    pass


a = Aa()
print(id(a))
b = Aa()
print(id(b))


# new 方法实现
class Manager(object):
    def __new__(cls, *args, **kwargs):
        # 1.创建对象的时候，new方法会被自动调用
        print(cls)
        # 重写new方法就一定要return super().__new__(cls)
        # 否则python解释器得不到分配空间的对象引用，就不会调用对象的初始化方法
        # 注意：__new__方法是一个静态方法，在调用的时候要传cls，不传就会报错
        # 2.super().__new__(cls)为对象分配空间
        # 3.返回对象的引用
        return super().__new__(cls)

    def __init__(self):
        self.soft = '大脑'

    def this_run(self):
        print(self.soft, '正在运行')


m = Manager()
print(m)
print(m.soft)
m.this_run()


# 1、定义一个类属性，初始值是None，用于记录单例对象的引用
# 2、重写__new__方法
# 3、如果类属性is None，调用父类方法分配空间，并在类属性中记录结果
# 4、返回类属性中记录的对象引用
class Manager(object):
    ins = None  # 1、定义一个类属性，初始值是None，用于记录单例对象的引用

    def __new__(cls, *args, **kwargs):  # 2、重写__new__方法
        if cls.ins is None:  # 3.1判断类属性是否为空
            cls.ins = super().__new__(cls)  # 3.2为空就把父类的new方法返回的对象的引用给类属性
        # 4、返回类属性中记录的对象引用
        return cls.ins

    def __init__(self):
        self.soft = '大脑'

    def this_run(self):
        print(self.soft, '正在运行')


#  单理模式要实现的效果就是：每一次实例化创建的对象都是同一个，内存地址相同
m = Manager()
print(m)
print(m.soft)
m2 = Manager()
print(m2)

# 类方法实现
class Sing(object):
    ins = None  # 类属性是属于类的，不论哪个对象都会有，不用等实例之后在创建

    @classmethod
    def get_ins(cls):
        if cls.ins is None:
            cls.ins = object.__new__(cls)  # object和super()用法一样
        return cls.ins


a = Sing.get_ins()  # 第一次
b = Sing.get_ins()  # 第二次
print(id(a))
print(id(b))


```

## 4.11 new方法 和 init 方法的关系

```python
# 使用类名()创建对象时，python解释器会做两件事情：
# 第一件事情，调用__new__方法为对象分配空间。
# 第二件事情，__init__对对象进行初始化。

class Person(object):
    def __init__(self):
        print('这里是init方法')

    def __new__(cls, *args, **kwargs):
        print('这里是new方法')


p1 = Person()
print(p1)  # None
# 因为子类的new方法覆盖了父类(基类)的new方法，所以没办法为对象分配空间，所以不会执行init为对象初始化


class Person(object):
    def __init__(self):  # 3.利用这个实例对象来调用init方法，上一步new方法产生的实例就是self
        print('这里是init方法')  # 4.执行init里面的代码

    def __new__(cls, *args, **kwargs):  # 1.先执行new方法中的代码
        print('这里是new方法')
        return super().__new__(cls)  # 2.new方法返回Person的实例，返回值是一个实例对象(返回给init方法)


p1 = Person()
print(p1)

```

## 4.12 魔术方法

```python
# 查看内置魔法方法
class Aa(object):
    pass


print(dir(Aa))


# __call__：允许一个类的实例像函数一样被调用
class Aa(object):
    def __init__(self):
        print('这里是init')

    def __call__(self, *args, **kwargs):
        print('这里是call')


a = Aa()  # 这里是init
a()  # 这里是call
Aa()()  # 这里是init 这里是call


# __repr__：改变对象的字符串显示
class A(object):
    def __repr__(self):
        return '你好'  # 返回值：必须有的，还一定要是字符串


a = A()
print(a)


# __dict__：查看类或对象中的所有属性
class A(object):
    sex = '男'

    def __init__(self, name, age):
        self.name = name
        self.age = age

    def __repr__(self):
        return '你好'  # 返回值：必须有的，还一定要是字符串


# 获取类的属性----方法和属性
print(A.__dict__)

# __doc__：表示类的描述信息
print(A.__doc__)


class A(object):
    """表示类的描述信息"""

    def funa(self):
        print(11111)


print(A.__doc__)

```



# 五.文件

## 5.1 文件方法简要概述

```python
# open 方法的定义
def open(file, mode='r', buffering=None, encoding=None, errors=None, newline=None, closefd=True): 
    pass

    'r'       open for reading (default)
    'w'       open for writing, truncating the file first
    'x'       create a new file and open it for writing
    'a'       open for writing, appending to the end of the file if it exists
    'b'       binary mode
    't'       text mode (default)
    '+'       open a disk file for updating (reading and writing)
    'U'       universal newline mode (deprecated)

```

## 5.2文件方法的使用

```python
# 打开文件 读 关闭
# 1.打开--open()
f = open('test.txt', 'r', encoding='utf-8')  # open函数会返回一个文件对象  encoding='utf-8'
print(f)  # 打印文件对象

# 2.读read
# print(f.read())  # 1234567890
print(f.read(5))  # 有参数的话代表的是读取的数据的字节单位，不写默认读取所有

# 3.关闭close
f.close()


# 访问模式对写入write()的影响

# r : 如果文件不存在会报错，不支持写入操作，表示只读
f = open('test.txt.txt', 'r')
f.write('AAA')  # 报错不能写
# print(f.read())
f.close()

# w : 写入，如果存在，对文件进行写的操作的时候或覆盖原来的内容
f = open('test.txt.txt', 'w')
# f.read()  # 报错 不能读
f.write('abcd')
f.close()

# a : 追加，如果文件不存在会新建文件，文件存在在原有的内容上追加新的内容
f = open('test.txt.txt', 'a')
f = open('test11.txt', 'a')
f.write('张三')
f.close()


# b: 二进制模式(可以和其他的模式组合)
# +: 读写模式(可以和其他的模式组合)


# readline() 方法可以一次读取一行内容，方法执行后，会把 文件指针移动到下一行，准备再次读取
f = open('test.txt.txt', 'r')
while True:
    test.txt = f.readline()
    if not test.txt:  # 判断是否读取到内容
        break
    print(test.txt)  # 每读取一行末尾已经有了一个\n
f.close()


# seek()
# 文件对象.seek(偏移量,起始位置)
f = open('test.txt.txt', 'a+')
# 起始位置:    0：文件开头 1：当前位置  2：文件结尾
f.seek(0, 0)
print(f.read())
f.close()


f = open('test.txt.txt', 'r')
try:
    f.read()
finally:
    f.close()

# with表达式其实是try-finally的简写形式。但是又不是全相同。
# errors='ignore'   ignore:代表忽略
with open('test.txt.txt', 'r', errors='ignore', encoding='utf-8') as f:
    print(f.read())
# with表达式相当于默认有一个f.close()，这里的f文件会自动关闭

```

## 5.3 目录的操作

```python
import os
# os 是操作系统模块，不同操作系统有不同的指令，以下方法只是替换命令行的指令操作而已
# rename(src,dst)：重命名文件或目录
os.rename("原名", "新名")
os.rename('test11.txt', 'test.txt')


# remove(path)：删除路径为path的文件
os.remove("test.txt")


# mkdir(path)：创建一个名为path的文件夹
os.mkdir("test")

# getcwd()：返回当前工作目录
print(os.getcwd())


# listdir(path)：返回path指定的文件夹包含的文件或文件夹的名字的列表
print(os.listdir())  # 获取当前的目录列表
print(os.listdir('../'))  # 获取当前的目录列表

# rmdir(path)：删除path指定的空目录
os.rmdir("test")
```

# 六.迭代器、生成器

## 6.1 迭代器和可迭代对象

```python
# 可迭代对象和迭代器
# Iterator 迭代器   Iterable 可迭代对象
# 可以for循环的都是属于可迭代对象
# 可以next()的都是迭代器
from collections.abc import Iterable, Iterator
# str1 = 'ZhangSan'  # 字符串
# print(isinstance(str1, Iterable))  # True  是可迭代对象
# print(isinstance(str1, Iterator))  # False  不是迭代器
# # 迭代器对象一定是一个可迭代对象， 可迭代对象不一定是一个迭代器
#
# 可迭代对象而已通过方法变成迭代器
# # __iter__()方法：可以返回一个迭代器对象
# it = str1.__iter__()
# print(isinstance(it, Iterable))  # True  是可迭代对象
# print(isinstance(it, Iterator))  # True  是迭代器

# st = 'ZhangSan'
# it = st.__iter__()  # 返回迭代器
# # 手动迭代，__next__方法会自动找到下一个元素
# print(it.__next__())  # z
# print(it.__next__())  # i
# print(it.__next__())  # y
# print(it.__next__())  # o
# print(it.__next__())  # 报错 StopIteration
# 为什么for循环迭代就不回报错：因为for循环内部抛出了一个StopIteration异常

# for循环工作原理
# 	1.在内部对可迭代对象调用__iter__方法，获取到迭代器对象
#   2.再一次次的通过迭代器对象调用__next__方法获取迭代结果


# iter()：iter()函数获取这些可迭代对象的迭代器 (和__iter__一样)
# next()：next()函数来获取下⼀条数据(和__next__一样)
# li = [1, 2, 3, 4]  # 列表是可迭代对象
# # 创建迭代器对象
# it = iter(li)  # 1.通过iter()方法变成了迭代器
# # print(it)
# # 输出迭代器的下一个元素
# print(next(it))  # 使用next对迭代器不断的获取下一个元素
# print(next(it))
# print(next(it))
# print(next(it))
# print(next(it))  # 去完了元素再取的话，就会报错StopIteration
```

### 利用类实现自定义迭代器


```python
# 创建一个返回数字的迭代器，初始值为0， 逐步递增1
from collections.abc import Iterable,Iterator
# 定义类
# class Aa():
#     def __init__(self):
#         self.n = 0  # 初始值=0
#     # 1.成为可迭代对象,重写iter方法
#     def __iter__(self):
#         return self  # 返回的是当前对象的实例
#     # 2.重写next方法,让他去找到每一条数据不断地调用next方法
#     def __next__(self):
#         # 3.不设立停止条件的话就会一直循环造成死循环
#         if self.n == 10:  # 设立停止的条件
#             raise StopIteration  # 抛出异常
#         self.n += 1
#         return self.n
# a = Aa()
# # 是可迭代对象也是迭代器
# print(isinstance(a, Iterable))
# print(isinstance(a, Iterator))
# for i in a:
#     print(i)



"""
迭代器实现字符串的逆序输出
n = 'python' -  nohtyp  n[0]=p  n[1]=y
len(n) = 6  n[6-1]= n  自减1
1.创建一个字符串n   下标i
2.重写iter方法,返回一个迭代器对象
3.重写next方法,不断地调用拿到下一个值   ---抛出一个异常
"""
# class str_num():
#     def __init__(self, n):
#         self.n = n
#         self.i = len(n)
#     def __iter__(self):
#         return self
#     def __next__(self):
#         if self.i == 0:
#             raise StopIteration
#         self.i -= 1
#         return self.n[self.i]
#
# b = str_num('python')
# for i in b:
#     print(i)
```



## 6.2 生成器

```python
# 生成器

# 1.生成器表达式:类似于列表推导式
# li = [i for i in range(5)]  # 列表推导式
# print(li)
# # 生成器表达式只需要把[]改成()
li2 = (i for i in range(5))  # 生成器表达式
print(li2)  # generator生成器  <generator object <genexpr> at 0x0000019E8D321660>
print(next(li2))  # 0
print(next(li2))  # 1
print(next(li2))  # 2
for i in li2:
    print(i)


# 2.生成器函数:
def funa():
    print('张三')
    # return 1
    yield 1
    yield 2
    yield 3


fn = funa()  # 调用了一个生成器函数,返回的是一个生成器对象
print(fn)  # 1
print(next(fn))  # 2
print(next(fn))  # 3
print(next(fn))  # StopIteration



a = [100, 60, 40, 20, 10, 0]
b = [0.01, 0.015, 0.03, 0.05, 0.075, 0.1]


# 生成器函数
def f(x):
    for i in range(len(a)):
        if n > a[i]:
            # 生成器推导式
            c = (a[j] - a[j + 1] for j in range(i, len(a) - 1))
            print(c)
            print(list(c))
            break
    r = sum(map(lambda x, y: x * y, b[i:], [(n - a[i])] + list(c)))
    print([(n - a[i])] + list(c))
    yield r * 10000


k = int(input("是否继续计算奖金？是：1， 否：0\n"))
while k:
    n = int(input('请输入利润，单位(万元):'))
    print('应发奖金为:', next(f(n)), '(元)')
    print()
    k = int(input("是否继续计算奖金？是：1， 否：0\n"))
print('感谢使用，程序结束！')
```





# 七.进程、线程、协程（纤程）

## 7.1 进程

```python
from multiprocessing import Process


# def __init__(self, group=None, target=None, name=None, args=(), kwargs={},
#              *, daemon=None):

def fun():
    print('test')


if __name__ == '__main__':
    th = Process(target=fun)
    th.start()
    print(th.is_alive())
    th.join(2)
    print(th.name)
```

>进程与进程之间全局变量不共享，所以他们的缓存空间是不一致的
>
>进程之前的通信可以借用队列来实现
>
>```python
>from multiprocessing import Process, Queue
>```
>
>进程池
>
>```python
># 1.导入Pool
>from multiprocessing import Pool
>import time
>
>
># 2.定义一个函数，模拟进程执行任务
>def work(n):
>    print('test')
>    time.sleep(1)
>    return n
>
>
>if __name__ == '__main__':
>    p = Pool(4)  # 创建了一个进程池，最大进程数是3
>    li = []
>    for i in range(6):
>        # res = p.apply(work, args=(i, ))
>        res = p.apply_async(work, args=(i,))  # 异步运行，根据进程池中有的进程数每次最多运行3个
>        li.append(res)
>    p.close()  # 关闭进程池
>    p.join()  # 阻塞主进程
>
>    for i in li:
>        print(i.get())  # 使用get获取apply_async的结果,如果是apply没有get方法
>```
>
>进程池之间的通信
>
>```python
>from multiprocessing import Pool, Manager
>import time
>
>
># 2.写入数据---进程池执行的代码
>def write(q):
>    for i in 'abcdefghijk.........':
>        print(f'将{i}放进队列中')
>        q.put(i)  # 把数据放进去
>
>
># 3.读取数据----进程池执行的代码
>def read(q):
>    # 有消息就读
>    for i in range(q.qsize()):  # 返回队列里面的消息数量
>        print('这是取出的数据：', q.get())
>
>
>if __name__ == '__main__':
>    q = Manager().Queue()  # 实例化了一个队列， 使用的是Manager里面的Queue
>    p1 = Pool()  # 创建进程池
>    p1.apply_async(write, args=(q,))
>    p1.apply_async(read, args=(q,))
>
>    p1.close()  # 关闭进程池
>    p1.join()  # 阻塞主进程
>    print('结束了-----')  # 主进程
>```



## 7.2 线程

```python
   # 构造方法
    def __init__(self, group=None, target=None, name=None,
                 args=(), kwargs=None, *, daemon=None):
        """This constructor should always be called with keyword arguments. Arguments are:

        *group* should be None; reserved for future extension when a ThreadGroup
        class is implemented.

        *target* is the callable object to be invoked by the run()
        method. Defaults to None, meaning nothing is called.

        *name* is the thread name. By default, a unique name is constructed of
        the form "Thread-N" where N is a small decimal number.

        *args* is the argument tuple for the target invocation. Defaults to ().

        *kwargs* is a dictionary of keyword arguments for the target
        invocation. Defaults to {}.

        If a subclass overrides the constructor, it must make sure to invoke
        the base class constructor (Thread.__init__()) before doing anything
        else to the thread.

        """
        assert group is None, "group argument must be None for now"
        if kwargs is None:
            kwargs = {}
        self._target = target
        self._name = str(name or _newname())
        self._args = args
        self._kwargs = kwargs
        if daemon is not None:
            self._daemonic = daemon
        else:
            self._daemonic = current_thread().daemon
        self._ident = None
        self._tstate_lock = None
        self._started = Event()
        self._is_stopped = False
        self._initialized = True
        # sys.stderr is not stored in the class like
        # sys.exc_info since it can be changed between instances
        self._stderr = _sys.stderr
        # For debugging and _after_fork()
        _dangling.add(self)

```

简单使用

```python
import threading
if __name__ == '__main__':
	t1 = threading.Thread(target=fun)
    t1.start()
```

>Thread 的方法
>
>```python
># 守护线程 ---- 要放在start前面
># 守护线程:True代表开启 主线程执行完了,子线程就会跟着结束,这是子线程设置守护线程
>t1.setDaemon(True) 
>
># 开启子线程
>t1.start()
>
># 阻塞主线程 ---- 必须放在start的后面
>t1.join()
>
># 设置线程名--修改
>t1.setName('线程1')
>
># 返回线程名
>print(t1.getName())
>```
>
>>线程之间的资源是共享的，多线程并发操作临界资源的时候可能会有数据安全的问题。
>>
>>解决方法
>>
>>```python
>>from threading import Thread, Lock
>>lock = Lock()
>>lock.release()
>>```

## 7.3 协程

```python
# 简单的协程实现
import time


def fun1():
    while True:
        yield 1
        time.sleep(1)


def fun2():
    while True:
        yield 2
        time.sleep(1)


if __name__ == '__main__':
    w1 = fun1()
    w2 = fun2()
    while True:
        print(next(w1))
        print(next(w2))
```

```python
# 使用greenlet实现切换任务
from greenlet import greenlet


def eat():
    print('开始吃东西了')
    g2.switch()  # 手动切换---切换到g2中运行
    print('吃炸鸡')
    # g2.switch()


def play():
    print('开始玩耍')
    # g1.switch()
    print('玩王者荣耀')


# greenlet(目标函数名)
g1 = greenlet(eat)  # 实例化了一个协程
g2 = greenlet(play)
g1.switch()  # 手动切换---切换到g1中运行

# switch协程的切换
```

```python
import gevent


# 1.如果没有遇到能够识别的io操作的话，不会进行任务的切换，实现并发的效果
def play():
    print('开始玩耍')
    # time.sleep(1)   # time.sleep(1)gevent不能够识别
    gevent.sleep(1)  # gevent.sleep(1)模拟的是gevent能够识别的io阻塞
    print('玩完了')


def writer():
    print('开始写代码了')
    gevent.sleep(1)
    print('写完了')


g1 = gevent.spawn(play)  # 创建一个协程对象
g2 = gevent.spawn(writer)

g1.join()  # 等待g1结束
g2.join()  # 等待g2结束


# joinall():这个方法的参数是一个协程对象列表，它会等待所有的协程都指向完了之后在退出
def work(name):
    for i in range(4):
        print(f'函数名：{name},循环的i值是：{i}')
        gevent.sleep(1)  # 没有遇到能够识别的io就不会实现并发的效果


g1 = gevent.spawn(work, 'work1')  # 实例化协程对象
g2 = gevent.spawn(work, 'work2')  # 实例化协程对象
gevent.joinall([g1, g2])
```

# 八.正则

```python
# 导入模块--re
import re

# re.match(正则表达式, 要匹配的字符串)
thing = 'Hello world'
m1 = re.match('Hello', thing)  # 从头开始找 区分大小写
print(m1)  # 匹配的对象
# 如果group没有匹配到数据就会报错
print(m1.group())  # Hello
print(m1.span())  # (0, 5)
```



```python
import re

# 1、 . 匹配任意一个字符(除了\n)
re1 = re.match('.', 'zhangsan')
print(re1.group())  # z
re2 = re.match('zi.', 'zhangsan')
print(re2.group())  # ziy
# re3 = re.match('.', '\n')  # \n不能用
# print(re3.group())

# 2、 [] 匹配[]中列举的字符
# 只能匹配小写
r1 = re.match('[h]', 'hello')
print(r1.group())  # h
# 只能匹配大写
r1 = re.match('[H]', 'Hello')
print(r1.group())  # H
# 大小写都可以
r1 = re.match('[Hh]', 'hello')
print(r1.group())
# 0-9的数字
r1 = re.match('[0123456789]', '4vsfdbdrt')
print(r1.group())  # 4
r1 = re.match('[0-9]he', '8hello')
print(r1.group())

# 3
# \d 匹配数字，即0-9
r3 = re.match('我\d', '我18岁了')
print(r3.group())
# \D 匹配非数字
r3 = re.match('我\D', '我T岁了')
print(r3.group())

# 4
# \s匹配空白，即 空格，tab键
r4 = re.match('\s', ' 张三')
print(r4.group())
r4 = re.match('\ss', ' s张三')
print(r4.group())

# 5
# \w 匹配单词字符，即a-z、A-Z、0-9、_
r5 = re.match('\w', 'abc')
print(r5.group())
r5 = re.match('\W', '@abc')  # 匹配非单词字符
print(r5.group())
```

```python
import re

# * 匹配前一个字符出现0次或者无限次
res = re.match('[A-Z]*', 'ZIYI')
# print(res)
print(res.group())

# +匹配前一个字符出现1次或者无限次
res = re.match('\d+', 'abc')  # \d:0-9
print(res.group())  # 至少要有一次
res = re.match('\d+', '1abc')  # \d:0-9
print(res.group())  # 1
res = re.match('[a-z]+', 'abcBAAdgfj')
print(res.group())  # abc

# ? 匹配前一个字符出现1次或者0次,要么1次, 要么没有
res = re.match('a?', 'aaaaaa')
print(res.group())  # a
res = re.match('\d?', 'a')
print(res.group())  # 没有 0次

# {m}匹配前一个字符出现m次
res = re.match('a{4}', 'aaaaaa')
print(res.group())  # aaaa
res = re.match('[a-zA-Z0-9]{6}', 'k45fgd')
print(res.group())

# {m,n}匹配前一个字符出现m到n次, 最少要有m次  最多n次
res = re.match('[a-zA-Z0-9]{1,9}', 'k45fgdjhdhjity4')
print(res.group())
res = re.match('\w{2,6}', '48%^&&')
print(res.group())  # 48
```

```python
import re
# ^匹配字符串开头
res = re.match('^A', 'Abc')  # 由A开头就匹配成功
print(res.group())  # A
res = re.match('^[0-9]', '345Abc')  # 由0-9开头就匹配成功
print(res.group())

# $匹配字符串结尾
res = re.match('[\w]*e$', 'zhangsane')  # 从头开始匹配
print(res.group())
res = re.match('[\w]*[\d]$', 'ziyie345')  # \d:0-9
print(res.group())


# 匹配分组
# |  匹配左右任意一个表达式
res = re.match('[\d]?\d$', '10')
print(res.group())
res2 = re.match('[\d]?\d$', '100')
print(res2.group())  # 报错
res3 = re.match('[\d]?\d$|100', '100')
print(res3.group())
res4 = re.match('[0-9]+|[a-z]+', 'a1gfdhj')
print(res4.group())

# () 将括号中字符作为一个分组
res = re.match('\w{4,15}@163.com', 'xxxx@163.com')
print(res.group())
res = re.match('\w{4,15}@(163|qq|126).com', 'xxxx@qq.com')
print(res.group())

# [^47] 这样表示取反，就是不包含了(^)
```



>```python
># search()会扫描整个字符串并返回第一个成功的匹配
>r1 = re.search('234', '121541515234')
>print(r1.group())  # 234
>```
>
>```python
># findall()以列表形式返回匹配到的字符串。如果没有找到匹配的，则返回空列表。
>res = re.findall('\d', '1z2a3b4q')  # findall没有返回值没有group方法
>print(res)
>```
>
>```sh
># match  从头开始匹配 匹配一次   --最不常用
># search 只返回第一个匹配 匹配一次  --较常用
># findall 匹配所有的字符串 返回一个列表 匹配所有    --最常用
>```
>
>```python
># sub() 将匹配到的数据进行替换
># def sub(pattern, repl, string, count=0, flags=0):
># pattern(需要被替换的), repl(用什么来替换), string（原来的字符串） 参数必填
>res = re.sub('\d+', '7', '我买了一杯18块的奶茶')
>print(res)
>res = re.sub('\D', '&', '我买了一杯18块的奶茶')
>print(res)
>res = re.sub('\D', '&', '我买了一杯18块的奶茶', 2)
>print(res)
>```
>
>```python
># split()根据匹配进行切割字符串，并返回一个列表
># re.split(pattern, string, maxsplit=0)
>r = re.split('\d', '1q2w3e4r')
>print(r)
>r = re.split('[, 。;]', '1,q2;w 3e 。4r')  # 空格也会计算
>print(r)
>```
>
>```python
>r = re.match('(\w+) (\w+)', 'hello python')  # ()分组
>print(r.group())  # hello python
>print(r.group(1))  # 编号 1就是第一个成功匹配的数据
>print(r.group(2))  # 编号 2就是第二个成功匹配的数据
># print(r.group(3))  # 报错 没有这个分组
>print(r.groups())  # ('hello', 'python')
>
># (?P<name>) 分组起别名  字典-键值对， 拿到的数据作为值 别名作为键
>r = re.match('(?P<f1>\w+) (?P<f2>\w+)', 'hello zhangsan world')
>print(r.groupdict())
>```
>
>```python
>import re
>res = re.match('ab*', 'abbbc')
>print(res.group())  # abbb  贪婪模式
>
>res2 = re.match('ab*?', 'abbbc')
>print(res2.group())  # a   非贪婪模式
>
># 非贪婪模式就是尽可能匹配最少的，非贪婪模式修饰的是 * + {m,n}
>res2 = re.match('a*?', 'aaaaaa')
>print(res2.group())  # 空的字符串  非贪婪模式
>res2 = re.match('a+?', 'aaaaaa')
>print(res2.group())  # a
>
>str1 = '<h1> hello zhansgan </h1>'
>print(re.match('<(\w*)>\w*</\\1>', str1).group())
>r = re.findall('<.*>', str1)  # 贪婪模式
>r2 = re.findall('<.*?>', str1)  # 非贪婪模式
>print(r)
>print(r2)
>```

# 九.GUI

GUI 参考

https://blog.csdn.net/m0_53602804/article/details/124170749

https://blog.csdn.net/qq_60381063/article/details/122844524

https://www.jb51.net/article/224743.htm

# 十.数据库链接

参考

https://blog.csdn.net/m0_63244368/article/details/124411220

https://blog.csdn.net/xiaogenggou/article/details/105885711

https://blog.csdn.net/qq_52764364/article/details/129758821
