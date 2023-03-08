# 基础

## 多行语句

在一行代码末尾加上`\`，表示下一行接本行，这是一行代码

## 引号

+ 单引号、双引号

  作用相同，当字符串中需要打印其中一种引号时，外层可以使用另一种引号表示这是一个字符串

+ 三引号

  多行字符串，允许跨行

## print

+ 不换行输出

  ```python
  >>> print("结尾加上 end=''",end="");print(" 就不会换行",end="");
  结尾加上 end='' 就不会换行
  ```

## 缩进

+ `python`中使用`冒号`+`tab`缩进代替大括号

  ```python
  if guess == 3:
      print("big sb")
  ```

## 运算符

+ `/`：真正的除法，得到小数
+ `//`：地板除，得到整数
+ `**`：幂运算；`2**3 = 8`

## for

+ `for i in xxxx`

## dir

+ 获取对象、变量、类型的属性、方法列表

  ```python
  dir(list)	// list类型的属性、方法列表
  dir()		//当前模块的属性、方法列表
  ```

# 数据类型

+ 使用`type()`函数可以得到变量类型

+ 使用`isinstance()`函数可以判断变量是不是某种类型

  ```python
  >>> isinstance(1,int)
  True
  ```

## 标准数据类型

### Numbers（数字）

+ 数字类型分为4种

  + **int** 

    + 使用`int()`将其他类型转为`int`

  + **bool**

  + **float** 

    + `1.2`

    + `1.5e+3`

      e记法，表示`1500.0`

    + 使用`float()`将其他类型转为`float`

  + **complex** (复数)

    + `1.2 + 1.3j`

### String（字符串）

+ 单引号、双引号：单行字符串

+ 三引号：跨行字符串

+ 原始字符串

  + 字符串前加上`r`，会将`\`自动转义为`\\`，来保证打印时不会把某些字符当作转义字符处理

  + 注意此时字符串不能以`\`结尾

  + 例

    ```python
    >>> str = r"c\c"
    >>> str
    'c\\c'
    >>> print(str)
    c\c
    ```

+ 使用`str()`将其他类型转换为字符串

+ 字符串不能修改

+ 字符串重复打印可以使用`*`

  ```python
  >>> "ceshi " * 3
  'ceshi ceshi ceshi '
  ```

+ 字符串索引

  + `0`表示第1个字符，`-1`表示最后一个字符

  + 字符串索引为左闭右开的，即结果包含起始下标字符，不包含结束下标字符

  + 字符串截取使用`变量[头下标:尾下标:步长]`

  + demo
  
    ```python
    str='Runoob'
     
    print(str[0:-1])           # 输出第一个到倒数第二个的所有字符
    print(str[0])              # 输出字符串第一个字符
    print(str[2:5])            # 输出从第三个开始到第五个的字符
    print(str[2:])             # 输出从第三个开始后的所有字符
    print(str[1:5:2])          # 输出从第二个开始到第五个且每隔两个的字符
    
    # 打印结果
    Runoo
    R
    noo
    noob
    uo
    ```

+ 常用函数

  ```python
  str = 'tEst'
  str.capitalize()	// 首字母转大写
  str.casefold()		// 全部转小写
  str.count('Es',1,3)	// 计算指定坐标范围内字符串出现次数，坐标范围可省略，表示范围为整个字符串
  str.endswith('s',1,3)	// 判断是否以指定字符结尾，坐标范围可省略
  str.expandtabs(tabsize=8)	// 将\t替换为指定个数的空格，默认8
  str.find('Es',1,3)	// 判断字符串中是否存在指定字符，坐标范围可省略
  str.index('Es',1,3)	// 返回字符串中是否存在指定字符下标，坐标范围可省略
  str.isalnum()		// 是否全为字母或数字
  str.isalpha()		// 判断是否包含字母并且不包含数字
  str.islower()		// 是否全为小写
  str.isupper()		// 是否全为大写
  str.lower()			// 转为小写
  str.upper()			// 转为大写
  str.isnumeric()		// 是否全为数字
  str.isspace()		// 是否全为空格
  str.replace('E','e',2)	// 字符串替换，最大次数可省略
  str.split(',',2)	// 按指定字符分割，最大分割次数可省略，默认按空格分割
  str.splitlines(2)	// 按\n分割成行，参数表示最多返回几行，可省略
  str.strip(' ')		// 删除字符串前后的指定字符，默认空格
  str.zfill(8)		// 返回指定长度的字符串，前面用0填充
  ```

+ 格式化

  ```python
  >>> "{0} love {1}".format("i","u")
  'i love u'
  >>> "{a} love {b}".format(a="i",b="u")
  'i love u'
  >>> '{0:.1f}{1}'.format(27.658,"GB")
  '27.7GB'
  >>> '%s结果：%d'%('计算',4)
  '计算结果：4'
  ```

  

### List（列表）

+ 数组

+ `append`：添加1个元素

+ `extend`：将1个列表中元素全部添加到另一个列表，相当于列表相加

+ `insert`：添加到指定位置；`insert(1,"ceshi")`

+ `remove`：指定内容删除

+ `del`：关键字，删除指定元素

  ```python
  del arr[1]	// 删除数组中下标为1的元素
  del arr 	// 删除数组
  ```

+ `pop`：弹出最后1个元素

+ 列表分片

  + `arr[1:3]`：将源列表下表1到3的元素生成新列表
  + `arr[:3]`：将源列表下表0到3的元素生成新列表
  + `arr[:]`：复制列表

+ 操作符在列表中应用

  + `比较操作符`：从左至右依次比较大小，类似于字符串比较大小

    ```python
    a1 = [2,3]
    a2 = [2,1]
    psrint(a1 > a2)	// true
    ```

  + `a1 + a2`：合并为1个列表，等于`extend`

  + `a1 * 3`：列表元素重复3次形成新列表

+ `in`、`not in`：判断列表中是否有某元素

+ `a1.count(2)`：列表`a1`中出现`2`的次数

+ `a1.index(1[,from,end])`：在指定范围内查找第一个出现该元素的下标

+ `a1.reverse()`：翻转列表

+ `a1.sort()`：从小到大排序；`a1.sort(reverse=True)`：从大到小排序

### Tuple（元组）

+ 元组中元素不支持修改，其他特性与列表相同

+ 使用小括号创建

  ```python
  tuple1 = (1,2,3)
  tuple2 = 1,2,3		// 默认集合就是元组
  tuple1 = (1,)		// 只有1个元素时必须有逗号，否则会定义为这个元素，而非元组
  ```

### Dictionary（字典）

+ map集合

  ```python
  dict1 = {"test":1}
  ```

+ 常用方法

  + fromkeys

    + 创建1个集合，key取集合中元素，value设置为相同的值

      ```python
      dict.fromkeys((2,3,4),5)
      # {2: 5, 3: 5, 4: 5}
      ```

  + keys：遍历key

  + values：遍历value

  + items：遍历键值对

  + 取值

    ```python
    dict1['test']		# 不存在时会报错
    dict1.get('test')	# 不存在时返回None
    dict1.get('test',0)	# 不存在时返回0
    ```

  + 判断是否存在key

    ```python
    2 in dict1
    ```

  + clear：清空集合

  + copy：复制集合，深拷贝

  + pop：弹出指定项

  + popitem：弹出1项

### Set

+ 自动去重无序集合

  ```python
  set1 = {1,2,3}
  set1 = set((2,3,4,4))
  ```

+ frozenset

  创建不可修改集合

  ```python
  set1 = frozenset((2,3,4))
  ```

  

## 其他类型

### type类型

+ 使用`type()`函数得到得变量类型就是`type`类型，表示变量得类型

# 函数

+ 使用`def`定义

  ```python
  def func():
      print("test")
  ```

+ 定义必须在调用之前

+ 调用时可以使用参数名指定参数

  ```python
  def func(a,b):
      print('test')
  func(2,b=3)
  ```

+ 可变参数

  ```python
  def func(*params):
      print(len(params))
  ```

+ 参数可以带默认值，带有默认值的参数必须放在参数列表后面

  ```python
  def func(a,b=2):
      print('test')
  func(2,b=3)
  ```

+ 内嵌函数

  函数内部还可以继续定义函数

  ```python
  def func():
      def func1():
          print('test1')
      func1()
  func()
  ```

+ global、nonlocal

  + 当修改外层作用域中的变量时，会在当前作用域创建同名的变量进行赋值，外层作用域中变量并不会被修改

  + 如果需求就是要修改外层作用域的变量，则需要使用`global`或`nonlocal`关键字，在当前作用域对变量进行一次声明

    ```python
    # global
    def func():
        global a # 必须使用global声明，才能使用全局变量a
        a = 2
    a = 1
    func()
    print(a)
    
    # nonlocal
    
    def func():
        a = 1
        def func1():
            nonlocal a # 必须使用nonlocal声明，才能使用func中的变量a
            a = 2
        func1()
        print(a)
    ```

  + `global`、`nonlocal`区别

    + `global`只能用于声明全局变量
    + `nonlocal`会一层一层函数的向上找需要声明的变量，但是不会找到全局

+ 闭包

  + 定义

    内部函数引用了外部函数中的变量，则这个内部函数就称之为闭包

    ```python
    def talk(user):
        def say(content):
            print("$s say:%s"%(user,content))
        return say
    
    say = talk('tom')
    say('nice')
    ```

  + 维基百科的严谨定义

    在一些语言中，在函数中可以（嵌套）定义另一个函数时，如果内部的函数引用了外部的函数的变量，则可能产生闭包。闭包可以用来在一个函数与一组“私有”变量之间创建关联关系。在给定函数被多次调用的过程中，这些私有变量能够保持其持久性。

  + 用途

    + 用于在函数外继续使用局部变量
    + 让函数内部的局部变量始终保持在内存中，减少全局变量的使用，造成全局变量污染

+ lambda

  ```python
  f = lambda x : x + 1
  f(2)	# 3
  ```

# 文件

+ 打开文件

  ```python
  f = open('/data/test.sh','r')
  ```

  打开模式：

  + r：只读（默认）
  + w：只写，文件存在则覆盖
  + x：文件存在抛出异常
  + a：只写，存在则追加
  + b：二进制打开
  + t：文本模式打开（默认）
  + +：读写模式，可与其他模式共同使用
  + U：通用换行符支持

+ 文件流操作

  + close：关闭文件流
  + read：读取指定个数字符，不指定参数则读取全部
  + readline：读取一行
  + write：写入字符
  + writeline：写入行
  + seek：定位指针，
    + from：0代表起始位置，1代表当前位置，2代表结尾
    + offset：偏移量
  + tell：返回在文件中当前位置

  + 遍历行

    ```python
    for line in f:
        print(line)
    ```


# 异常

+ 捕获

  ```python
  try:
      f = open("./test.txt")
      print(f.read())
      f.close()
  except OSError:
      print("报错了")
  except (OSError,EOFError) as error:
      print("报错了")
  except:
      print("捕获所有异常")
  finally:
      print("finally")
  ```

+ 主动抛出异常

  ```python
  raise OSError("test")
  ```

# else特殊用法

## 循环else

+ 循环正常结束时执行
+ 中途发生异常或者break，则不执行
+ 适用于`while、for`

```python
index = 0
while index < 10:
    index += 1
    print("index = %s"%index)
    if index == 8:
        break
else:
    print("正常结束")
```

## try/else

+ 不抛出任何异常时执行

  ```python
  try:
      int('abc')
  except ValueError:
      print("出错了")
  else:
      print("没错")
  ```

# with

## with使用

```python
try:
    f = open("./test.txt")
    print(f.read())
finally:
    f.close()
    print("finally")

# 等价于
with open("./test.txt") as f:
    print(f.read())
```

+ `open`支持上下文管理器，所以支持`with`语法
+ `open`中定义了`__enter__`和`__exit__`方法，实现了文件打开和关闭，所以不需要用户自己关心了

+ `with`支持同时嵌套

  ```python
  with nested(A(), B(), C()) as (X, Y, Z):
      # with-body code here
      
  # 等价于
  with A() as X:
      with B() as Y:
          with C() as Z:
              # with-body code here
  ```

## 自己实现支持with的类

```python
class Open:

    def __init__(self, filename, mode='r', encoding=None):
        self.filename = filename
        self.mode = mode
        self.encoding = encoding

    def __enter__(self):
        print("__enter__, 有了这个就可以使用with Open() as f语句，这里的f就是我return的内容")
        return self

    def read(self):
        print(f"文件进行读操作,读取文件：{self.filename!r}, 模式：{self.mode!r}, 编码：{self.encoding!r}")

    def __exit__(self, exc_type, exc_val, exc_tb):
        print("__exit__, 我是用来清理资源的，当操作执行完毕之后就会执行我，比如：关闭文件")
```

关键在于`__enter__`和`__exit__`方法，分别会在`with`开始和结束时被调用

# 类

## 定义

```python
class Student:
    name = "lilei"

    def play():
        print("happy")
```

## 继承

```python
class Student(People):
    # 不对父类进行任何变动则需使用pass
    pass

class Student(People):
    # self代表当前对象，相当于java中this
    def __init__(self,fname,lname):
        # 调用父类方法
        super.__init__(fname,lname)
        print(Student.__bases__) # 查看父类
```

## self

类中得方法的第一个参数必须是对象本身，一般用形参`self`

## 私有变量

```python
class Student:
    # 公有变量
    name = "lilei"
    # 前面加上双下划线，就是私有变量了
    __score = 20

    def play():
        print("happy")
        
s = Student()
print(s.__score)	# 抛异常
print(s._Student__score)	# 20
```

`python`的私有变量是`伪私有`，原理是将`__`开头的变量重命名为`_类名__变量名`，所以访问`__变量名`时访问不到，但是通过`_类名__变量名`一样能访问到

## 通过类调用对象方法

`python`中对象的概念，更偏向于`属性的集合`，不包含方法

`python`中所有的方法都是`static`的，所以

```python
s = Student()
s.play()
# 都可以写成
Student.play(s)
```

子类调用任何父类方法时，也可以

```python
class Student(People):

    def play(self):
        super().play()
        # 等价于
        People.play(self)
        print("lilei happy")
```

## 类对象、实例对象

```python
class People:
    count = 0

p1 = People()
p2 = People()

p1.count += 10

print(People.count)     # 0
print(p1.count)         # 10
print(p2.count)         # 0
```

+ 类中属性全都是`static`属性
+ 对象的属性没有被修改时，都是指向类属性的，类属性被修改时，对象属性同时被修改
+ 当对象属性被修改是，对象创建了1个新的属性并重新指向他

## BIF

+ issubclass

  判断是否为子类

  ```python
  issubclass(B,A)		# B子类  A父类
  ```

+ isinstance

  是否为类的实例对象

  ```python
  isinstance(b,B)
  ```

+ hasattr

  判断对象是否有指定属性

  ```python
  hasattr(b,'x')
  ```

+ getattr

  从对象中获取属性，可选指定默认值

  ```python
  getattr(b,'x',None)
  ```

+ setattr

  为对象设置属性

  ```python
  setattr(b,'x',1)
  ```

+ delattr

  删除对象中指定属性，不存在则抛出异常

  ```python
  delattr(b,'x')
  ```

+ property

  通过一个属性操作另一个属性

  ```python
  class A:
      def getSize(self):
          return self.size
      def setSize(self,size):
          self.size = size
      def delsize(self):
          del self.size
      x = property(getSize,setSize,delsize)
  
  # 通过操作A.x即可操作变量A.size，用于类被修改时，不想影响引用这个类的代码
  A.x = 0
  print(A.x)
  ```

## 魔法方法

+ `__new__`

  + 在`__init__`之前执行，用于返回实例对象，不常用，需要对返回实例对象进行修改时可以重写该方法

  + 例

    ```python
    class A:
        def __new__(cls,str):
            return str
    
    a = A('1234')
    print(a)    # 这里直接返回了字符串，而不是A的实例对象
    ```

+ `__init__`：构造方法

+ `__del__`

  + 析构方法，对象对垃圾回收器回收时被调用

  + 例

    ```python
    class A:
        def __del__(self):
            print("__del__被调用了")
    ```

+ `__add__`

  + 对象相加时执行

  + 例

    ```python
    class A(int):
        def __add__(self,other):
            return int.__add__(self,other)
    
    a = A(3)
    b = A(4)
    print(a + b)
    ```

+ `___setattr__`

  + 设置属性时运行

+ `___delattr__`

  + 删除属性时运行

+ `___getattribute__`

  + 尝试获取属性

+ `___getattr__`

  + 获取的属性不存在时运行

  + 例

    ```python
    class A(int):
        def __init__(self):
            self.test = 1
    
        def __getattr__(self,name):
            print("%s不存在"%name)
    
        def __getattribute__(self,name):
            print("%s存在"%name)
            return super().__getattribute__(name)
    
        def __setattr__(self,name,value):
            print("__setattr__")
            super().__setattr__(name,value)
        
        def __delattr__(self,name):
            print("delattr")
            super().__delattr__(name)
    
    a = A()
    print(a.test)
    print(a.x)
    a.x = 2
    del a.x
    
    # __setattr__
    # test存在
    # 1
    # x存在
    # x不存在
    # None
    # __setattr__
    # delattr
    ```

+ 描述符

  + 实现了下面任意方法的类，并且该类作为另一个类的属性使用时，就可以称之为1个描述符类

    + `__get__(self,instance,Owner)`
      + `self`：属性本身
      + `instance`：引用属性的实例
      + `Owner`：引用属性的类
    + `__set__(self,instance,value)`
    + `__delete__(self,instance)`

  + 可以用于对某个属性进行强化

  + 例：华氏度与摄氏度自动转换

    ```python
    class Celsius:
        def __init__(self,value=26.0):
            self.value = value
    
        def __get__(self,instance,Owner):
            return self.value
    
        def __set__(self,instance,value):
            self.value = value
    
    class Fahrenheit:
    
        def __get__(self,instance,Owner):
            return instance.cel * 1.8 + 32
    
        def __set__(self,instance,value):
            instance.cel = (value - 32) / 1.8
    
    class Temperature:
        cel = Celsius()
        fah = Fahrenheit()
    
    t = Temperature()
    t.cel = 38
    print(t.cel)    # 38
    print(t.fah)    # 100.4
    t.fah = 50  
    print(t.cel)    # 10.0
    print(t.fah)    # 50.0
    ```

  + 与`__getattribute__`区别

    + 如果想操作`Temperature`中的属性，`__getattribute__`需要定义在`Temperature`类中，而`__get__`定义在描述符类中
    + `__get__`用于定义对某一个属性的操作，而`__getattribute__`定义的是对类中所有属性的操作行为

+ 还有很多魔法方法，需要的时候自行百度吧

# 迭代器、生成器

## 迭代器

+ 通过如下两个方法可以操作迭代器

  + `iter`：获取迭代器对象
  + `next`：获取下一个值

+ 例

  ```python
  t = iter('flower')
  print(next(t))
  print(next(t))
  ```

+ `for ... in ...`就是调用的迭代器

+ 与之对应得魔法方法：`__iter__`、`__next__`

## 生成器

+ 使用了`yield`关键字得方法就是生成器

+ `yield`：遇到该关键字时，返回后面的值，下次再调用该方法时，从上次结束位置开始执行

+ 生成器可以被迭代

+ 例

  ```python
  def test():
      yield 1
      yield 2
  
  for i in test():
      print(i)
  ```

# 模块

## 自定义模块

+ 1个可调用得`py`文件就是1个模块

### 引用模块

```python
# 1.原始导入
import easygui
# 必须使用指定包名调用
easygui.msgbox()

# 2.重命名导入
import easygui as e
# 使用简称调用
e.msgbox()

# 3.从包中导入指定方法
from easygui import *
# 此时可以省略包名
msgbox()
```

### `if __name__ == "__main__"`

+ 在主程序中打印`__name__`得到的是`__main__`

+ 在被引入得模块中打印`__name__`得到的是模块名

+ 根据这个特性，可以通过`__name__`变量区分代码是主程序还是作为模块导入，来决定哪些代码只有作为主程序时才被执行

+ 例

  ```python
  # test.py
  def test1():
      print("test1")
  
  def test2():
      print("test2")
  
  if __name__ == "__main__":
      test2()
      
  # main.py
  import test
  
  test.test1()
  
  # 调用 ./test.py 时打印 test2
  # 调用 ./main.py 时打印 test1
  ```

### 搜索路径

+ 通过`sys.path`可以打印模块搜索路径

  ```python
  import sys
  print(sys.path)
  
  # ['/mnt/d/github/python-study/code', '/usr/lib/python38.zip', '/usr/lib/python3.8', '/usr/lib/python3.8/lib-dynload', '/usr/local/lib/python3.8/dist-packages', '/usr/lib/python3/dist-packages']
  ```

  + 前面的优先级更高
  + 第一个是当前文件所在路径

+ 添加搜索路径

  ```python
  import sys
  
  sys.path.append("/root")
  print(sys.path)
  ```

## 包

+ 定义包
  + 使用包名创建1个目录
  + 目录下创建名为`__init__.py`的空文件
  + 把需要的模块放在目录下
+ 使用时通过`包名.模块名`即可使用

## 常用模块

### 内置函数

#### range

+ `range(5)`：`0,1,2,3,4`
+ `range(1,5)`：`1,2,3,4`
+ `range(1,5,2)`：`1,3`

#### filter

```python
list1 = list(filter(lambda x: x%2=0,range(10)))
```

#### map

+ 类似于`java`中`stream().map()`，对集合数据加工后返回新的集合

  ```python
  list1 = list(map(lambda x:x*2,range(10)))
  ```

### random

+ 引入

  ```python
  import ramdom
  ```

+ 方法

  + `randint(MIN,MAX)`，生成指定范围的随机数

    ```python
    random.randint(0,5)
    ```

### os

+ 引入

  ```python
  import os
  ```

+ 方法

  + getcwd：获取当前目录
  + chdir：进入目录
  + listdir：获取当前目录列表
  + mkdir：创建目录
  + mkdirs：创建多层目录
  + remove：删除文件
  + rmdir：删除单层目录，目录非空则抛异常
  + rmdirs：删除多层目录，子目录到父目录递归删除，遇到非空目录则抛异常
  + rename：重命名
  + system：执行shell命令

+ 跨平台定义

  + os.curdir：当前目录`.`
  + os.pardir：父目录`..`
  + os.sep：返回当前系统路径分隔符，如：windows：`\\`，linux：`/`
  + os.linesep：返回当前系统休止符，如：windows：`\r\n`，linux：`\n`
  + os.name：输出操作系统

#### os.path

+ basename：单独返回文件名

  ```python
  import os.path
  print(os.path.basename("/data/test.sh"))
  ```

+ dirname：去掉文件名，返回路径

+ join：列表中字符串组合成路径

+ split：从路径最后一级进行拆分为2个元素的列表

  ```python
  print(os.path.split("/data/k8s/test.sh"))
  # ('/data/k8s', 'test.sh')
  ```

+ splitext：拆分扩展名

  ```python
  print(os.path.splitext("/data/k8s/test.sh"))
  # ('/data/k8s/test', '.sh')
  ```

+ getsize：获取文件大小，单位字节

+ getatime：获取文件最近访问时间

+ getctime：获取文件创建时间

+ getmtime：获取文件修改时间

+ exists：判断文件是否存在

+ isabs：判断是否为绝对路径

+ isdir：判断是否为目录

+ isfile：判断是否为文件

+ islink：判断是否为链接

+ ismount：是否为挂载点
+ samefile：是否指向同一个文件