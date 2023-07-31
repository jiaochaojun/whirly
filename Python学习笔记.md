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

##### 2.4  检查多个条件

###### 2.4.1 使用and检查多个条件

要检查是否两个条件都为True，可使用关键字and将两个条件测试合而为一。如果每个测试都通过了，整个表达式的值为True；如果至少有一个测试没有通过，整个表达式就为False。

示例：

检查两个人的年龄是否都不小于21岁

```python
age_0 = 22
age_1 = 18
print(age_0 >= 21 and age_1 >=21)

age_1 = 22
print(age_0 >= 21 and age_1 >=21)

#运行结果：
#False
#True
```

为改善可读性，可将每个测试分别放在一对圆括号内，但并非必须这样做。

###### 2.4.2  使用or检查多个条件

关键字or也能够让你检查多个条件，但只要至少一个条件满足，就能通过整个测试。仅当两个测试都没有通过时，使用or的表达式才为False。

示例：

```python
age_0 = 22
age_1 = 18
print((age_0 >= 21) or (age_1 >=21))

age_0 = 20
print(age_0 >= 21 and age_1 >=21)

#运行结果：
#True
#False
```

##### 2.5  检查特定值是否包含在列表中

有时候，执行操作前必须检查列表是否包含特定的值。要判断特定的值是否已包含在列表中，可使用关键字in。

示例：

```python
banned_users =['andrew','carolina','david']
user = 'andrew'
print(user in banned_users)

#运行结果：True

banned_users =['andrew','carolina','david']
user = 'marie'
print(user in banned_users)

#运行结果：False

```

也可以使用关键字not in 确定特定的值未包含在列表中。

示例：

```python
banned_users =['andrew','carolina','david']
user = 'marie'

if user not in banned_users:
    print(f"{user.title()},you can post a response if you wish.")

#运行结果：Marie,you can post a response if you wish.
```

布尔表达式

它不过是条件测试的别名。与条件测试一样，布尔表达式的结果要么为True要么为False。布尔值通常用于记录条件，如游戏是否正在运行，或者用户是否可以编辑网站的特定内容，在跟踪程序状态或程序中重要条件方面，布尔值提供了一种高效的方式。

#### 3.if语句

理解了条件测试后，就可以开始编写if语句了。if语句有很多种，选择使用哪种取决于要测的条件数。

##### 3.1  简单的if语句

最简单的if语句只有一个测试和一个操作。

示例：

```python
age = 19

if age > 18:
    print("you are over 18 years old.")
    
#运行结果：you are over 18 years old.
```

先是条件测试，然后在紧跟在测试后面的缩进代码块中，可执行任何操作。如果测试结果为True，Python就会执行紧跟在if语句后面的代码，否则Python将忽略这些代码。

##### 3.2  if—else语句

我们通常需要在条件测试通过时执行一个操作，在没有通过时执行另一个操作。

示例：

```python
age = 17

if age > 18:
    print("you are over 18 years old.")
else:
    print("you are not over 18 years old.")

#运行结果：you are not over 18 years old.
```

if—else结构非常适合这种让python执行两种操作之一的情形。

##### 3.3  if-elif-else结构

我们通常需要检查超过两个的情形，为此可使用if-elif-else结构。Python只执行if-elif-else结构中的一个代码块，它依次检查每个条件测试，直到遇到了通过了的条件测试，将执行紧跟它后面的代码，并跳过余下的测试。

示例：

门票收费规则：

4岁以下免费；

4-18岁收取30元；

18岁（含）以上收起50元；

```python
age = 12

if age >= 18:
    print("you need to pay 50 yuan.")
elif age >= 4:
    print("you need to pay 30 yuan.")
else:
    print("you are free.")
    
#运行结果：you need to pay 30 yuan.

age = 12

if age >= 18:
    price = 50
elif age >= 4:
    price = 30
else:
    price = 0

print(f"you need to pay {price} yuan.")
#运行结果：you need to pay 30 yuan.
#第二种写法代码更加简洁
```

注意：

可根据需要使用任意数量的elif代码块。

可省略else代码块。在有些情况下，else代码块很有用；而在其他一些情况下，使用一条elif语句来处理特定的情形更加清晰。

##### 3.4  测试多个条件

if-elif-else结构功能虽然强大，但仅适合用于只有一个条件满足的情况：遇到通过了的测试后，python就跳过余下的测试，这种行为很好，效率很高，让你能够测试一个特定的条件。

然而，有时候必须检查你关心的所有条件。在这时，应使用一系列不包含elif和else代码块的简单if语句。在可能有多个条件为True且需要在每个条件为True时都采取相应措施时，适合使用这种方法。

示例：

披萨店点餐，根据客户点的配料进行添加配料。

```python
requested_toppings = ['mushrooms','extra cheese']

if 'mushrooms' in requested_toppings:
    print("Adding mushrooms.")
if 'pepperoni' in requested_toppings:
    print("Adding pepperoni.")
if 'extra cheese' in requested_toppings:
    print("Adding extra cheese.")

print("\nFinished making your pizza!")
   
#运行结果：
#Adding mushrooms.
#Adding extra cheese.
#
#Finished making your pizza!
```

总之，如果只想执行一个代码块，就使用 if-elif-else结构；如果要执行多个代码块，就使用一系列独立的if语句。

##### 3.5  使用if语句处理列表

###### 3.5.1  检查特殊元素

```python
requested_toppings = ['mushrooms','green peppers','extra cheese']

for requested_topping in requested_toppings:
    if requested_topping == 'green peppers':
        print("Sorry,we are out of green peppers right now.")
    else:
        print(f"Adding {requested_topping}")
print("\nFinished making your pizza!")

#运行结果：
#Adding mushrooms
#Sorry,we are out of green peppers right now.
#Adding extra cheese
#
#Finished making your pizza!
```

###### 3.5.2  确定列表不是空的

```python
requested_toppings = []

if requested_toppings:
    for requested_topping in requested_toppings:
        print(f"Adding {requested_topping}")
    print("\nFinished making your pizza!")
else:
    print("Are you sure you want a plain pizza?")
    
#运行结果：
#Are you sure you want a plain pizza?
```

###### 3.5.3  使用多个列表

```python
available_toppings = ['mushrooms','green peppers','extra cheese',
                      'olives','pepperoni','pineapple']

requested_toppings = ['mushrooms','french fries','extra cheese']

for requested_topping in requested_toppings:
    if requested_topping in available_toppings:
        print(f"Adding {requested_topping}")
    else:
        print(f"Sorry, we don't have {requested_topping}")
    
print("\nFinished making you pizzal.")

#运行结果：
#Adding mushrooms
#Sorry, we don't have french fries
#Adding extra cheese
#
#Finished making you pizzal.
```



if语句格式注意：

在诸如==、>=和<=等比较运算符两边各添加一个空格，比较好。这样的空格会使得代码阅读起来更容易。

### 第5章 字典

#### 1.使用字典

在python中，字典是一系列键值对。每个键都与一个值相关联，你可使用键来访问相关联的值。与键相关联的值可以是数、字符串、列表乃至字典。事实上，可以将任何Python对象用作字典中的值。

在Python中，字典用放在花括号中的一系列键值对来表示。

示例：

```python
alien_0 ={'color':'green','points':5}
```

键值对是两个相关联的值。指定键时，Python将返回与之相关联的值。键和值之间用冒号分隔，而键值对之间用逗号分隔。在字典中，想存储多少个键值对都可以。

最简单的字典只有一个键值对。

##### 1.1  访问字典中的值

要获取与键相关联的值，可依次指定字典名和放在方括号内的键。

示例：

```python
alien_0 ={'color':'green','points':5}
print(alien_0['color'])

#运行结果：green
```

字典中可包含任意数量的键值对。

##### 1.2  添加键值对

字典是一种动态结构，可随时在其中添加键值对。要添加键值对，可依次指定字典名、用方括号括起的键和相关联的值。

示例：

```python
alien_0 ={'color':'green','points':5}
print(alien_0)   

alien_0['x_position'] = 0
alien_0['y_position'] = 25
print(alien_0)

#运行结果：
#{'color': 'green', 'points': 5}
#{'color': 'green', 'points': 5, 'x_position': 0, 'y_position': 25}
```

##### 1.3  创建一个空字典

在空字典中添加键值对有时候可提供便利，而有时候必须这样做。为此，可先使用一对花括号定义一个字典，在分行添加各个键值对。

示例：

```python
alien_0 = {}

alien_0['color'] = 'green'
alien_0['points'] = 5

print(alien_0)

#运行结果：{'color': 'green', 'points': 5}
```

##### 1.4  修改字典中的值

要修改字典中的值，可依次指定字典名、用方括号括起的键，以及与该键相关联的新值。

```python
alien_0 = {'color':'green'}
print(f"The alien is {alien_0['color']}")

alien_0['color'] = 'yellow'
print(f"The alien is {alien_0['color']}")

#运行结果：
#The alien is green
#The alien is yellow
```

```python
alien_0 = {'x_position':0,'y_position':25,'speed':'medium'}
print(f"Original x_position:{alien_0['x_position']}")

if alien_0['speed'] == 'slow':
    x_increment = 1
elif alien_0['speed'] == 'medium':
    x_increment = 2
else:
    #外星人的速度一定很快
    x_increment = 3

alien_0['x_position'] = alien_0['x_position'] + x_increment
print(f"New x_position:{alien_0['x_position']}")

#运行结果：
#Original x_position:0
#New x_position:2
```

这种技术很好，通过修改外星人的字典中的值，可以改变外星人的行为。

##### 1.5  删除键值对

对于字典中不再需要的信息，可使用del语句将相应的键值对彻底删除。使用del语句时，必须指定字典名和要删除的键。

示例：

```python
alien_0 = {'color':'green','points':5}
print(alien_0)

del alien_0['points']
print(alien_0)

#运行结果：
#{'color': 'green', 'points': 5}
#{'color': 'green'}
```

注意：删除的键值对会永远消失。

##### 1.6  由类似对象组成的字典

在前面的示例中，字典存储的是一个对象的多种信息。但是，也可以用字典存储众多对象的同一种信息。

示例：

```python
favorite_languages = {
    'jen':'python',
    'sarah':'c',
    'edward':'ruby',
    'phil':'python',
    }
language = favorite_languages['sarah'].title()
print(f"Sarah's favorite language is {language}")

#运行结果：Sarah's favorite language is C
```

如示例所示，我们将一个较大的字典放在了多行中。每个键都是一个被调查者的名字，而每个值都是被调查者喜欢的语言。确定需要使用多行来定义字典时，要在输入左花括号后按回车键。在下一行缩进四个空格，指定第一个键值对，并在它后面加上一个逗号。定义好字典后，在最后一个键值对的下一行添加一个右花括号，并缩进四个空格，使其与字典中的键对齐。一种不错的做法是，在最后一个键值对后面也加上逗号，为以后在下一行添加键值对做好准备。

##### 1.7  使用get()来访问值

使用放在方括号内的键从字典中获取值时，可能会引发问题：如果指定的键不存在就会出错。

就字典而言，可使用方法get()，在指定的键不存在时返回一个默认值，从而避免这样的错误。

方法get()的第一个参数用于指定键，是必不可少的；第二个参数为指定的键不存在时要返回的值，是可选的：

示例：

```python
alien_0 = {'color':'green','speed':'slow'}

point_value = alien_0.get('points','No point value assigned')
print(point_value)

#运行结果：No point value assigned
```

如果字典中有’points‘，将获得与之相关联的值；如果没有，将获得指定的默认值。虽然这里没有键’points‘，但将获得一条清晰的消息，不会引发错误。如果指定的键有可能不存在，应考虑使用方法get()，而不要使用方括号表示法。

**注意：**  调用get()时，如果没有指定第二个参数且指定的键不存在，Python将返回值None。这个特殊值表示没有相应的值。None并非错误，而是一个表示所需值不存在的特殊值。

#### 2.遍历字典

##### 2.1  遍历所有键值对

示例：

```python
user_0 = {
    'username':'efermi',
    'first':'enrico',
    'last':'fermi',
    }

for key,value in user_0.items():
    print(f"\nKey:{key}")
    print(f"Value:{value}")

#运行结果：
#Key:username
#Value:efermi
#
#Key:first
#Value:enrico
#
#Key:last
#Value:fermi
```

for语句的第二部分包含字典名和方法items()，它返回一个键值对列表。接下来，for循环依次将每个键值对赋给指定的两个变量。

##### 2.2  遍历字典中的所有键

在不需要使用字典中的值时，方法keys()很有用。

示例：

```python
favorite_languages = {
    'jen':'python',
    'sarah':'c',
    'edward':'ruby',
    'phil':'python',
    }
for name in favorite_languages.keys():
    print(name.title())
    
#运行结果：
#Jen
#Sarah
#Edward
#Phil
```

**注意：** 遍历字典时，会默认遍历所有键。因此显式地使用方法Keys()可让代码容易理解，但你也可以选择省略它。

示例：

```python
favorite_languages = {
    'jen':'python',
    'sarah':'c',
    'edward':'ruby',
    'phil':'python',
    }
for name in favorite_languages:
    print(name.title())
    
#运行结果：
#Jen
#Sarah
#Edward
#Phil
```

并且在这种循环中，我们也可以使用当前键来访问与之相关联的的值。

```python
favorite_languages = {
    'jen':'python',
    'sarah':'c',
    'edward':'ruby',
    'phil':'python',
    }

friends = ['phil','sarah']

for name in favorite_languages:
    print(f"Hi {name}")
    
    if name in friends:
        language = favorite_languages[name].title()
        print(f"\t{name.title()}, I see you love {language}!")

#运行结果：
#Hi jen
#Hi sarah
#	Sarah, I see you love C!
#Hi edward
#Hi phil
#	Phil, I see you love Python!
```

示例：

```python
favorite_languages = {
    'jen':'python',
    'sarah':'c',
    'edward':'ruby',
    'phil':'python',
    }

if 'erin' not in favorite_languages.keys():
    print("Erin, please take our poll!")
    
#运行结果：Erin, please take our poll!
```

方法keys()并非只能用于遍历：实际上，它返回一个列表，其中包含字典中的所有键。所以检测到’erin‘，不在列表中，打印一条消息。

##### 2.3  按特定顺序遍历字典中的所有键

从python3.7开始，遍历字典时将按插入的顺序返回其中的元素。不过在有些情况下，你可能要按照与此不同的顺序遍历字典。

要以特定顺序返回元素，一种办法是在for循环中对返回的键进行排序。为此，可使用函数sorted()来获得按特定顺序排列的键列表副本：

示例：

```python
favorite_languages = {
    'jen':'python',
    'sarah':'c',
    'edward':'ruby',
    'phil':'python',
    }


for name in sorted(favorite_languages.keys()):
    print(f"{name.title()}, thank you for taking the poll.")
#运行结果：
#Edward, thank you for taking the poll.
#Jen, thank you for taking the poll.
#Phil, thank you for taking the poll.
#Sarah, thank you for taking the poll.
```

##### 2.4  遍历字典中的所有值

如果主要对字典包含的值感兴趣，可使用方法values()来返回一个值列表，不包含任何键。

示例：

```python
favorite_languages = {
    'jen':'python',
    'sarah':'c',
    'edward':'ruby',
    'phil':'python',
    }


print("The following languages have been mentioned:")
for language in favorite_languages.values():
    print(language.title())

#运行结果：
#The following languages have been mentioned:
#Python
#C
#Ruby
#Python
```

这种提取方法显然没有考虑重复项。为剔除重复项，可使用集合（set）。集合中的每个元素都必须是独一无二的。

```python
favorite_languages = {
    'jen':'python',
    'sarah':'c',
    'edward':'ruby',
    'phil':'python',
    }


print("The following languages have been mentioned:")
for language in set(favorite_languages.values()):
    print(language.title())
    
#运行结果：
#The following languages have been mentioned:
#Ruby
#C
#Python
```

通过对包含重复元素的列表调用set()，可让Python找出列表中独一无二的元素，并使用这些元素来创建一个集合。结果是一个不重复的列表。

**注意：**  可使用一对花括号直接创建集合，并在其中用逗号分隔元素：

示例：

```python
languages = {'python','ruby','python','c'}
print(languages)

#运行结果：{'ruby', 'python', 'c'}
```

集合和字典很容易混淆，因为它们都是一对花括号定义的。当花括号内没有键值对时，定义的很可能是集合。不同于列表和字典，集合不会以特定的顺序存储元素。

#### 3.嵌套

有时候，需要将一系列字典存储在列表中，或将列表作为值存储在字典中，这称为嵌套。你可以在列表中嵌套字典、在字典中嵌套列表甚至在字典中嵌套字典。

##### 3.1  字典列表

示例：

```python
alien_0 = {'color':'green','points':5}
alien_1 = {'color':'yellow','points':10}
alien_2 = {'color':'red','points':15}

aliens = [alien_0,alien_1,alien_2]

for alien in aliens:
    print(alien)

#运行结果：
#{'color': 'green', 'points': 5}
#{'color': 'yellow', 'points': 10}
#{'color': 'red', 'points': 15}
```

示例：

```python
aliens = []

for alien_number in range(30):
    new_alien = {'color':'green','points':5,'speed':'slow'}
    aliens.append(new_alien)

for alien in aliens[:5]:
    print(alien)
    
print("...")
print(f"Total number of aliens:{len(aliens)}")

#运行结果：
#{'color': 'green', 'points': 5, 'speed': 'slow'}
#{'color': 'green', 'points': 5, 'speed': 'slow'}
#{'color': 'green', 'points': 5, 'speed': 'slow'}
#{'color': 'green', 'points': 5, 'speed': 'slow'}
#{'color': 'green', 'points': 5, 'speed': 'slow'}
#...
#Total number of aliens:30
```

在本例中首先创建一个空列表，用于存储接下来要被创建的所有外星人。range()返回一系列数，唯一的用途是告诉Python要重复这个循环多少次。每次执行这个循环时，都创建一个外星人，并将其附加到列表aliens末尾。使用一个切片来打印前5个外星人。打印列表长度，以证明确实创建了30个外星人。

这些外星人都具有相同的特征，但又都是独立的，我们可以独立地修改每个外星人。

##### 3.2  在字典中存储列表

有时候，需要将列表存储在字典中，而不是将字典存储在列表中。

示例：

```python
pizza = {
    'crust':'thick',
    'toppings':['mushrooms','extra cheese'],
    }

print(f"You ordered a {pizza['crust']}-crust pizza "
      "with the following topping:")

for topping in pizza['toppings']:
    print("\t" + topping)
    
#运行结果：
#You ordered a thick-crust pizza with the following topping:
#	mushrooms
#	extra cheese
```

如果函数调用print()中的字符很长，可以在合适的位置分行。只需要在每行末尾都加上引号，同时对于除第一行外 的其他各行，都在行首加上引号并缩进。这样，python将自动合并圆括号内的所有字符串。

示例：

```python
favorite_languages = {
    'jen':['python','ruby'],
    'sarah':['c'],
    'edward':['ruby','go'],
    'phil':['python','haskell'],
    }

for name,languages in favorite_languages.items():
    print(f"\n{name.title()}'s favorite languages are:")
    for language in languages:
        print(f"\t{language.title()}")
        
#运行结果：
#Jen's favorite languages are:
#	Python
#	Ruby
#
#Sarah's favorite languages are:
#	C
#
#Edward's favorite languages are:
#	Ruby
#	Go
#
#Phil's favorite languages are:
#	Python
#	Haskell
```

注意：列表和字典的嵌套层级不应太多。如果嵌套层级比前面的示例多得多，很可能有更简单的解决方案。

##### 3.3  在字典中存储字典

可在字典中嵌套字典，但这样做时，代码可能很快复杂起来。

示例：

```python
users = {
    'aeinstein':{
        'first':'albert',
        'last':'einstein',
        'location':'princeton',
        },
    'mcurie':{
        'first':'marie',
        'last':'curie',
        'location':'paris',
        },
    }

for username,user_info in users.items():
    print(f"\nUsername:{username}")
    full_name = f"{user_info['first']}{user_info['last']}"
    location = user_info['location']
    
    print(f"\tFull name:{full_name.title()}")
    print(f"\tLocation:{location.title()}")
    
#运行结果：
#Username:aeinstein
#	Full name:Alberteinstein
#	Location:Princeton
#
#Username:mcurie
#	Full name:Mariecurie
#	Location:Paris
```

### 第6章  用户输入和while循环

#### 1.用户输入

##### 1.1  函数input()的工作原理

函数input()让程序暂停运行，等待用户输入一些文本。获取用户输入后，Python将其赋给一个变量，以方便使用。

示例：

```python
message = input("Tell me something, and I will repeat it back to you: ")
print(message)

#运行结果：
#Tell me something, and I will repeat it back to you: hello
#hello
```

每当使用函数input()时，都应指定清晰易懂的提示，准确地指出希望用户提供什么样的信息，指出用户应该输入何种信息的任何提示都行，通过在提示末尾冒号后面包含一个空格，可将提示与用户输入分开，让用户清楚地知道其输入始于何处。有时候提示可能超过一行。例如，你可能需要指出获取特定输入的原因。在这种情况下，可将提示赋给一个变量，再将该变量传递给函数input()。这样，即便提示超过一行，input()语句也会非常清晰。

示例：

```python
prompt = "If you tell us who you are, we can personalize the messages you see."
prompt += "\nWhat is your first name? "

name = input(prompt)
print(f"\nHello,{name}!")

#运行结果：
#If you tell us who you are, we can personalize the messages you see.
#What is your first name? chaojun
#
#Hello,chaojun!
```

本例演示了一种创建多行字符串的格式。第一行将消息的前半部分赋给变量prompt中。在第二行中，运算符+=在前面赋给变量prompt的字符串末尾附加一个字符串。最终的提示占据两行，且问号后面有一个空格，这也是为了使其更加清晰。

##### 1.2  使用int()来获取数值输入

使用函数int()时，Python将用户输入解读为字符串。如果只需要打印输出，并没有什么问题。但是如果试图将输入作为数来使用，就会引发错误。因为它无法将字符串和整数进行比较。为了解决这个问题，可使用函数int()，它让Python将输入视为数值。函数int()将数的字符串表示转换为数值表示。

示例：

```python
age = input("How old are you? ")

age = int(age)
if age > 12:
    print("Yes")
    
#运行结果：
#How old are you? 19
#Yes
```

将数值输入用于计算和比较前，务必将其转换为数值表示。

##### 1.3  求模运算符

处理数值信息时，求模运算符%是个很有用的工具，它将两个数相除并返回余数。

#### 2.while循环

for循环用于针对集合中的每个元素都执行一个代码块，而while循环则不断运行，直到指定的条件不满足为止。

##### 2.1  使用while循环

可用while循环来数数。

```python
current_number = 1
while current_number <= 5:
    print(current_number)
    current_number += 1
    
#运行结果：
#1
#2
#3
#4
#5
```

##### 2.2  让用户选择何时退出

可以使用while循环让程序在用户愿意时不断运行。

示例：我们可以定义一个退出值，只要用户输入的不是这个值，程序就接着运行。

```python
prompt = "\nTell me something, and I will repeat it back you:"
prompt += "\nEnter 'quit' to end the progrem. "

message = ""
while message != 'quit':
    message = input(prompt)
    
    if message != 'quit':
        print(message)
#运行结果：
#Tell me something, and I will repeat it back you:
#Enter 'quit' to end the progrem. hello
#hello
#
#Tell me something, and I will repeat it back you:
#Enter 'quit' to end the progrem. quit
```

##### 2.3  使用标志

在更复杂的程序中，很多不同的事件会导致程序停止运行。如果在一条while语句中检查所有条件，将会既复杂又困难。在要求很多条件都满足才继续运行的程序中，可定义一个变量，用于判断整个程序是否处于活动状态。这个变量称为标志，充当程序的交通信号灯。可以让程序在标准为True时运行，在False时停止运行。这样while语句中就只需要检查一个条件：标志的当前值是否为True。然后所有其他测试（是否发生改变，应将标志设置为False事件）都放在其他地方，从而使程序更整洁。

示例：

```python
prompt = "\nTell me something, and I will repeat it back you:"
prompt += "\nEnter 'quit' to end the progrem. "

active = True
while active:
    message = input(prompt)
    
    if message == 'quit':
        active = False
    else:
        print(message)
        
#运行结果：
#Tell me something, and I will repeat it back you:
#Enter 'quit' to end the progrem. hello
#hello
#
#Tell me something, and I will repeat it back you:
#Enter 'quit' to end the progrem. quit
```

##### 2.4  使用break退出循环

要立即退出while循环，不在运行循环中余下的代码，也不管条件测试的结果如何，可使用break语句。break语句用于控制控制程序流程，可控制哪些代码行将执行、哪些代码行不执行，从而让程序按你的要求执行你要执行的代码。

示例：

```python
prompt = "\nPlease enter the name of a city you have visited:"
prompt += "\n(Enter 'quit' when you are finished.) "

while True:
    city = input(prompt)
    
    if city == 'quit':
        break
    else:
        print(f"I'd love to go to {city.title()}")
        
#运行结果：
#Please enter the name of a city you have visited:
#(Enter 'quit' when you are finished.) chong qing
#I'd love to go to Chong Qing
#
#Please enter the name of a city you have visited:
#(Enter 'quit' when you are finished.) nan jing
#I'd love to go to Nan Jing
#
#Please enter the name of a city you have visited:
#(Enter 'quit' when you are finished.) quit
```

以while True打头的循环将不断运行，直到遇到break语句。

在任何python的循环中都可以用break语句。例如可使用break语句来退出遍历列表或字典的for循环。

##### 2.5  在循环中使用continue

要返回循环开头，并根据条件测试结果，决定是否继续执行，可使用continue语句，它不像break语句那样不再执行余下的代码并退出整个循环。

示例：

```python
current_number = 0
while current_number < 10:
    current_number += 1
    if current_number % 2 == 0:
        continue
    
    print(current_number)

#运行结果：
#1
#3
#5
#7
#9
```

避免无限循环

每个while循环都必须停止运行的途径，这样才不会没完没了地执行下去。

如果程序陷入无限循环，可按Ctrl+C，也可关闭显示程序输出的终端窗口。

##### 2.6  使用while循环处理列表和字典

目前为止，我们每次都只处理了一项用户信息：获取用户的输入，再将输入打印出来或做出应答；循环再次运行时，获悉另一个输入值并作出响应。然而，要记录大量的用户和信息，需要在while循环中使用列表和字典。

###### 2.6.1  在列表之间移动元素

示例：

```python
unconfirmed_users = ['alice','brian','candace']
confirmed_users = []

while unconfirmed_users:
    current_user = unconfirmed_users.pop()
    
    print(f"Verifying user:{current_user.title()}")
    confirmed_users.append(current_user)
    
print("\nThe following users have been confirmed:")
for confirmed_user in confirmed_users:
    print(confirmed_user.title())
    
#运行结果：
#Verifying user:Candace
#Verifying user:Brian
#Verifying user:Alice
#
#The following users have been confirmed:
#Candace
#Brian
#Alice
```

###### 2.6.2  删除为特定值的所有列表元素

前面我们使用函数remove()来删除列表中的特定值。这之所以可行是因为要删除的值只在列表中出现一次，如果要删除列表中所有为特定值的元素，该怎么办呢？

示例：

```python
pets = ['dog','cat','dog','goldfish','cat','rabbit','cat']
print(pets)

while 'cat' in pets:
    pets.remove('cat')
    
print(pets)

#运行结果：
#['dog', 'cat', 'dog', 'goldfish', 'cat', 'rabbit', 'cat']
#['dog', 'dog', 'goldfish', 'rabbit']
```

###### 2.6.3  使用用户输入来填充字典

可使用while循环提示用户输入任意多的信息。

示例：

```python
responses = {}

#设置一个标志，指出调查是否继续。
polling_active = True

while polling_active:
    
    #提示输入被调查者的姓名和回答。
    name = input("\nWhat is your name?")
    response = input("Which moutain would you like to climb someday? ")
    
    #将回答存储在字典中。
    responses[name] = response
    
    #看看是否还有人要参与调查。
    repeat = input("Would you like to let another person respond?(yes/no) ")
    if repeat == 'no':
        polling_active = False

#调查结束，显示结果。
print("\n---Poll Results---")
for name,response in responses.items():
    print(f"{name} would like to climb {response}.")
    
#运行结果：
#What is your name?Li hua
#Which moutain would you like to climb someday? Mountain Tai
#Would you like to let another person respond?(yes/no) no
#
#---Poll Results---
#Li hua would like to climb Mountain Tai.
```

### 第7章 函数

函数是带名字的代码块，用于完成具体的工作。要执行的函数定义的特定任务，可调用该函数。需要在程序中多次执行同一项任务时，无需反复编写完成该任务的代码，只需要调用执行该任务的函数。

#### 1.定义函数

示例：

```python
def greet_user():
    """显示简单的问候语。"""
    print("Hello!")
    
greet_user()

#运行结果：Hello!
```

关键字def告诉python，我要定义一个函数。向python指出了函数名，还可能在圆括号内指出函数为完成任务需要什么样的信息。在这里，函数名为greet_user(),不需要任何信息就可以完成任务，所有括号内是空的。（**注意**： 即便不需要任何其他信息，括号也不可少），最后定义以冒号结尾。跟在后面缩进的代码块构成了函数体。第二行的文本称为文档字符串的注释，描述了函数是做什么的。文档字符串用三引号括起，python使用它们生成有关程序中函数的文档。要使用这个函数，就调用它。调用函数，可依次指定函数名以及用圆括号括起的必要信息。

##### 1.1  向函数传递信息

示例：

```python
def greet_user(username):
    """显示简单的问候语。"""
    print(f"Hello,{username.title()}!")
    
greet_user('jesse')

#运行结果：Hello,Jesse!
```

这里就实现了将用户名传递给greet_user（）函数。

##### 1.2  实参和形参

如上例中，函数greet_user()的定义中，变量username是一个形参，即函数完成工作所需信息。在代码greet_user('jesse')中，值‘jesse’是一个实参，即调用函数时传递给函数的信息。在代码greet_user('jesse')中，将实参‘jesse’传递给了函数greet_user()，这个值被赋给了形参username。

#### 2.传递实参

函数定义中可能包含多个形参，因此函数调用中也可能包含多个实参。向函数传递实参的方式很多：可使用**位置实参**，这要求实参的顺序与形参的顺序相同；也可使用**关键字实参**，其中每个实参都由变量名和值组成；还可使用**列表和字典**。

##### 2.1  位置实参

调用函数时，必须将函数调用中的每个实参都关联到函数定义中的一个形参。为此，最简单的关联方式是基于实参的顺序。这种关联方式称为位置实参。

示例：

```python
def describe_pet(animal_type,pet_name):
    """显示宠物信息。"""
    print(f"\nI have a {animal_type}")
    print(f"My {animal_type}'s name is {pet_name}")
    
describe_pet('hamster','harry')

#运行结果：
#I have a hamster
#My hamster's name is harry
```

在函数调用中，实参‘hamster’被赋给形参animal_type，实参‘harry’被赋给形参pet_name。

可根据需要多次调用函数。

```python
def describe_pet(animal_type,pet_name):
    """显示宠物信息。"""
    print(f"\nI have a {animal_type}")
    print(f"My {animal_type}'s name is {pet_name}")
    
describe_pet('hamster','harry')
describe_pet('dog','Willie')

#运行结果：
#I have a hamster
#My hamster's name is harry
#
#I have a dog
#My dog's name is Willie
```

在函数中，可根据需要使用任意数量的位置实参，python将按顺序将函数调用中的实参关联到函数定义中相应的形参。

**位置实参的顺序很重要！！！**

##### 2.2  关键字实参

关键字实参是传递给函数的名称值对。因为直接在实参中将名称和值关联起来，所以向函数传递实参时，不会混淆。

示例：

```python
def describe_pet(animal_type,pet_name):
    """显示宠物信息。"""
    print(f"\nI have a {animal_type}")
    print(f"My {animal_type}'s name is {pet_name}")
    
describe_pet(animal_type = 'hamster',pet_name = 'harry')
describe_pet(animal_type = 'dog',pet_name = 'Willie')

#运行结果：
#I have a hamster
#My hamster's name is harry
#
#I have a dog
#My dog's name is Willie
```

注意：关键字实参的顺序无关紧要，因为python已经知道应该将实参分别赋给哪个形参。

```python
def describe_pet(animal_type,pet_name):
    """显示宠物信息。"""
    print(f"\nI have a {animal_type}")
    print(f"My {animal_type}'s name is {pet_name}")
    
describe_pet(pet_name = 'harry',animal_type = 'hamster')

#运行结果：
#I have a hamster
#My hamster's name is harry
```

注意：使用关键字实参时，务必准确指定函数定义中的形参名。

##### 2.3  默认值

编写函数时，可给每个形参指定默认值，在调用函数时，给形参提供了实参时，python将使用指定的实参值；否则，将使用形参的默认值。形参设定默认值后，可在函数调用中省略相应的实参。使用默认值可简化函数调用，还可清楚地指出函数的典型用法。

示例：

比如上面宠物信息函数，如果你发现大多数宠物是小狗，那么你可以将形参animal_type的默认值设置为’dog‘。这样调用函数描述小狗时，就可不提供这种信息：

```python
def describe_pet(pet_name,animal_type='dog'):
    """显示宠物信息。"""
    print(f"\nI have a {animal_type}")
    print(f"My {animal_type}'s name is {pet_name.title()}")
    
describe_pet(pet_name = 'willie')

#运行结果：
#I have a dog
#My dog's name is Willie
```

**注意：** 这里修改了形参的排列顺序，函数调用时只包含一个实参，视为位置实参，所以形参的顺序要改变。

即：使用默认值时，必须先在形参列表中列出没有默认值的形参，再列出有默认值的实参。

##### 2.4  等效的函数调用

鉴于可混合使用位置实参、关键字实参和默认值，通常有多种等效的函数调用方式。

如上例所示，animal_type提供了默认值，所以在任何情况下都必须给pest_name提供实参。指定该实参时可采用位置方式或者关键字方式。如果描述的不是小狗，还必须在函数调用中给animal_type提供实参。同样指定该实参时，可采用位置方式或者关键字方式。

使用函数后，有可能遇到实参不匹配错误。提供的实参多于或者少于函数完成工作所需的信息时，将出现实参不匹配错误。

#### 3.返回值

函数并非总是直接显示输出，它还可以处理一些数据，并返回一个或一组值。函数返回的值称为返回值。在函数中，可使用return语句将值返回到调用函数的代码行。返回值让你能够将程序的大部分繁重的工作移到函数中去完成，从而简洁主程序。

示例：

接受名和姓并返回整洁的姓名

```python
def get_formatted_name(first_name,last_name):
    """返回整洁的姓名。"""
    full_name = f"{first_name} {last_name}"
    return full_name.title()
musician = get_formatted_name('jimi', 'hendrix')
print(musician)

#运行结果：Jimi Hendrix
```



让实参变成可选的

有时候，需要让实参变成可选的，这样使用函数的人就能只在必要时提供额外信息。可使用默认值来让实参变成可选的。

示例：

```python
def get_formatted_name(first_name,last_name,middle_name = ''):
    """返回整洁的姓名。"""
    if middle_name:
        full_name = f"{first_name} {middle_name} {last_name}"
    else:
        full_name = f"{first_name} {last_name}"
    return full_name.title()

musician = get_formatted_name('jimi', 'hendrix')
print(musician)

musician = get_formatted_name('john','hooker','lee')
print(musician)

#运行结果：
#Jimi Hendrix
#John Lee Hooker
```

可选值让函数能够处理各种不同的情形，同时确保函数调用尽可能简单。

##### 3.1  返回字典

函数可返回任何类型的值，包括列表和字典等较复杂的数据结构。

示例：

```python
def build_person(first_name,last_name):
    """返回一个字典，其中包含有关一个人的信息。"""
    person = {'first':first_name,'last':last_name}
    return person

musician = build_person('jimi','hendrix')
print(musician)

#运行结果：{'first': 'jimi', 'last': 'hendrix'}
```

这个函数接受简单的文本信息，并将其放在一个更合适的数据结构中，让你不仅能打印这些信息，还能以其他方式处理它们。还可以拓展这个函数，使其接受可选值，如中间名、年龄、职业等其他任何要存储的信息。

##### 3.2  结合使用函数和while循环

可将函数同前面的任何python结构结合起来使用。

```python
def get_formatted_name(first_name,last_name):
    """返回整洁的姓名。"""
    full_name = f"{first_name} {last_name}"
    return full_name.title()

while True:
    print("\nPlease tell me your name:")
    print("(enter 'q' at any time to quit)")
    
    f_name = input("First name: ")
    if f_name == 'q':
        break
    
    l_name = input("Last name: ")
    if l_name == 'q':
        break
    
    formatted_name = get_formatted_name(f_name, l_name)
    print(f"\nHello,{formatted_name}")
    
#运行结果：
#Please tell me your name:
#(enter 'q' at any time to quit)
#First name: eric
#Last name: matthes
#
#Hello,Eric Matthes
#
#Please tell me your name:
#(enter 'q' at any time to quit)
#First name: q
```



##### 3.3  传递列表

将列表传递给函数后，函数可以直接访问其内容。

```python
def greet_users(names):
    """向列表中的每位用户发出简单的问候。"""
    for name in names:
        msg = f"Hello,{name.title()}!"
        print(msg)
        
usernames = ['hannah','ty','margot']
greet_users(usernames)

#运行结果：
#Hello,Hannah!
#Hello,Ty!
#Hello,Margot!
```

###### 3.3.1  在函数中修改列表

将列表传递给函数后，函数就可对其进行修改。在函数中对这个列表所做的任何修改都是永久性的，这让你能够高效地处理大量数据。

示例：

```python
def print_models(unprinted_designs,completed_models):
    """
    模拟打印每个设计，直到没有未打印的设计为止。
    打印每个设计后，都将其移到列表completed_models中。
    """
    while unprinted_designs:
        current_design = unprinted_designs.pop()
        print(f"Printing model:{current_design}")
        completed_models.append(current_design)
        
def show_completed_models(completed_models):
    """显示打印好的所有模型。"""
    print("\nThe following models have been printed:")
    for completed_model in completed_models:
        print(completed_model)
        
unprinted_designs = ['phone case','robot pendant','dodecahedron']
completed_models = []

print_models(unprinted_designs, completed_models)
show_completed_models(completed_models)

#运行结果：
#Printing model:dodecahedron
#Printing model:robot pendant
#Printing model:phone case
#
#The following models have been printed:
#dodecahedron
#robot pendant
#phone case
```

###### 3.3.2  禁止函数修改列表

有时候需要禁止函数修改列表。

可向函数传递列表的副本而非原件，这样函数的修改都只影响副本，而原件丝毫不受影响。

要将列表的副本传递给函数可以这样做：

```python
function_name(list_name[:])
```

切片表示法[:]创建列表的副本。

虽然像函数传递列表的副本可以保留原始列表的内容，但除非有充分的理由，否则还是应该将原始列表传递给函数。这是因为让函数使用现成的列表可避免花时间和内存创建副本，从而提高效率，在处理大型列表时尤其如此。

##### 3.4  传递任意数量的实参

有时候，预先不知道函数需要接受多少个实参，好在Python允许函数从调用语句中收集任意数量的实参。

示例：

```python
def make_pizza(*toppings):
    """打印顾客点的所有配料。"""
    print(toppings)
    
make_pizza('pepperoni')
make_pizza('mushrooms','green peppers','extra cheese')

#运行结果：
#('pepperoni',)
#('mushrooms', 'green peppers', 'extra cheese')
```

形参名*toppings中的星号让Python创建一个名为toppings的空元组，并将收到的所有值都封装到这个元组中。



###### 3.4.1  结合使用位置实参和任意数量实参

如果要让函数接受不同类型的实参，必须在函数定义中将接纳任意数量实参的形参放在最后。Python先匹配位置实参和关键字实参，再将余下的实参都搜集到最后一个形参中。

**注意：**  你会经常看到通用形参名*args，它也收集任意数量的位置实参。

###### 3.4.2  使用任意数量的关键字实参

有时候，需要接受任意数量的实参，但预先不知道传递给函数的会是什么样的信息。在这种情况下，可将函数编写成能够接受任意数量的键值对——调用语句提供多少就接受多少。

示例：

```python
def build_profile(first,last,**user_info):
    """创建一个字典，其中包含我们知道的有关用户的一切。"""
    user_info['first_name'] = first
    user_info['last_name'] = last
    return user_info

user_profile = build_profile('albert','einstein',
                             location = 'princeton',
                             filed = 'physcs')
print(user_profile)

#运行结果：
#{'location': 'princeton', 'filed': 'physcs', 'first_name': 'albert', 'last_name': #'einstein'}
```

函数build_profile()的定义要求提供名和姓，同时允许根据提供需要提供任意数量的名称值对。形参**user_info中的两个星号让python创建一个名为user_info的空字典，并将收到的所有名称值对都放到这个字典中。在这个函数中可以像访问其他字典那样访问user_info中的名称值对。函数内将名和姓加入字典中，然后返回字典。

**注意：** 你经常看到形参名**kwargs,它用于收集任意数量的关键字实参。



#### 4.将函数存储在模块中

使用函数的优点之一是可以将代码块与主程序分离。通过给函数指定描述性名称，可以让主程序容易理解的多。还可以更进一步，将函数存储在成为**模块**的独立文件中，再将模块导入到主程序中。import语句允许在当前运行的程序文件中使用模块中的代码。

通过将函数存储在独立的文件中，可隐藏程序代码的细节，将重点放在程序的高层逻辑上，这还能让你在众多不同的程序中重用函数。将函数存储在独立文件中后，可与其他程序员共享这些文件而不是整个程序。知道如何导入函数还能让你使用其他程序员编写的函数库。

导入模块的方法有很多种，以下一一进行简要介绍。

##### 4.1导入整个模块

要让函数是可导入的，得先创建模块。模块是拓展名为.py的文件，包含要导入到程序中的代码。

下面创建一个包含函数make_pizza()的模块。为此，将文件pizza.py中除函数make_pizza()之外的其他代码删除。

接下来，在pizza.py所在目录中创建一个名为making_pizzas.py的文件，这个文件导入刚创建的模块，再调用make_pizza()两次。

要调用被导入模块中的函数，可指定被导入模块的名称pizza和函数名make_pizza()，并用句点分隔。

示例：

pizza.py

```python
def make_pizza(size,*toppings):
    """概述要制作的披萨。"""
    print(f"\nMaking a {size}-inch pizza with the following toppings:")
    for topping in toppings:
        print(f"-{topping}")
```

```python
#making_pizzas.py
import pizza

pizza.make_pizza(16,'pepperoni')
pizza.make_pizza(12,'mushrooms','green peppers','extra cheese')

#运行结果：
#Making a 16-inch pizza with the following toppings:
#-pepperoni

#Making a 12-inch pizza with the following toppings:
#-mushrooms
#-green peppers
#-extra cheese
```



#####  4.2导入特定的函数

还可以导入模块中的特定函数，导入方法的语法如下：

> from module_name import function_name

通过用逗号分隔函数名，可根据需要从模块中导入任意数量的函数：

> from module_name import function_0, function_1, function_2

使用这种语法时，调用函数时无需使用句点。由于import语句显式地导入了函数make_pizza()，调用时只需指定其名称即可。

示例：

```python
from pizza import make_pizza

make_pizza(16,'pepperoni')
make_pizza(12,'mushrooms','green peppers','extra cheese')

#运行结果：
#Making a 16-inch pizza with the following toppings:
#-pepperoni
#
#Making a 12-inch pizza with the following toppings:
#-mushrooms
#-green peppers
#-extra cheese
```



##### 4.3使用as给函数指定别名

如果要导入函数的名称可能与程序中现有的名称冲突，或者函数的名称太长，可指定简短而独一无二的别名：函数的另一个名称，类似于外号。要给函数取这种特殊外号，需要在导入它时指定。

通用语法：

> from module_name import function_name as fn

示例：

```python
from pizza import make_pizza as mp

mp(16,'pepperoni')
mp(12,'mushrooms','green peppers','extra cheese')

#运行结果：
#Making a 16-inch pizza with the following toppings:
#-pepperoni
#
#Making a 12-inch pizza with the following toppings:
#-mushrooms
#-green peppers
#-extra cheese
```

##### 4.4使用as给函数指定别名

还可以给模块指定别名。通过给模块指定简短的别名（如模块pizza指定别名为p），让你能够更加轻松地调用模块中的函数。相比于pizza.make_pizza()，p.make_pizza()更为简洁。可以让你不用再关注模块名，只专注于描述性的函数名。这些函数名明确指出了哈函数的功能，对于理解代码而言，比模块名更重要。

给模块指定别名的通用语法：

> import mudule_name as mn

##### 4.5导入模块中的所有函数

使用星号*运算符可让Python导入模块中的所有函数：

> from module_name import *

import语句中的星号*让python将模块piazza中的每个函数都复制到这个程序文件中。由于导入了每个函数，可通过名称来调用每个函数，而无需使用句点表示法。然而，使用并非自己编写的大型模块时，最好不要采用这种导入方法。因为如果模块中有函数的名称与当前项目中使用的名称相同，可能导致意想不到的结果：Python可能遇到多个名称相同的函数或变量，进而覆盖函数，而不是分别导入所有的函数。

最佳的做法就是，要么只导入需要使用的函数，要么导入整个模块并使用句点表示法。这让代码更清晰，更容易阅读和理解。

#### 5.函数编写指南

编写函数时需要牢记几个细节。

1. 应给函数指定描述性名称，且只在其中使用小写字母和下划线。描述性名称可帮助你和别人明白代码想要做什么，给模块命名时也遵循上述约定。
2. 每个函数都应包含简要地阐述其功能的注释。该注释紧跟在函数定义后面，并采用文档字符串格式。
3. 给形参指定默认值时，等号两边不要有空格，对于函数调用中的关键字实参，也应遵循这种规定。
4. 如果形参很多，导致函数定义的长度过长，可在函数定义中输入左括号后按回车键，并在下一行按两次Tab键，从而将形参列表和只缩进一层的函数体区分开来。
5. 如果程序或模块包含多个函数，可使用两个空行将相邻的函数分开。
6. 所有import语句都应放在文件的开头。唯一例外的情形是，在文件开头使用了注释来描述整个程序。

### 第8章  类

**面向对象编程**是最有效的软件编写方法之一。在面向对象编程中，你编写表示现实世界中的事物和情景的类，并基于这些类来创建对象。编写类时，你定义一大类对象都有的通用行为。基于类创建对象时，每个对象都自动具备这种通用行为，然后可根据需要赋予每个对象独特的个性。根据类来创建对象称为**实例化**，这让你能够使用类的实例。

#### 1.创建和使用类

使用类几乎可以模仿任何东西，下面来编写一个表示小狗的简单类Dog，它表示的不是特定的小狗，而是任何小狗。对于大多数小狗，它们都有名字和年龄，蹲下和打滚。我们的Dog类将包含它们。这个类让Python知道如何创建表示小狗的对象。编写这个类后，我们将使用它来创建表示特定小狗的实例。

##### 1.1  创建Dog类

示例：

```python
class Dog:
    """一次模拟小狗的简单尝试。"""
    
    def _init_(self, name, age):
        """初始化属性name和age。"""
        self.name = name
        self.age = age
        
    def sit(self):
        """模拟小狗收到命令时蹲下。"""
        print(f"{self.name} is now sitting.")
        
    def roll_over(self):
        """模拟小狗收到命令时打滚。"""
        print(f"{self.name} rolled over")
```

> 第一行首先定义了一个Dog类，根据约定，在python中首字母大写的名称指的就是类。这个类定义中没有圆括号，因为要从空白创建这个类。
>
> 第二行编写了一个文档字符串，对这个类的功能做了描述。
>
> 方法__ init _（），类中的函数称为方法。前面学到的有关函数的一切都适用于方法，目前来说，唯一的区别就是调用方法的方式。
>
> 第三行的方法__ init _（）是一个特殊的方法，每当我们根据Dog类创建新实例时，Python都会自动运行它。在这个方法的名称中，开头和结尾各有两个下划线，这是一种约定，旨在避免python默认方法与普通方法发生名称冲突，务必确保__ init _（）的两边都有两个下划线，否则当你使用类来创建实例时，将不会自动调用这个方法，进而引发难以发现的错误。
>
> 我们将方法__ init _（）定义成包含三个形参：self,name和age。在这个方法的定义中，形参self必不可少，而且必须位于其他形参的前面。
>
> 为何必须在方法定义中包含形参self呢？因为python调用这个方法；来创建Dog实例时，将自动传入实参self。每个与实例相关联的方法调用都自动传递实参self，它是一个指向实例本身的引用，让实例能够访问类中的属性和方法。创建Dog实例时，python将调用Dog类的方法__ init _（）。我们将通过实参向Dog()传递名字和年龄，self会自动传递，因此不需要传递它。每当根据Dog类创建实例时，都只需给最后两个形参（name和age）提供值。
>
> 第六行定义的两个变量都有前缀self。以self为前缀的变量可供类中的所有方法使用，可以通过类的任何实例来访问。self.name = name 获取与形参name相关联的值，并将其赋给变量name，然后该变量被关联到当前创建的实例。self.age = age 的作用与此类似。像这样可通过实例访问的变量称为属性。
>
> Dog类还定义了另外两个方法：sit()和roll_over()。这些方法执行时不需要额外的信息，因此它们只有一个形参self。我们随后创建的实例能够访问这些方法，换句话说，它们都会蹲下和打滚。当前，sit()和roll_over()所做的有限，只是打印一条消息，指出小狗正在蹲下或打滚。但也可以拓展这些方法以模拟实际情况：如果这个类包含在一个计算机游戏中，这些方法将包含创建小狗蹲下和打滚动画效果的代码；如果这个类是用于控制机器狗的，这些方法将让机器狗做出蹲下和打滚的动作。
