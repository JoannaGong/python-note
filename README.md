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
| :------: | :------ |
| ArithmeticError | 所有数值计算错误的基类 |
| AssertionError | 断言语句失败 |
| AttributeError | 对象没有这个属性 |
| BaseException | 所有异常的基类 |
| DeprecationWarning | 关于被弃用的特征的警告 |
| EnvironmentError | 操作系统错误的基类 |
| EOFError | 没有内建输入，达到EOF标记 |
| Exception | 常规错误的基类 |
| FloatingPointError | 浮点计算错误 |
| FutureWarning | 关于构造将来语义会有改变的警告 |
| GeneratorExit | 生成器发生异常来通知退出 |
| ImportError | 导入模块/对象失败 |

## with 上下文管理

finally 块由于是否发生异常都会执行，通常放释放资源的代码。
其实，我们可以通过 with 上下文管理，更方便的实现释放资源的操作。
with 不是不用来取代 finally，只是作为补充

```python
with context_expr[as var]:
    pass
    
with open('b.txt', 'r', encoding='utf-8') as f:
    content = f.readline()
    print(content)
```

## traceback 模块

print_exc是简化版的print_exception

```python
import traceback
try:
    print('step1')
    num = 1/0
except:
    traceback.print_ext()
```

## raise 自定义异常类

自定义异常类一般都是运行时异常，通常继承 exception 或其子类即可。
命名一般以 Error、Exception 为后缀。
自定义异常由 raise 语句抛出

```python
class AgeError(Exception):  # 继承Exception类
    def __init__(self, errorInfo):
        Exception.__init__(self)
        self.errorInfo = errorInfo
    def __str__(self):
        return str(self.errorInfo) + '年龄错误！应该在1-150之间'

if __name__ == '__main__':
    age = int(input('请输入一个年龄：'))
    if age < 1 or age > 150:
        raise AgeError()
    else:
        print('正常的年龄：', age)
```
[if __name__ == '__main__'](http://blog.konghy.cn/2017/04/24/python-entry-program/)


# 模块

## import 语句导入

* import 模块名         # 导入一个模块
* import 模块1，模块2...         # 导入多个模块
* import 模块名 as 模块别名        # 导入模块并使用新名字

## __import__() 动态导入

import 语句本质上就是调用内置函数__import__()，我们可以通过它实现动态导入。
给__import__()动态传递不同的参数值，就能导入不同的模块。
一般不建议自行使用__import__()导入，其行为在 python2 和 python3 中有差异，会导致意外错误。如需动态导入，可以使用 importlib 模块。

```
s = 'math'
m = __import__(s)
print(m.pi)
```

```
import importlib
a = importlib.import_module("math")
print(a.pi)
```

## 导入包操作

from package import item 这种语法中，item 可以是包、模块，也可以是函数、类、变量
import item1.item2  这种语法中，item 必须是包或模块，不能是其他

* import a.aa.module_AA
在使用时，必须加完整名称来引用。比如：a.aa.module_AA.fun_AA()

* from a.aa import module_AA
在使用时，直接可以使用模块名。比如：module_AA.fun_AA()

* from a.aa.module_AA import fun_AA   直接导入函数
在使用时，直接可以使用函数名。比如：fun_AA()

# 基于 tkinter 模块创建 GUI 程序步骤

* 创建应用程序主窗口对象（也称：根窗口）
```
from tkinter import *
root = Tk()
```

* 在主窗口中，添加各种可视化组件，比如：按钮Button，文本框Label
```
btn01 = Button(root)
btn01["text"] = "按钮"
```

* 通过几何布局管理器，管理组件的大小和位置
btn01.pack()

* 事件处理
通过绑定事件处理程序，响应用户操作所触发的事件

```
from tkinter import *
from tkinter import messagebox
root = Tk()
root.title("My first GUI")
root.geometry("500x300+100+200")

btn01 = Button(root)
btn01["text"] = "按钮"

btn01.pack()

def songhua(e):
    messagebox.showinfo("Message", "send flower")
    print("送花结束")

btn01.bind("<Button-1>", songhua)

root.mainloop()
```

## 主窗口位置和大小

geometry('w*h ± x ± y')
w 为宽度， h 为高度， +x 表示距屏幕左边的距离， -x 表示距屏幕右边的距离
+y 表示距屏幕上边的距离， -y 表示距屏幕下边的距离

## 常用组件汇总列表

| Tkinter 类 | 名称 | 简介 |
| :------: | :------: | :------ |
| Toplevel | 顶层 | 容器类，可用于为其他组件提供单独的容器；Toplevel 有点类似于窗口 |
| Button | 按钮 | 代表按钮组件 |
| Canvas | 画布 | 提供绘图功能，包括直线、矩形、椭圆、多边形、位图等 |
| Checkbutton | 复选框 | 可供用户勾选的复选框 |
| Entry | 单行输入框 | 用户可输入内容 |
| Framc | 容器 | 用于装载其它 GUI 组件 |
| Label | 标签 | 用于显示不可编辑的文本或图标 |
| LabelFrame | 容器 | 也是容器组件，类似于 Frame，但它支持添加标题 |
| Listbox | 列表框 | 列出多个选项，供用户选择 |
| Menu | 菜单 | 菜单组件 |
| Menubutton | 菜单按钮 | 用来包含菜单的按钮（包括下拉式、层叠式等） |
| OptionMenu | 菜单按钮 | Menubutton 的子类，也代表菜单按钮，可通过按钮打开一个菜单 |
| Message | 消息框 | 类似于标签，但可以显示多行文本；后来当 Label 也能显示 |


## GUI 程序的经典面向对象写法

```
from tkinter import *

class Application(Frame):
    def __init__(self, master=None):
        super().__init__(master)
        self.master = master
        self.pack()
        self.createWidget()
    def createWidget(self):
        pass

root = Tk()
root.geometry("500x300+200+300")
root.title("一个经典的GUI程序类的测试")

app = Application(master=root)

root.mainloop()
```













# object 根类

object 类是所有类的父类，因此所有的类都有 object 类的属性和方法。

## mro()方法

通过类的方法 mro() 或者类的属性__mro__，可以输出这个类的继承层次活动

```python
class A:
    pass
class B(A):
    pass
class C(B):
    pass
print(C.mro())
```

## dir() 查看对象属性

## __str__() 方法

用于返回一个对于“对象的描述”，对应于内置函数str()，经常用于print()方法，帮助我们查看对象的信息

```python
class Person:
    def __init__(self, name):
        self.name = name

    def __str__(self):
        return "名字是：{0}".format(self.name)

p = Person("Lilei")
print(p)
```

## super() 获得父类定义

在子类中，如果想要获得父类的方法时，我们可以通过super()来做。
super()代表父类的定义，不是父类对象。

```python
class A:
    def say(self):
        print("A:", self)

class B(A):
    def say(self):
        # A.say(self)
        super().say()
        print("B:", self)

B().say()
```

## isinstance() 函数

用来判断一个对象是否是一个已知的类型
isinstance(object, classinfo)


# 多态

多态是指同一个方法调用由于对象不同可能会产生不同的行为。

* 多态是方法的多态，属性没有多态
* 多态的存在是有2个必要条件：继承、方法重写

```python
class Man:
    def eat(self):
        print('hungry')

class Chinese(Man):
    def eat(self):
        print('Chinese eat with chopsticks')

class English(Man):
    def eat(self):
        print('English eat with fork')

class Indian(Man):
    def eat(self):
        print('Indian eat with their hands')

def eat_method(m):
    if isinstance(m, Man):
        m.eat()     # 多态，一个方法调用，根据对象不同、调用不同的方法
    else:
        print("cannot eat")

eat_method(Chinese())
eat_method(English())
eat_method(Indian())
```

# GUI

## 面向对象GUI经典基本程序

```python
from tkinter import *


class Application(Frame):

    def __init__(self, master=None):
        # super() 代表的是父类的定义，而不是父类对象

        super().__init__(master)
        self.master = master
        self.pack()

        self.create_widget()

    def create_widget(self):
        pass


if __name__ == '__main__':
    root = Tk()
    root.title("GUI经典程序")
    root.geometry("500x300+200+200")
    app = Application(master=root)
    root.mainloop()
```

```python
from tkinter import *


class Application(Frame):

    def __init__(self, master=None):
        # super() 代表的是父类的定义，而不是父类对象

        super().__init__(master)
        self.master = master
        self.pack()

        self.create_widget()

    def create_widget(self):
        self.label01 = Label(self, text="GUI Label1", width=10, height=2, bg="black", fg="white")
        self.label01.pack()

        self.label02 = Label(self, text="GUI Label2", width=10, height=2, bg="pink", fg="white",
                             font=("黑体", 20))
        self.label02.pack()

        # 显示图像
        global photo
        photo = PhotoImage(file="images/1.gif")
        self.label03 = Label(self, image=photo)
        self.label03.pack()

        # 显示多行文本
        self.label04 = Label(self, text="beauty1\nbeauty2\nbeauty3", borderwidth=5, relief="groove", justify="right")
        self.label04.pack()



if __name__ == '__main__':
    root = Tk()
    root.title("GUI经典程序")
    root.geometry("800x800+200+200")
    app = Application(master=root)
    root.mainloop()
```


## options 选项

* 创建对象时，使用命名参数（即关键字参数）
fred = Button(self, fg="red", bg="blue")

* 创建对象后，使用字典索引方式
fred["fg"] = "red"
fred["bg"] = "blue"

* 创建对象后，使用 config() 方法
fred.config(fg="red", bg="blue")


## 可变参数

可变数量的参数

* *param(一个星号)：将多个参数收集到一个“元组”对象中

* **param(两个星号)：将多个参数收集到一个“字典”对象中

```python
def f1(a, b, **c):
    print(a, b, c)

f1(8, 9, name="leo", age=18)
```

## canvas 画图

```python
from tkinter import *
from tkinter import messagebox
import random

class Application(Frame):

    def __init__(self, master=None):
        # super() 代表的是父类的定义，而不是父类对象

        super().__init__(master)
        self.master = master
        self.pack()

        self.create_widget()

    def create_widget(self):
        self.canvas = Canvas(self, width=300, height=200, bg="pink")
        self.canvas.pack()

        # 画一条直线
        line = self.canvas.create_line(10, 10, 30, 20, 40, 50)

        # 画一个矩形
        rect = self.canvas.create_rectangle(50, 50, 100, 100)

        # 画一个椭圆
        oval = self.canvas.create_oval(50, 50, 100, 100)


        global photo
        photo = PhotoImage(file="images/1.gif")
        self.canvas.create_image(150, 170, image=photo)

        Button(self, text="画10个矩形", bg="blue", command=self.draw50Recg).pack(side="left")

    def draw50Recg(self):
        for x in range(0, 10):
            x1 = random.randrange(int(self.canvas["width"])/2)
            y1 = random.randrange(int(self.canvas["height"])/2)
            x2 = x1 + random.randrange(int(self.canvas["width"])/2)
            y2 = y1 + random.randrange(int(self.canvas["height"])/2)
            self.canvas.create_rectangle(x1, y1, x2, y2)


if __name__ == '__main__':
    root = Tk()
    root.title("GUI经典程序")
    root.geometry("600x600+200+200")
    app = Application(master=root)
    root.mainloop()

```

# 布局管理器

三种管理器：pack  grid place

## grid 布局管理器

| 选项 | 说明 | 取值范围 |
|:------: | :------ | :------ |
| column | 单元格的列号 | 从0开始的正整数 |
| columnspan | 跨列，跨越的列数 | 正整数 |
| row | 单元格的行号 | 从0开始的正整数 |
| rowspan | 跨行，跨越的行数 | 正整数 |
| ipadx, ipady | 设置子组件之间的间隔，x方向或者y方向，默认单位为像素 | 非负浮点数，默认0.0 |
| padx, pady | 与之并列的组件之间的间隔，x方向或者y方向，默认单位为像素 | 非负浮点数，默认0.0 |
| sticky | 组件紧贴所在单元格的某一角，对应于东南西北中以及4个角 | n,s,w,e,nw,sw,se,nt,center(默认) |

```python
from tkinter import *

class Application(Frame):

    def __init__(self, master=None):
        # super() 代表的是父类的定义，而不是父类对象

        super().__init__(master)
        self.master = master
        self.pack()

        self.create_widget()

    def create_widget(self):
        self.label01= Label(self, text="user")
        self.label01.grid(row=0, column=0)
        self.entry01 = Entry(self)
        self.entry01.grid(row=0, column=1)
        Label(self, text="user=tellphone").grid(row=0, column=2)

        Label(self, text="password").grid(row=1, column=0)
        Entry(self, show="*").grid(row=1, column=1)

        Button(self, text="login").grid(row=2, column=1, sticky=EW)
        Button(self, text="cancel").grid(row=2, column=2, sticky=E)


if __name__ == '__main__':
    root = Tk()
    root.title("GUI经典程序")
    root.geometry("500x300+200+200")
    app = Application(master=root)
    root.mainloop()
```

## 通过 grid 布局，实现计算器软件界面

```python
from tkinter import *

class Application(Frame):

    def __init__(self, master=None):
        # super() 代表的是父类的定义，而不是父类对象

        super().__init__(master)
        self.master = master
        self.pack()

        self.create_widget()

    def create_widget(self):
        btnText = (("MC", "M+", "M-", "MR"),
                   ("C", "+", "/", "x"),
                   (7, 8, 9, "-"),
                   (4, 5, 6, "+"),
                   (1, 2, 3, "="),
                   (0, "."))
        Entry(self).grid(row=0, column=0, columnspan=4)

        for rindex,r in enumerate(btnText):
            for cindex,c in enumerate(r):
                if c == "=":
                    Button(self, text=c, width=2).grid(row=rindex+1, column=cindex, rowspan=2, sticky=NSEW)
                elif c == 0:
                    Button(self, text=c, width=2).grid(row=rindex+1, column=cindex, columnspan=2, sticky=NSEW)
                elif c == ".":
                    Button(self, text=c, width=2).grid(row=rindex+1, column=cindex+1, rowspan=2, sticky=EW)
                else:
                    Button(self, text=c, width=2).grid(row=rindex+1, column=cindex, sticky=EW)


if __name__ == '__main__':
    root = Tk()
    root.title("GUI经典程序")
    root.geometry("500x300+200+200")
    app = Application(master=root)
    root.mainloop()

```

## pack 布局管理器

pack 适用于简单的垂直或水平排布，如果需要复杂的布局，可以使用 grid 或 place

## pack 布局用法，制作钢琴按键布局

```python
from tkinter import *

root = Tk()
root.geometry("700x220")

f1 = Frame(root)
f1.pack()
f2 = Frame(root)
f2.pack()

btnText = ("流行风", "中国风", "日本风", "重金属", "轻音乐")

for txt in btnText:
    Button(f1, text=txt).pack(side="left", padx="10")

for i in range(1, 20):
    Label(f2, width=5, height=10, borderwidth=1, relief="solid",
          bg="black" if i % 2 == 0 else "white").pack(side="left", padx=2)

root.mainloop()
```

# python 爬虫

## robots.txt 口头协议

taobao.com/robots.txt


## 爬取步骤

* 给一个url
* 写程序，模拟浏览器访问url
* 解析内容，提取数据

## 涉及内容

* 使用到的库
urllib\requests\bs4

* 解析网页内容的知识
正则表达式，bs4,xpath,jsonpath

* 涉及到动态html
selenium + phantomjs, chromeheadless

* scrapy 框架
高性能框架使用

* scrapy-redis 组件
redis, 分布式爬虫

* 涉及到爬虫 - 反爬虫 - 反反爬虫 的一些内容
UA，代理，验证码，动态页面等


## urllib 库

模拟浏览器发送请求的库，python自带

## urllib.request

* urlopen() 发送请求
* urlretrieve()

## urllib.parse

* quote    url编码函数，将中文转换为%xx
* unquote     url解码函数，将%xx转换为指定字符
* urlencode   将字典拼接，并实现了编码的功能

```python
import urllib.parse
ret = urllib.parse.quote(image_url)
re = urllib.parse.unquote(image_url)
url = urllib.parse.urlencode(data)

```

## response

* read()              读取相应内容，内容是字节类型
* geturl()            读取请求的url
* getheaders()        获取头部信息，列表里面有元组
* getcode()           获取状态码
* readlines()         按行读取，返回列表，都是字节类型

```python
import urllib.request

url = "http://www.baidu.com"

# 发送请求
response = urllib.request.urlopen(url)

# print(response.read().decode())

# with open('baidu.html', 'w', encoding='utf8') as fp:
#     fp.write(response.read().decode())

# print(dict(response.getheaders()))

print(response.geturl())

image_url = "https://hbimg.huabanimg.com/91c55b6bd4e80d2e2d31f4889498072670397d5319e47-j0Y3Wp_fw658"

response = urllib.request.urlopen(image_url)

# 图片只能写入本地二进制的格式

# with open('prince.jpg', 'wb') as fp:
#     fp.write(response.read())

urllib.request.urlretrieve(image_url, 'prince.jpg')
```



## 字符串与二进制字符串之间的转换

* encode() 字符串 => 二进制
如果小括号里不写参数，默认是utf8
如果写，就写 gbk

* decode()  二进制 => 字符串
如果不写，默认utf8
如果写，写 gbk


## get 方式

```python
import urllib.request
import urllib.parse

keywords = input("请输入您想要搜索的内容")

url = 'http://www.baidu.com/s'

data = {
    'wd': keywords,
    'ie': 'uft-8'
}

query_string = urllib.parse.urlencode(data)

url = url + '?' + query_string

# 发送请求

response = urllib.request.urlopen(url)
file_name = keywords + ".html"

with open(file_name, 'wb') as fp:
    fp.write(response.read())
```

# 构建请求头部信息（反爬第一步）

## 伪装自己的UA，让服务器认为你是浏览器上网

构建请求对象： urllib.request.Request()

```python
import urllib.request
import urllib.parse

url = 'http://www.baidu.com/'

headers = {
    "User-Agent": "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3770.100 Safari/537.36"
}

request = urllib.request.Request(url=url, headers=headers)

response = urllib.request.urlopen(request)

print(response.read().decode())
```

## post() 

```python
import urllib.request
import urllib.parse

post_url = "https://fanyi.baidu.com/sug"
word = input('输入要翻译的英文单词：')

form_data = {
    'kw': word
}

headers = {
    "user-agent": "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3770.100 Safari/537.36"
}

request = urllib.request.Request(url=post_url, headers=headers)
form_data = urllib.parse.urlencode(form_data).encode()

response = urllib.request.urlopen(request, data=form_data)

print(response.read().decode())
```



















