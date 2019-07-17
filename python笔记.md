- 注释的快捷键：选中之后cmd+/

- 输出只用单引号就行(双引号也可以)而且他会自行运算

  如print 'helloworld'

  结果为helloworld

  print 100+200

  结果为300

- print语句中会把逗号，当成空格

  eg print 'a','b'   输出就是a b

  ​     print 'a'+'b'  输出就是ab，没有空格

  而且+不能连接不同数据类型，例如print 'a'+':',3，后面是数字前面是字符串不能用加号+连接，可以改成print 'a'+':'+'3'，这样是可以的，而且没有空格。

- python是动态语言，就是变量本身的类型是不固定的，在Python中，等号`=`是赋值语句，可以把任意数据类型赋值给变量，同一个变量可以反复赋值，而且可以是不同类型的变量，例如：

  ```
  a = 123    # a是整数
  print a
  a = 'imooc'   # a变为字符串
  print a
  ```

  这种**变量本身类型不固定的语言称之为动态语言，与之对应的是静态语言**。

  静态语言在定义变量时必须指定变量类型，如果赋值的时候类型不匹配，就会报错

- python里的字符串可以用单引号或者双引号表示都可以

  - 一般就用单引号。例如print 'helloworld'。
  - 但如果输出的本身有单引号，那就要用双引号了。如“I‘am OK”
  - 同样输出本身有双引号那就用单引号廓住
  - 如果既有单引号又有双引号就在字符串中的引号前面加转义字符\表示这是一个普通的字符而不是字符串的起始。如要表示字符串Bob said “I‘m OK”.就写成'Bob said\ "I\ 'm OK\ ".'
  - 如果一个字符串包含很多需要转义的字符，对每一个字符都进行转义会很麻烦。为了避免这种情况，直接用''' …….''' 即用三个单引号把中间的东西包住就行了

- 要使用中文需要在最前面加

  ```
  # -*- coding: utf-8 -*-
  ```

- c++和python在使用括号嵌套时不能用中括号，只能用小括号多层嵌套

- 整数的运算结果就是整数浮点数就是浮点数，但是整数和浮点数运算结果是浮点数。eg：10/4=2,但10.0/4=2.5

- > Python把`0`、`空字符串''`和`None`看成 False，其他数值和非空字符串都看成 True

  python中使用短路计算(首先要遵循上面那个大定义)

  - 在计算` a and b `时，如果 a 是 False，则根据与运算法则，整个结果必定为 False，因此返回 a；如果 a 是 True，则整个计算结果必定取决与 b，因此返回 b。

  - 在计算` a or b `时，如果 a 是 True，则根据或运算法则，整个计算结果必定为 True，因此返回 a；如果 a 是 False，则整个计算结果必定取决于 b，因此返回 b。

  所以Python解释器在做布尔运算时，只要能提前确定计算结果，它就不会往后算了，直接返回结果，如果只看前面确定不了，结果就根据后面的值决定。eg：

  ```
  a = 'python'
  print 'hello,', a or 'world'
  
  b = ''
  print 'hello,', b or 'world'
  ```

  输出结果为

  ```
  hello, python
  hello, world
  ```

  第一个a为非空字符串，真，后面是or因此无论后面是啥结果都是真，故取python

  第二个b为空字符串，假，后面是or因此整个表达式的取值就要看后面的了，world为真故取world。

- python中定义的list就类似于c++中的数组，a[3]就表示有三个元素a[0],a[1]a[2]

  在python里还有个可以倒着输出的表示但是数字顺序略有不同例如a[-1,],a[-2],a[-3]就相当于前面的a[2],a[1],a[0]

- 在list里插入元素使用insert().如在上面的a中加元素可以使用a.insert(0,'Paul'),

  两个参数，第一个表示插入的位置，第二个表示插的是什么。

- 删除的话用pop(),里面只有一个参数就是要删除元素的位置

- tuple是另一种有序的列表，中文翻译为“ 元组 ”。tuple 和 list 非常类似，但是，tuple一旦创建完毕，就不能修改了。

  同样是表示班里同学的名称，用tuple表示如下：

  ```
  >>> t = ('Adam', 'Lisa', 'Bart')
  ```

  创建tuple和创建list唯一不同之处是用`( )`替代了`[ ]`.但是获取t中的元素还是用[]

- 当tuple只有一个元素时，要在这个元素后面加个逗号不然会把括号当成表示运算优先级的括号。

  t=(1)

  输出就是1，因为把括号当成了运算优先级

  t=(1,)

  这样输出就是(1,),表示t是一个tuple

- c++中用else if，而python中用elif

  c++是if(...)                             python是if ……:

  ​           …………....;                                        …………......

  ​          else if(....  )                                   elif……:

  ​           …………....;                                        ………………...

- dict（字典）表示一个关键字和值得对应关系的集合，用{}表示

  如学生姓名list

  ['Adam', 'Lisa', 'Bart']

  和考试的成绩list

  [95, 85, 59]

  可以关联起来

  ```
  d = {
      'Adam': 95,
      'Lisa': 85,
      'Bart': 59
  }
  ```

  前面的名字叫key，后面的分数叫value，dict的作用就是根据key来找value

  > list和tuple是有序的，每个元素都有固定的顺序索引，而且内容是可以重复的，因为索引不一样；
  >
  > dict和set都是无序的，但是dict得key和set的元素内容是不能重复的。有时候我们只想要dict中的key而不想要value或者只想要value不要key，这个时候就可以用set，它和dict一样没有顺序但是不可重复。

  set相当于在list外面加了一层中括号，的表示方法为xxx=set([………………...])

  set的插入和删除使用s.add()和s.remove()。list使用insert()和pop()。往dict里面加元素直接用赋值语句就可以，d[key]=value

- 在list中插入元素除了用L.insert( ，)之外还可以用L.append(),后面这个append方法是在表的结尾加入指定元素，只有一个参数。

- 汉诺塔问题

  给a,b,c三个柱子，a上面放着n个圆盘，且都是下面的比上面的大，借助b全部移动到c上去，要求顺序一致

  代码为：

  ```
  def hanoi(n, a, b, c):
      if n == 1:
          print a, '-->', c
      else:
          hanoi(n - 1, a, c, b)
          print a, '-->', c
          hanoi(n - 1, b, a, c)
  hanoi(4, 'A', 'B', 'C')
  ```

  这里取n为4来测试结果是正确的，这里用的是递归的思想，把a上面的圆盘看成两部分，最下面的一块和的上面的n-1块，line 5意思是通过c把a上面的n-1块放到b上，line 7就是通过a把刚才放到b上的n-1块再放到c上。递归调用。

   **整个算法可以理解为三步：**(就是else下面的那三步)

  **1.先把A上的n-1个移动到B上**

  **2.把A上最大的那一个移动到C上**

  **3.再把刚才移动到B上的n-1个移动到C上**

- ### 默认参数与可变参数

  python函数一般有两个参数（也可以定义多个），但是必须参数必须在默认参数的前面，eg def abs（a,b=1）这样是可以的，但是def abs(a=1,b)这样就是错误的.默认参数的作用是简化调用，你只需要把必须的参数传进去。但是在需要的时候，又可以传入额外的参数来覆盖默认参数值。

  我们来定义一个计算 x 的N次方的函数:

  ```
  def power(x, n):
      s = 1
      while n > 0:
          n = n - 1
          s = s * x
      return s
  ```

  假设计算平方的次数最多，我们就可以把 n 的默认值设定为 2：

  ```
  def power(x, n=2):
      s = 1
      while n > 0:
          n = n - 1
          s = s * x
      return s
  ```

  这样一来，计算平方就不需要传入两个参数了：

  ```
  print power(5)
  25
  print power(5,3)
  123
  ```

  > 简言之默认参数就是为了方便，如果定义函数时默认参数有一个默认值，那么调用函数时如果不给默认参数赋值，就用默认值，如果赋新值就用新的

  可变参数的用法

  def average(*args)：

  举一个求平均数的例子

  ```
  def average(*args):
      sum=0.0
      if len(args)==0:
          return sum
      for x in args:
          sum+=x
      return sum/len(args)
  print average()
  print average(1, 2)
  print average(1, 2, 2, 3, 4)
  ```

  这样就可以传入很多参数，其实实际上是吧参数们都放到一个tuple里了，看成一个tuple就好了。

- 从list或tuple中取符合条件元素的切片操作

  例如L为一lis

  L[0:2]就表示从索引0开始取取到索引2为止但不包括索引2，即索引0，1。

  L[1:3]取的就是L[1],L[2]

  L[:]表示从头取到尾

  还可以有第三个参数表示每N个取一个，eg:L[::2]就表示从头取到尾而且每两个元素只取一个即L[0],L[2]……...

- 对字符串同样可以用切片操作slice，只是切片的结果还是字符串

  有个字符串方法upper()可以吧字符串变成大写字母，eg：'abc'.upper()，输出即为'ABC'.现在利用切片操作定义一个函数只让字符串的第一个字母变大写，

  ```
  def firstcharupper(s):
     return s[0].upper+s[1:]   ##此处用s[0:1]替换s[0]也可以
  print firstcharupper('hello')
  ```

  输出结果即为Hello

- 迭代和递归

  - 迭代是利用变量的原值推算出一个新值，即为了实现某个目的不断调用某个算法，即A不断调用B
  - 递归是自己调用自己，不断缩小问题的规模，将迭代中的A不断调用B中的B换成A即变为递归。

  递归中一定有迭代，但迭代中不一定有递归，递归是一种特殊的迭代，即刚好调用的是A本身，大部分可以相互转换.能用迭代的不用递归,递归调用函数,浪费空间,并且递归太深容易造成堆栈的溢出.

- 索引迭代，对于一个list，可以使用enumerate()方法为它的每个元素加上索引

  eg：

  ```
  L = ['Adam', 'Lisa', 'Bart', 'Paul']
  for index ,name in enumerate(L):
     print index+':'+name
  ```

  结果即为

  0 : Adam
  1 : Lisa
  2 : Bart
  3 : Paul

  enumerate()这个函数相当于是把L从['Adam', 'Lisa', 'Bart', 'Paul']变成了类似于[(0, 'Adam'), (1, 'Lisa'), (2, 'Bart'), (3, 'Paul')]**，但是要注意这么说是为了理解并不是真的变成一个新的list了，所以不能用L=enumerate(L)**

- dict的迭代

  - key的迭代直接用for key in **d**:
  - value的迭代用for value in **d.values()**:
  - key和value同时迭代用for key，value in **d.items()**:

- 在python中函数名其实就是指向函数的变量

  eg：求绝对值的函数abs（）

  abs(-1)

  结果即为1

  f=abs

  f(-1)

  结果也为1

  如果abs=len

  那么这是abs(-1)就会报错

  而abs([1,2,3])结果正确且输出3

- 了解了上面的函数名可以看做变量之后，我们就可以构造高阶函数，及能够接受函数作为参数的函数

  eg:

   def add(x,y,f)

  return f(x)+f(y)

  add(-5,9,abs）

  结果即为14，即把函数名看做指向函数的变量之后，就可以把函数看成变量从而当作参数，高阶函数的参数里面就有作为参数的函数

- map()函数为python中内置的一个高阶函数，两个参数，第一个参数是一个函数f(x)，第二参数是一个list，输出结果为将每个list中的元素执行函数f(x)后整合成的新的list。

  eg： def f(x)

  ​         return x*x

  ​         print  map(f,[1,2,3]）

  输出结果即为[1,4,9],只是形成一个新的list，但是并没有改变原来的list。

- 类似的高阶函数还有reduce和filter，reduce函数的参数函数f要有两个参数，每次操作两个数，最后输出一个数而不是一个新的list；filter()函数接收一个**函数 f** 和一个**list**，这个函数 f 的作用是对每个元素进行判断，返回 True或 False，**filter()根据判断结果自动过滤掉不符合条件的元素，返回由符合条件元素组成的新list。**

- 匿名函数，关键字为lambda(希腊字母中的拉姆达)

  例如用map函数的时候上面那种情况就可以写成map(lambda x:x*x [1,2,3])

  lambda表示这个函数是匿名函数，冒号前面的是参数（可以有多个），后面是函数的表达式，而且只能有一个表达式，不用写return，函数的返回结果直接就是表达式的值。

- import用来引用模块。平常写的一个xxx.py文件就是一个模块，import加上module name即可导入，eg import tensorflow。

  python中还有包package的概念，如果说模块是一个.py文件，那么一个包就是包含多个.py的文件夹（**注意区分包和普通的文件夹，包中的每一级目录都要有一个—init—.py文件，哪怕是空文件，而普通文件夹就随便了**），不同包中的模块是可以重名的，只要在导入前在module_name前面加上package_name.即可，eg：import a.fn,即为引入a包中的fn模块。

- try、except语句用来抓错误，没有错误就执行try后面正常的，捕捉到制定错误是执行except语句。

  ```
  try:
      from cStringIO import StringIO
  except ImportError:
      from StringIO import StringIO
  ```

  正常就从cStringIO安装，如果出现导入错误就执行except下面的，从StringIO安装。

- 类和对象

  ```
  class Person:
     address='china'       这个是定义了一个类属性
     def __init__(self,name,gender)：    初始化函数，每次创建对象都会调用这个函数，self是对象的引用，后面的参数是对象的属性
     self.name=name
     self.gender=gender
  xiaoming=Person('xiaoming','男)     创建对象
  xiaoming.addres   对象也是可以调用类属性的，但是当类属性和对象属性名字存在冲突时，先调用对象属性
  ```

- 表示x的y次方用x**y

- 定义对象方法直接在类中定义就可以，参数用(self)。定义类方法的话前面要加一个装饰器@classmethod，参数用(cls)，不加会被认为是对象方法。

- 类的继承，比如从Person类继承得Student类

  ```
  class Person(object):
      def __init__(self, name, gender):
          self.name = name
          self.gender = gender
  ```

  定义Student类从Person类继承，加了一个额外的属性score，加到初始化函数里，同时注意一定要在def __init__(self, name, gender):后面加一句super(Student, self).__init__(name, gender) 去初始化父类，否则，继承自 **Person** 的 **Student** 将没有 **name** 和 **gender**，相当于再重复一下父类的属性。

  ```
  class Student(Person):
      def __init__(self, name, gender, score):
          super(Student, self).__init__(name, gender)
          self.score = score
  ```

- 如何定义多个对象属性

  ```
  class Person(object):
      def __init__(self, name, gender, **kw):
          self.name=name
          self.gender=gender
          for k,v in kw.iteritems():
              setattr(self,k,v)
  p = Person('Bob', 'Male', age=18, course='Python')
  print p.age
  print p.course
  ```

  关键字**kw代表的意思就是多个属性，下面用一个循环

  for k,v in kw.iteritmes():

    setattr(self,k,v)

  这样就把**kw的属性加入到初始化类中了，直接print p.属性   就可以输出

- %s是一种格式化字符串显示的用法，例如在class Person中加一个--str--方法

- ```
  class Person(object):
      def __init__(self, name, gender):
          self.name = name
          self.gender = gender
      def __str__(self):
          return '(Person: %s, %s)'%(self.name,self.gender)
  ```

  p=Person('Bob','男')

  print p

  就会输出(Person:Bob,男)

  > %s的用法就是'(Person: %s, %s)'%(self.name,self.gender)，在要输出的东西了用%s来代替字符串的位置，然后后面跟一个%，%后面跟具体的要输出的东西

- gcd greatest common divisor(最大公因数)

  求最大公因数的函数

  ```
  def gcd(a,b):
     if b==0:
         return a
     return gcd(b,a%b)
  ```

  其实就是用了欧几里得算法，即辗转相除法（在数论中也有涉及）

  > a=k*b+c,则a，b的最大公约数等于b，c的最大公约数

- 
