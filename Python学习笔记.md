# Python编程学习

## 第一部分    基础知识

### 第1章  起步

#### 1.  搭建编程环境

##### 选择下载Anaconda，并在csdn上找到相关安装说明，然后按照说明一步步安装Anaconda并配置环境。

[[(17条消息) Anaconda安装-超详细版(2023)_anaconda版本如何选择_酷酷的懒虫的博客-CSDN博客](https://blog.csdn.net/weixin_43412762/article/details/129599741?ops_request_misc=%7B%22request%5Fid%22%3A%22169044075916800227440219%22%2C%22scm%22%3A%2220140713.130102334..%22%7D&request_id=169044075916800227440219&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_positive~default-1-129599741-null-null.142^v91^insert_down28v1,239^v3^control&utm_term=anaconda安装&spm=1018.2226.3001.4187)]:

### 第2章  变量和简单数据类型

#### 1. 变量

变量常被描述为可用于存储值的盒子。另一种定义是，变量是可以赋给值的标签，也可以说变量指向特定的值。

在程序中可随时修改变量的值，并始终记录变量的最新值。

示例：

```python
message = "come on !" #将变量message与文本"come on !"关联起来
print(message)  #将与变量message关联的值打印到屏幕上

message = "just so so !"
print(message)
```

这里我们先是添加了一个名为message的变量，**每个变量都指向一个值——与该变量相关的信息**，这里，指向的值为文本"come on !",接着我们修改变量message的值，并将其关联的值打印到屏幕上。

**==注意：变量命名规则==**

1. **变量名只能包含字母、数字和下划线。并且只能以字母或下划线开头，不能以数字开头。**
2. **变量名不能包含空格，但可以使用下划线来分隔单词。**
3. **不要将Python关键字和函数名用作变量名。**
4. **变量名要简短而具有描述性。**
5. **慎用小写字母l和大写字母O，易与数字1和0弄混**

#### 2. 字符串

字符串就是一系列的字符。在python中用引号引起的都是字符串，其中**引号可以是单引号也可以是双引号**。

这种灵活性使得在字符串中包含引号和撇号。

常用字符串操作

方法 title()

将每个单词的首字母都改为大写

示例：

```python
name = "xuanfeng xiao"
print(name.title())

#运行结果：Xuanfeng Xiao
```

补充：**方法**是python可对数据执行的操作，在name.title()中，（.）让python对变量name执行方法title()指定的操作，后面的()是因为方法通常需要额外的信息来完成其工作，这种信息在括号内提供，方法title()不需要额外信息故括号内为空。



方法 upper()

将字符串改为全部大写

示例：

```python
name = "xuanfeng xiao"
print(name.upper())

#运行结果：XUANFENG XIAO
```



方法 lower()

将字符串改为全部小写

示例：

```python
name = "xuanfeng xiao"
print(name.lower())

#运行结果：xuanfeng xiao
```



方法 format()

实现f字符串

示例：

```python
first_name = "xuanfeng"
last_name = "xiao"
full_name = "{} {}".format(first_name, last_name)
print(full_name)

#运行结果：xuanfeng xiao
```

在高版本python中实现f字符串也可以通过以下实现：

```python
first_name = "xuanfeng"
last_name = "xiao"
full_name = f"{first_name} {last_name}"
print(full_name)
```



字符串中添加制表符\t,换行符\n

示例：

```python
print("languages:\n\tPython\n\tC\n\tJava")

#运行结果：
#languages:
#	Python
#	C
#	Java
```

较少行的代码实现较多行的输出



删除空白

示例：

```python
message = " python "
print(message)
print(message.rstrip())
print(message.lstrip())
print(message.strip())

#运行结果：
# python 
# python
#python 
#python
```

方法 rstrip(),删除字符串末尾的空白

方法 lstrip(),删除字符串开头的空白

方法 strip(),删除字符串两边的空白

#### 3. 数

##### 整数

在python中可对整数执行加减乘除运算，终端会话中python直接返回运算结果。

python使用两个乘号表示乘方运算，同一表达式可使用多种运算，还可使用圆括号修改运算次序，空格不影响计算。

示例：

```python
a = 2 + 3
print(a)
a = 2 - 3
print(a)
a = 2 * 3
print(a)
a = 2 / 3
print(a)
a = 2 ** 3
print(a)
a = (2 + 3) * 4
print(a)

#运行结果是：
#5
#-1
#6
#0.6666666666666666
#8
#20
```

##### 浮点数

所有带有小数点的数称为浮点数。

**注意！**

结果包含的小数位数可能是不确定的。

任意两个数相除时，结果总是浮点数，即便两个数都是整数且能整除。

任何运算中，只要有操作数是浮点数，结果总是浮点数。



书写很大的数时，可使用下划线将其中的数字分组，使其清晰易读。

并且打印这种数时，下划线不会跟着打印。即便不按三位分组也不影响最终的值，因为python存储时会忽略下划线。

示例

```python
universe_age = 14_000_000_000

#运行结果：14000000000
```



##### 常量

常量类似于变量，但其值在程序的整个生命周期内保持不变。

python没有内置的常量类型，程序员通常使用**全大写**来指出应将某个变量视为常量。



### 第3章 列表

#### 1.列表简介

##### 1.1 列表是什么

列表由一系列按特定顺序排列的元素组成。列表通常包含多个元素，所以列表通常命名为复数。

在python中，用方括号表示列表，并于逗号分隔其中的元素。

示例：

```python
bicycles = ['trek','cannondale','redline','specialized']
print(bicycles)

#运行结果：['trek', 'cannondale', 'redline', 'specialized']
```

可见，将列表打印出来，将打印列表的内部表示，包括方括号。

##### 1.2 访问列表元素

列表是有序的，所以访问列表元素，只需将该元素的位置（**索引**），告诉python即可。

示例：

```python
bicycles = ['trek','cannondale','redline','specialized']
print(bicycles[0])

#运行结果：trek

bicycles = ['trek','cannondale','redline','specialized']
print(bicycles[0].title())

#运行结果：Trek
#运用title()方法，使首字母大写，看起来更整洁
```

**注意**：索引从**0**开始，而不是从1开始。

要访问第x个元素，索引为x-1。

访问列表最后一个元素还有一种特殊语法。通过将索引改为-1，就可访问列表最后一个元素。同理访问倒数列表第二个元素，索引可以为-2。这种语法适用于在不知道列表长度的情况下，访问最后一个元素。

示例：

```python
bicycles = ['trek','cannondale','redline','specialized']
print(bicycles[-1].title())

#运行结果：Specialized
```

```python
bicycles = ['trek','cannondale','redline','specialized']
message = f"my first bicycle was a {bicycles[0].title()}"
print(message)

#运行结果：my first bicycle was a Trek
```

##### 1.3 修改、添加和删除元素

创建的大多数列表将是动态的，这意味着列表创建后，可以随着程序运行而增删改元素。

###### 修改

要修改列表元素，可指定列表名和要修改的元素的索引，再指定该元素的新值。

示例：

```python
bicycles = ['trek','cannondale','redline','specialized']
print(bicycles)
bicycles[0] = 'fenghuang'
print(bicycles)

#运行结果：['trek', 'cannondale', 'redline', 'specialized']
#        ['fenghuang', 'cannondale', 'redline', 'specialized']
```

###### 添加

- 在列表末尾添加元素

在列表中添加新元素时，最简单的方式就是将元素**附加（append）**到列表，就是将新元素添加到列表末尾。

示例：

```python
bicycles = ['trek','cannondale','redline','specialized']
print(bicycles)
bicycles.append('fenghuang')
print(bicycles)

#运行结果：
#['trek', 'cannondale', 'redline', 'specialized']
#['trek', 'cannondale', 'redline', 'specialized', 'fenghuang']
```

方法append()将元素添加到列表末尾，而不影响到列表中的其他所有元素。

方法append()可以轻松实现动态创建列表。

示例：

```python
bicycles = []

bicycles.append('trek')
bicycles.append('cannondale')
bicycles.append('redline')
bicycles.append('specialized')

print(bicycles)

#运行结果：['trek', 'cannondale', 'redline', 'specialized']
```

- 在列表中插入元素

使用方法insert()可在列表的任何位置添加新元素，但需指定新元素的索引和值。这种操作还会使要插入索引及以后的元素右移一个位置。

示例：

```python
bicycles = ['trek','cannondale','specialized']

bicycles.insert(2, 'redline')

print(bicycles)

#运行结果：['trek', 'cannondale', 'redline', 'specialized']
```

###### 删除

- 使用del语句删除元素

如果知道要删除元素在列表中的位置，可使用del语句。

示例：

```python
bicycles = ['trek','cannondale','specialized','redline']

print(bicycles)

del bicycles[0]

print(bicycles)

#运行结果：
#['trek', 'cannondale', 'specialized', 'redline']
#['cannondale', 'specialized', 'redline']
```

- 使用方法pop()删除元素

如果将元素从列表中删除后，接着需要使用它的值，则使用方法pop()。

方法pop()删除列表末尾的元素，并让你能够接着使用它。

示例：

```python
bicycles = ['trek','cannondale','specialized','redline']

print(bicycles)

poped_bicycles = bicycles.pop()

print(bicycles)
print(poped_bicycles)

#运行结果：
#['trek', 'cannondale', 'specialized', 'redline']
#['trek', 'cannondale', 'specialized']
#redline
```

方法pop()还可以弹出任意位置的元素，需要在括号内填入指定的要删除的元素的索引即可

如果你要从列表中删除一个元素，且不再以任何方式使用它，就使用del语句；如果你要在删除元素后还能继续使用它，就使用方法pop()。

- 根据值删除元素

有时候，你不知道从列表中删除的值的位置，如果知道要删除元素的值，可使用方法remove()。

示例：

```python
bicycles = ['trek','cannondale','specialized','redline']

print(bicycles)

bicycles.remove('specialized')

print(bicycles)

#运行结果：
#['trek', 'cannondale', 'specialized', 'redline']
#['trek', 'cannondale', 'redline']
```

方法remove()删除元素后，还可接着使用它的值。

示例：

```python
bicycles = ['trek','cannondale','specialized','redline']

print(bicycles)

too_expensive = 'specialized'

bicycles.remove(too_expensive)

print(bicycles)

print(f"{too_expensive} is too expensive for me")

#运行结果：
#['trek', 'cannondale', 'specialized', 'redline']
#['trek', 'cannondale', 'redline']
#specialized is too expensive for me
```

**注意！** 方法remove()只删除第一个指定的值，如果要删除的值在列表中出现多次，就需要使用循环来确保将每个值都删除。

##### 1.4 组织列表

使用方法sort()对列表永久排序

按字母顺序永久性修改列表元素的排列顺序。

示例：

```python
bicycles = ['trek','cannondale','specialized','redline']

print(bicycles)

bicycles.sort()

print(bicycles)

#运行结果：
#['trek', 'cannondale', 'specialized', 'redline']
#['cannondale', 'redline', 'specialized', 'trek']
```

还可以按照与字母顺序相反的顺序排列列表元素，只需向方法sort()传递参数reverse=True即可。

示例：

```python
bicycles = ['trek','cannondale','specialized','redline']

print(bicycles)

bicycles.sort(reverse=True)

print(bicycles)

#运行结果：
#['trek', 'cannondale', 'specialized', 'redline']
#['trek', 'specialized', 'redline', 'cannondale']
```



使用函数sorted()对列表临时排序

要保留列表元素原来的排列顺序，同时以特定的顺序呈现它们，可使用函数sorted()。函数sorted()让你能够按特定顺序显示列表元素，同时不影响它们在列表中的原始排列顺序。

示例：

```python
bicycles = ['trek','cannondale','specialized','redline']

print("Here is the original list:")
print(bicycles)

print("\nHere is the sorted list")
print(sorted(bicycles))

print("\nHere is the original list:")
print(bicycles)

#运行结果：
#Here is the original list:
#['trek', 'cannondale', 'specialized', 'redline']
#
#Here is the sorted list
#['cannondale', 'redline', 'specialized', 'trek']
#
#Here is the original list:
#['trek', 'cannondale', 'specialized', 'redline']
```

同理如果要按照与字母顺序相反的顺序，也可向函数sorted()传递参数reverse=True。

示例：

```python
bicycles = ['trek','cannondale','specialized','redline']

print("Here is the original list:")
print(bicycles)

print("\nHere is the sorted list:")
print(sorted(bicycles,reverse=True))

print("\nHere is the original list again:")
print(bicycles)

#运行结果：
#Here is the original list:
#['trek', 'cannondale', 'specialized', 'redline']
#
#Here is the sorted list:
#['trek', 'specialized', 'redline', 'cannondale']
#
#Here is the original list again:
#['trek', 'cannondale', 'specialized', 'redline']
```

**注意！**如果并非所有的值都是小写时，按字母顺序排列列表要复杂一些，决定排列顺序时有多种解读大写字母的方式，要指定准确的排列顺序，会比较复杂。

##### 1.5 倒着打印列表

要反转列表的顺序可使用方法reverse()。

示例：

```python
bicycles = ['trek','cannondale','specialized','redline']

print("Here is the original list:")
print(bicycles)

bicycles.reverse()
print("\nHere is the sorted list:")
print(bicycles)

#运行结果：
#Here is the original list:
#['trek', 'cannondale', 'specialized', 'redline']
#
#Here is the sorted list:
#['redline', 'specialized', 'cannondale', 'trek']
```

**注意** reverse()不是按照字母顺序相反的顺序排列列表元素，而只是反转列表元素的排列顺序。方法revers()永久修改列表元素的排列顺序，但随时可恢复到原来的排列顺序，只需要对列表再次调用reverse()即可。

##### 1.6  确定列表长度

使用函数len()可快速获悉列表的长度。

示例：

```python
bicycles = ['trek','cannondale','specialized','redline']

lenth = len(bicycles)

print(lenth)

#运行结果：4
```

**注意**   计算列表长度时从1开始，不用差1，而列表索引不同，是从0开始的，需要差1。

#### 2.操作列表

##### 2.1 遍历整个列表

你经常需要遍历列表的所有元素，对每个元素执行相同的操作。

可使用for循环实现。

示例：

```python
bicycles = ['trek','cannondale','specialized','redline']
for bicycle in bicycles:
    print(bicycle)
    
#运行结果：
#trek
#cannondale
#specialized
#redline
```

在自行车列表中，取出一个，并将其与变量bicycle相关联，最后打印前面赋给变量bicycle的值。这样对于列表中的每一辆自行车，都将重复执行第2、3行的代码。

循环过程：

1. 首先读取第一行代码，获取列表bicycles中的第一个值'trek',并将其与变量bicycle相关联。
2. 接着读取下一行代码，打印bicycle的值，即‘trek’。由于列表中还包含其他值，所以返回到循环第一行，获取列表下一个名字'cannondale',并将其与变量bicycle相关联，重复如此，直至列表中没有其他值，执行for循环之后的代码，由于程序循环后没有其他代码，所有程序就此结束。

命名的意义：

for bicycle in bicycles: 这样的命名有助于明白for循环将对每个元素执行的操作，使用单数和复数可帮助判断处理的是单个列表元素还是整个列表。



for循环过程中执行更多操作

示例：

```python
bicycles = ['trek','cannondale','specialized','redline']
for bicycle in bicycles:
    print(f"{bicycle.title()},that was a great bicycle!")
    print(f"I will ride {bicycle.title()} next week.\n")
print("I love them!")

#运行结果：
#Trek,that was a great bicycle!
#I will ride Trek next week.
#
#Cannondale,that was a great bicycle!
#I will ride Cannondale next week.
#
#Specialized,that was a great bicycle!
#I will ride Specialized next week.
#
#Redline,that was a great bicycle!
#I will ride Redline next week.
#
#I love them!
```

**注意：**

1. for bicycle in bicycles:  ，冒号的作用是指告诉python，下面一行是循环的第一行。
2. 缩进问题，通过上述代码我们可以看到，第1、2个print每次循环都执行，但是第3个print只执行一次，因为第1、2个都缩进了，而第3个没有缩进。python会根据缩进判断代码行与前一个代码行的关系。为避免意外缩进错误，请只缩进需要缩进的代码。对于前面的代码，需要在for循环中执行的都要缩进，而循环后再执行的代码不需要缩进。

##### 2.2 创建数值列表

使用函数range()可以让你轻松生成一系列数。

示例：

```python
for value in range(1,5):
    print(value)
#运行结果：
#1
#2
#3
#4
```

**注意** range(1,5)生成的数是1-4，没有5。

调用函数range()时，也可以指定一个参数，这样它将要从0开始。

```python
for value in range(5):
    print(value)
 
#运行结果：
#0
#1
#2
#3
#4
```

使用range()创建数字列表

要创建数字列表可使用函数list()将range()的结果直接转换为列表。如果range()作为list()的参数，输出将是一个数字列表。

示例：

```python
numbers = list(range(1,6))
print(numbers)

#运行结果：[1, 2, 3, 4, 5]
```

使用range()函数时还可以设定步长，为此需要指定第三个参数。

示例：

```python
numbers = list(range(1,13,2))
print(numbers)

#运行结果：[1, 3, 5, 7, 9, 11]
```

从1开始数，不断加2，直到达到或超过终值13.

如何将前10个整数的平方加入到一个列表中呢？

示例：

```python
list =[]
for number in range(1,11):
    list.append(number**2)
print(list)

#运行结果：[1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
```

##### 2.3 对数字列表执行简单的统计计算

有几个专门处理数字列表的函数。

```python
list =[]
for number in range(1,11):
    list.append(number**2)
print(list)

num1 = min(list)
num2 = max(list)
num3 = sum(list)

print(f"the smallest number is {num1}\n")
print(f"the largest number is {num2}\n")
print(f"the sum of the list number is {num3}")

#运行结果：
#[1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
#the smallest number is 1
#
#the largest number is 100
#
#the sum of the list number is 385
```

求最小值的函数min()，求最大值的函数max()，求总和的函数sum()

##### 2.4 列表解析

列表解析将for循环和创建新元素的代码合并为一行，并自动附加新元素。

示例：

如何将前10个整数的平方加入到一个列表中呢？

```python
squares = [value**2 for value in range(1,11)]
print(squares)

#运行结果：[1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
```

使用这种语法，首先指定一个描述性的列表名，如squares。然后，指定一个左方括号，并定义一个表达式，用于生成要存储到列表中的值。接下来，编写一个for循环，用于给表达式提供值，再加上右方括号。

**注意** 这里的for语句末尾没有冒号。

##### 2.5 使用列表的一部分

###### 2.5.1 切片

已经学习了如何处理列表的所有元素，还可以处理列表的部分元素，python称之为切片。

要创建切片，可指定要使用的第一个元素和最后一个元素的索引。与函数range()一样，python在到达第二个索引之前的元素后停止。要输出列表中的前三个元素，需要指定索引0和3，这将返回索引为0、1和2的元素。

示例：

```python
players = ['charles','martina','florence','eli']
print(players[0:3])

#运行结果：['charles', 'martina', 'florence']
```

如上例，处理一个运动队队员列表，结果打印的是该列表的一个切片，其中只包含三名队员，输出也是列表，只包含前三名队员。由此我们可以生成列表的任意子集。

如果没有指定第一个索引，将自动从列表开头开始。

示例：

```python
players = ['charles','martina','florence','eli']
print(players[:3])

#运行结果：['charles', 'martina', 'florence']
```

同理若没有指定终止索引，切片将终止于列表末尾。

无论列表有多长，这种语法都能够让你输出从特定位置到列表末尾的所有元素。

```python
players = ['charles','martina','florence','eli']
print(players[1:])

#运行结果：['martina', 'florence', 'eli']
```

负数索引返回离队列末尾相应距离的元素，因此你可以输出列表末尾的任意切片。

示例：输出名单上最后三名队员

```python
players = ['charles','martina','florence','eli']
print(players[-3:])

#运行结果：['martina', 'florence', 'eli']
```

**注意：** 可在表示切片的方括号内指定第三个值。这个值告诉python在指定范围内每隔多少元素取一个。

示例：

```python
players = ['charles','martina','florence','eli']
print(players[0:3:2])

#运行结果：['charles', 'florence']
```

###### 2.5.2 遍历切片

如果要遍历列表的部分元素，可在for循环中使用切片。

示例：

```python
players = ['charles','martina','florence','eli']

print("Here are the first three players on my team:")
for player in players[:3]:
    print(player.title())
  
#运行结果：
#Here are the first three players on my team:
#Charles
#Martina
#Florence
```

###### 2.5.3 复制列表

复制过程，要复制列表可创建一个包含整个列表的切片，方法是同时省略起始索引和终止索引( [:] )。这让python可以复制一个始于第一个元素，终止于最后一个元素的切片，即整个列表的副本。

示例：一个列表包含你所喜欢的食物，恰好，你喜欢的食物，你朋友也喜欢。想再创建一个列表包含你朋友喜欢的食物，可以通过复制来实现这个列表：

```python
my_foods = ['pizza','falafel','carrot cake']
friend_foods = my_foods[:]

print("my favorite foods are:")
print(my_foods)

print("\nMy friend's favorite foods are:")
print(friend_foods)

#运行结果：
#my favorite foods are:
#['pizza', 'falafel', 'carrot cake']
#
#My friend's favorite foods are:
#['pizza', 'falafel', 'carrot cake']
```

**注意：** 我们可能会想当然认为friend_foods = my_foods也可以实现，但是这并不能得到两个列表。这里只是将my_foods赋给friend_foods,而不是将my_foods的副本赋给friend_foods。这种语法实际上是让python将新变量friend_foods关联到已与my_foods相关联的列表，因此两个变量指向同一个列表。

证明如下：

```python
my_foods = ['pizza','falafel','carrot cake']
friend_foods = my_foods[:]

print("my favorite foods are:")
print(my_foods)

print("\nMy friend's favorite foods are:")
print(friend_foods)

my_foods.append('cannoli')
friend_foods.append('ice cream')

print("\nmy favorite foods are:")
print(my_foods)

print("\nMy friend's favorite foods are:")
print(friend_foods)

#运行结果：
#my favorite foods are:
#['pizza', 'falafel', 'carrot cake']
#
#My friend's favorite foods are:
#['pizza', 'falafel', 'carrot cake']
#
#my favorite foods are:
#['pizza', 'falafel', 'carrot cake', 'cannoli']
#
#My friend's favorite foods are:
#['pizza', 'falafel', 'carrot cake', 'ice cream']
```

```python
my_foods = ['pizza','falafel','carrot cake']
friend_foods = my_foods

print("my favorite foods are:")
print(my_foods)

print("\nMy friend's favorite foods are:")
print(friend_foods)

my_foods.append('cannoli')
friend_foods.append('ice cream')

print("\nmy favorite foods are:")
print(my_foods)

print("\nMy friend's favorite foods are:")
print(friend_foods)

#运行结果：
#my favorite foods are:
#['pizza', 'falafel', 'carrot cake']
#
#My friend's favorite foods are:
#['pizza', 'falafel', 'carrot cake']
#
#my favorite foods are:
#['pizza', 'falafel', 'carrot cake', 'cannoli', 'ice cream']
#
#My friend's favorite foods are:
#['pizza', 'falafel', 'carrot cake', 'cannoli', 'ice cream']
```

#### 3.元组

列表非常适合于存储程序运行期间可能发生变化的数据集。有时候需要创建一系列不可修改的元素，元组可以满足这种需求。python将不能修改的值称为不可变的，而不可变的列表称为元组。

###### 3.1 定义元组

元组看起来像列表，但使用圆括号而不是中括号来标识。定义元组后，就可使用索引来访问其元素，就像访问列表元素一样。

示例：存储一不可变的矩形长和宽

```python
dimensions = (200,50)

print(dimensions[0])
print(dimensions[1])

#运行结果：
#200
#50
```

**注意：** 严格地说，元组是由逗号标识的，圆括号只是让元组看起来更加整洁、更清晰。如果你要定义一个只包含一个元素的元组，必须在这个元素后面加上逗号：

```python
my_t =(2,)

print(my_t[0])

#运行结果：
2
```

创建只包含一个元素的元组通常没有意义，但自动生成的元组有可能只有一个元素。

###### 3.2 遍历元组中的所有值

示例：

```python
dimensions = (200,50)
for dimension in dimensions:
    print(dimension)
  
#运行结果：
#200
#50
```

###### 3.3 修改元组变量

虽然不能修改元组的元素，但可以给存储元组的变量赋值。因此，如果要修改前述矩形的尺寸，可重新定义整个元组。

```python
dimensions = (200,50)

print("original dimensions:")
for dimension in dimensions:
    print(dimension)

diemnsions = (400,100)

print("\nModified dimensions:")
for dimension in dimensions:
    print(dimension)
  
#运行结果：
#original dimensions:
#200
#50
#
#Modified dimensions:
#200
#50
```

相比于列表，元组是更简单的数据结构。如果需要存储的一组值在程序的整个生命周期内都不变，就可以使用元组。

### 第4章  if语句

#### 1.简单示例

假设你有一个汽车列表，并想将其中每辆车的名称打印出来。对于大多数汽车，应以首字母大写的方式打印其名称，但对于汽车名‘bmw’，应以全大写的方式打印。

```python
cars = ['audi','bmw','subaru','toyota']

for car in cars:
    if car == 'bmw':
        print(car.upper())
    else:
        print(car.title())

#运行结果：
#Audi
#BMW
#Subaru
#Toyota
```

#### 2.条件测试

每条if语句的核心都是一个值为True或False的表达式，这种表达式称为条件测试。Python根据条件测试的值为True还是False来决定是否执行if语句中的代码。如果条件测试的值为True，Python就执行紧跟在if语句后面的代码；如果为False，Python就忽略这些代码。

##### 2.1  检查是否相等

大多数条件下测试将一个变量的当前值同特定值进行比较。最简单的条件测试检查变量的值是否与特定值相等。

```python
car = 'bmw'
print(car == 'bmw')

#运行结果:True
```

检查是否相等时会区分大小写。

示例：

```python
car = 'bmw'
print(car == 'Bmw')

#运行结果：False
```

如果大小写很重要，这种行为有其优点。但如果大小写不重要，只想检查变量的值，可将变量的值转换为小写，再进行比较。

```python
car = 'Bmw'
print(car.lower() == 'bmw')

#运行结果：True
```

##### 2.2 检查是否不相等

要判断两个值是否不等，可结合使用惊叹号和等号（！=）

```python
car = 'audi'
if car != 'auto':
    print("it is not your car!")
#运行结果：it is not your car!
```

##### 2.3  数值比较

检查数值非常简单。

可比较相等、不等、大于、小于、大于等于、小于等于等关系。

示例：

```python
age = 18
if age == 18:
    print("Yes")
if age != 18:
    print("No")
else:
    print("Yes")
if age >= 17:
    print("Yes")
    
#运行结果：
#Yes
#Yes
#Yes
```

