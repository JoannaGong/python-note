# python-note
### 数字
* Int 整型
* Float 浮点型

### 数字的运算
** 求方 （4**3 表示 4 的 3 次方）

### 命令
* print: 打印指定内容
* type: 返回对象或实例的类型

### 字符串
三引号可以形成带有换行的多行字符串，由于 python 对脚本当中没有进行任何处理的字符串不进行编译，所以我们通常会用三引号作为长注释、多行注释
* '' 单引号
* "" 双引号
* ''' 三单引号
* """ 三双引号
* str 类型函数

### 字符串的索引（index）
* 取单个元素：字符串\[index\]
* 截取元素（有下限没有上限）：字符串\[start:end\]
* 步长截取（按照步长减一进行）：字符串\[start:end：num\]
  print("abcdefghijk"\[1:8:2\]) => bdfh
* 默认取法：字符串\[start:end,step\]
  这三个参数都有默认值，start:0, end: 结尾， step：1，可以取到字符串最后一位
  print("abcdefghijk"\[:5\])  => abcde
  print("abcdefghijk"\[3:\])  => defghijk
  step可以为负值，表示取反，从右往左
  
 ### 字符串的方法
 * 字符串长度：字符串.len()
 
 | center | 让字符串在指定的长度居中，如果不能居中，左短右长，可以指定填充内容，默认以空格填充 | "while".center(10, 'a') |
 | :------: | :------ | :------ |
 | ljust  | 让字符串在指定的长度左齐，如果不能居中，左短右长，可以指定填充内容，默认以空格填充 | "while".ljust(10, 'a')  |
 | rjust  | 让字符串在指定的长度右齐，如果不能居中，左短右长，可以指定填充内容，默认以空格填充 | "while".rjust(10, 'a')  |
 | zfill  | 将字符串填充到指定的长度，不足的地方，用0从左开始填充                           |  "while".zfill(10)      |
 | format | 按照顺序，将后面的参数传递给前面的大括号                                       |"{1} {0} {1}".format("hello", "world")|
 | strip  | 默认去除两端的空格，去除内容可以指定                                           |                |
 | lstrip | 默认去除左边的空格，去除内容可以指定                                           |                |  
 | rstrip | 默认去除右边的空格，去除内容可以指定                                           |                |
 
 ### 字符串的查找
 | count | 计数功能，返回自定字符在字符串中的个数 |
 | :------: | :------ |
 | find  | 查找，返回从左第一个指定字符的索引；若找不到，返回-1 |
 | rfind | 查找，返回从右第一个指定字符的索引；若找不到，返回-1 |
 | index  | 查找，返回从左第一个指定字符的索引；若找不到，报错 |
 | rindex | 查找，返回从右第一个指定字符的索引；若找不到，报错 |
 | replace | 从左到右替换指定的元素，可以指定替换的个数，默认全部替换 |
 | translate | 按照对应关系来替换内容 |     |
 ```
 from string import maketrans
 trans = maketrans("12345", "abcde")
 print("121231234".translate(trans))
 ```
 
# 列表
列表是一个有序的、可修改的、元素以逗号分割、以中括号包围的序列

## 推导式创建列表
```
arr = [x*2 for x in range(10) if x%9==0]
print(list(arr))
```

## 列表元素的增加和删除

* append() 方法
在列表尾部添加新的元素，速度最快，推荐使用
```
arr.append(100)
```

* + 运算符操作
* extend() 方法
```
arr = [1, 2, 3]
arr.extend(['4', '5'])
print(list(arr))
```

* insert() 插入元素
* 乘法扩展
```
a = ['a', 'b', 'c']*2       // ['a', 'b', 'c', 'a', 'b', 'c']
```

* pop() 方法
* remove() 方法
* del 删除
```
a = ['a', 'b', 'c']
del a[1]
```
## 查找
* index() 获得指定元素在列表中首次出现的索引
* count() 获得指定元素在列表中出现的次数
* len() 返回列表长度

## 列表排序
* sort() 按顺序排序
```
a = [3, 4, 5, 3, 4, 2, 1,44]
a.sort(reverse=True)    // 取反
```
* 打乱顺序
```
import random
a = [1, 2, 3, 4, 5]
random.shuffle(a)
print(a)
```

## 建新列表的排序
* sorted()
* reverse() 取反

## 列表中的内置函数
* max()
* min()
* sum()

# 元组
元组属于不可变序列，不能修改元组中的元素

## 创建
* 通过（）创建元组，小括号可以省略；
如果元组中只有一个元素，则必须后面加逗号。
```
a = (10, 20, 30)
a = 10, 20, 30
a = (1,)
```

* 通过 tuple() 创建
```
b = tuple()    // 创建一个空元组对象
b = tuple('abc')     // 把字符串转换成列表  // ['a', 'b', 'c']
b = tuple(range(10))
b = tuple([2, 3, 4])
```

# 字典
字典是‘键值对’的无序可变序列

## 创建

* 通过 {} 和 dict 创建
```
a = {'name': 'abc', 'age': 18, 'sex': 'female'}
a = dict([('name', 'abc'),('age', 18),('sex', 'female')])
```

* 通过 zip() 创建
```
k = ['name', 'age', 'sex']
v = ['abc', 18, 'female']
d = dict(zip(k, v))
```

* 通过 fromkeys 创建值为空的字典
```
a = dict.fromkeys(['name', 'age', 'sex'])   // {'name': None, 'age': None, 'sex': None}
```

* keys() 列出所有的键
* values() 列出所有的值
* items() 列出所有的键值对
* len() 键值对的个数
* 检测一个‘键’是否在字典中
```
'name' in a
```

## 字典元素添加、修改、删除

* 给字典新增‘键值对’，如果‘键’存在，则覆盖旧的键值对；如果不存在，则新增
```
a = {'name': 'abc', 'age': 18, 'sex': 'female'}
a['con'] = 'bcd'
print(a)
```

* 使用 update() 将新字典中所有键值对全部加到旧字典对象中，如果key 有重复，则直接覆盖
* 字典中元素的删除，可以使用 del() 方法；或者 clear() 删除所有键值对；pop() 删除指定键值对，并返回对应的‘键对象’
```
a = {'name': 'abc', 'age': 18, 'sex': 'female'}
del(a['name'])
print(a)
```

* popitem() 随机删除和返回该键值对

# 序列解包
用于元组、列表、字典，便于对多个变量赋值
```
a = {'name': 'abc', 'age': 18, 'sex': 'female'}
[x, y, z] = a
print(x)
print(y)
print(z)
```
## lambda 匿名函数

```python
a = lambda a, b, c, d: a+b+c+d
print(a(1, 2, 3, 4))
b = [lambda a: a*2, lambda b: b*5]
print(b[0](3))
```

## eval() 函数

将字符串当成有效的表达式来求值，并返回求值结果

## nonlocal 关键字

* nonlocal 用来声明外层的局部变量
* global 用来声明全局变量

## LEGB 规则

python 在查找‘名称’时，是按照 LEGB 规则查找的
local => enclosed => global => built in

* local 指的是函数或者类的方法内部
* enclosed 指的是嵌套函数（一个函数包裹另一个函数，闭包）
* global 指的是模块中的全局变量
* built in 指的是 python 为自己保留的特殊名称

## 类

* __init__() 方法：初始化创建好的对象，给实例属性赋值
* __new__() 方法：用于创建对象，但我们一般无需重新定义该方法
* __del__() 析构方法
* __call__()方法：可调用的对象，对象可以像函数一样被调用

## 方法没有重载
python 中是没有方法的重载的，定义一个方法即可有多种调用方式，相当于实现了其他语言中的方法的重载；
如果我们在类体中定义了多个重名的方法，只有最后一个方法有效

## 工厂模式
```python
class CarFactory:
    def create_car(self, brand):
        if brand == 'Benz':
            return Benz()
        elif brand == 'BMW':
            return BMW()
        elif brand == 'Audi':
            return Audi()
        else:
            print('无法生产该车型')

class Benz:
    print('Benz')

class BMW:
    print('BMW')

class Audi:
    print('Audi')

factory = CarFactory()
car1 = factory.create_car('Benz')
car2 = factory.create_car('Ford')
```

## 单例模式

```python
class MySingleton:
    __obj = None
    __init_flag = True

    def __new__(cls, *args, **kwargs):
        if cls.__obj == None:
            cls.__obj = object.__new__(cls)

        return cls.__obj

    def __init__(self, name):
        if MySingleton.__init_flag:
            print('init')
            self.name = name
            MySingleton.__init_flag = False

a = MySingleton('aa')
b = MySingleton('bb')
print(a)
print(b)
```

## 文件操作

```python
f = open(r"b.txt", "w", encoding='utf-8')
f.write('星期天')
f.close()
```

```python
with open(r'b.txt', 'r', encoding='utf-8') as f:
    print(f.read())
```

```python
# 每次读取一行
with open(r'b.txt', 'r', encoding='utf-8') as f:
    for x in f:
        print(x, end="")
```

## try except 基本结构

try...except...else 结构增加了’else 块。如果try块中没有抛出异常，则执行else块
如果try 块中抛出异常，则执行except 块，不执行 else 块。
try...except...finally 结构中，finally 块无论是否发生异常，都会被执行；
通常用来释放try块中申请的资源

```python
try:
    #被监控的可能引发异常的语句块
except BaseException as e:
    #异常处理语句块
else:
    pass
finally:
    pass
```

## try 多个 except 结构

按照先子类后父类的顺序

```python
try:
    #被监控的可能引发异常的语句块
except Exception1:
    #处理 Exception1 的语句块
except Exception2:
    #处理 Exception2 的语句块
except BaseException as e:
    #处理可能遗漏的异常的语句块
```

## 常见异常的解决

* 一般不要将 return 语句放到 try，except，else，finally 块中，会发生一些意想不到的错误。
建议放到方法最后
* SyntaxError 语法错误
int a = 3
* NameError 尝试访问一个没有申明的变量
print(a)
* ZeroDivisionError 除数为 0 的错误（零除错误）
* ValueError 数值错误
float('abc')
* TypeError 类型错误
123 + 'abc'
* AttributeError 访问对象的不存在的属性
* IndexError 索引越界异常
* KeyError 字典的关键字不存在

## 常见异常汇总

| 异常名称 | 说明 |
| :......: | :...... |
| ArithmeticError | 所有数值计算错误的基类 |





