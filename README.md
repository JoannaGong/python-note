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
* 默认取法：字符串\[start\:end\:step\]
  这三个参数都有默认值，start:0, end: 结尾， step：1，可以取到字符串最后一位
  print("abcdefghijk"\[:5\])  => abcde
  print("abcdefghijk"\[3:\])  => defghijk
