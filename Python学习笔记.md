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
        print(f"{self.name} rolled over.")
```

> 第一行首先定义了一个Dog类，根据约定，在python中首字母大写的名称指的就是类。这个类定义中没有圆括号，因为要从空白创建这个类。
>
> 第二行编写了一个文档字符串，对这个类的功能做了描述。
>
> 方法__ init __（），类中的函数称为方法。前面学到的有关函数的一切都适用于方法，目前来说，唯一的区别就是调用方法的方式。
>
> 第三行的方法__ init __ （ ）是一个特殊的方法，每当我们根据Dog类创建新实例时，Python都会自动运行它。在这个方法的名称中，开头和结尾**==各有两个下划线==**，这是一种约定，旨在避免python默认方法与普通方法发生名称冲突，务必确保 __ init __ （）的两边都有两个下划线，否则当你使用类来创建实例时，将不会自动调用这个方法，进而引发难以发现的错误。
>
> 我们将方法__ init __（）定义成包含三个形参：self,name和age。在这个方法的定义中，形参self必不可少，而且必须位于其他形参的前面。
>
> 为何必须在方法定义中包含形参self呢？因为python调用这个方法；来创建Dog实例时，将自动传入实参self。每个与实例相关联的方法调用都自动传递实参self，它是一个指向实例本身的引用，让实例能够访问类中的属性和方法。创建Dog实例时，python将调用Dog类的方法__ init _（）。我们将通过实参向Dog()传递名字和年龄，self会自动传递，因此不需要传递它。每当根据Dog类创建实例时，都只需给最后两个形参（name和age）提供值。
>
> 第六行定义的两个变量都有前缀self。以self为前缀的变量可供类中的所有方法使用，可以通过类的任何实例来访问。self.name = name 获取与形参name相关联的值，并将其赋给变量name，然后该变量被关联到当前创建的实例。self.age = age 的作用与此类似。像这样可通过实例访问的变量称为属性。
>
> Dog类还定义了另外两个方法：sit()和roll_over()。这些方法执行时不需要额外的信息，因此它们只有一个形参self。我们随后创建的实例能够访问这些方法，换句话说，它们都会蹲下和打滚。当前，sit()和roll_over()所做的有限，只是打印一条消息，指出小狗正在蹲下或打滚。但也可以拓展这些方法以模拟实际情况：如果这个类包含在一个计算机游戏中，这些方法将包含创建小狗蹲下和打滚动画效果的代码；如果这个类是用于控制机器狗的，这些方法将让机器狗做出蹲下和打滚的动作。

##### 1.2根据类创建实例

可将类视为有关如何创建实例的说明。Dog类是一系列说明，让python知道如何创建表示特定小狗的实例。

实例：

```python
class Dog:
    """一次模拟小狗的简单尝试。"""
    
    def __init__(self, name, age):
        """初始化属性name和age。"""
        self.name = name
        self.age = age
        
    def sit(self):
        """模拟小狗收到命令时蹲下。"""
        print(f"{self.name} is now sitting.")
        
    def roll_over(self):
        """模拟小狗收到命令时打滚。"""
        print(f"{self.name} rolled over.")
        

my_dog = Dog('Willie',6)

print(f"My dog's name is {my_dog.name}.")
print(f"My dog is {my_dog.age} years old.")  

#运行结果：
#My dog's name is Willie.
#My dog is 6 years old.
```

这里python创建了一条名为Willie，6岁的小狗。Python使用实参‘Willie’和6调用Dog类的方法   __ init __ （），创建了一个表示特定小狗的实例。并根据提供的值来设置属性name和age。接下来python返回了一个表示这条小狗的实例，而我们将这个实例赋给了变量my_dog。

在这里命名的约定很有用：通常认为首字母为大写的名称指的是类，而小写的名称指的是根据类创建的实例。

###### 1.2.1  访问属性

要访问实例的属性，可使用句点表示法。

> my_dog.name

如上来访问my_dog的属性name的值

句点表示法在python中很常用，这种语法演示了python如何获悉属性的值。在这里python先找到实例my_dog，再查找与该实例相关联的属性name。在Dog类中引用这个属性的时候，使用的是self.name。使用同样的方法来获取属性age的值。

###### 1.2.2  调用方法

根据Dog类创建实例后，就能使用句点表示法来调用Dog类中定义的任何方法了。

实例：让小狗下蹲和打滚。

```python
class Dog:
    """一次模拟小狗的简单尝试。"""
    
    def __init__(self, name, age):
        """初始化属性name和age。"""
        self.name = name
        self.age = age
        
    def sit(self):
        """模拟小狗收到命令时蹲下。"""
        print(f"{self.name} is now sitting.")
        
    def roll_over(self):
        """模拟小狗收到命令时打滚。"""
        print(f"{self.name} rolled over.")
        

my_dog = Dog('Willie',6)

my_dog.sit()
my_dog.roll_over()      

#运行结果：
Willie is now sitting.
Willie rolled over.
```

要调用方法，可指定实例的名称（这里是my_dog）和要调用的方法，并用句点分隔。遇到my_dog.sit()时，python在类Dog中查找方法sit（）并运行其代码。

如果属性和方法指定了合适的描述性名称，即便没见过的代码块，我们也能轻松地推断出它是做什么的。

###### 1.2.3  创建多个实例

可根据需求创建多个实例。

```python
class Dog:
    """一次模拟小狗的简单尝试。"""
    
    def __init__(self, name, age):
        """初始化属性name和age。"""
        self.name = name
        self.age = age
        
    def sit(self):
        """模拟小狗收到命令时蹲下。"""
        print(f"{self.name} is now sitting.")
        
    def roll_over(self):
        """模拟小狗收到命令时打滚。"""
        print(f"{self.name} rolled over")
        

my_dog = Dog('Willie',6)
your_dog = Dog('Lucy',3)

print(f"My dog's name is {my_dog.name}.")
print(f"My dog is {my_dog.age} years old.")
my_dog.sit()

print(f"\nYour dog's name is {your_dog.name}.")
print(f"Your dog is {your_dog.age} years old.")
your_dog.sit()

#运行结果：
#My dog's name is Willie.
#My dog is 6 years old.
#Willie is now sitting.
#
#Your dog's name is Lucy.
#Your dog is 3 years old.
#Lucy is now sitting.
```

这里我们创建了两条小狗，分别名为Willie和Lucy。每条小狗都是一个独立的实例，有自己的一组属性，能够执行相同的操作。

即使给第二条小狗指定同样的名字和年龄，python依然会根据Dog类创建另一个实例。你可按需求根据一个类创建任意数量的实例，条件是将每个实例都存储在不同的变量中，或者占用列表或字典的不同位置。

#### 2.使用类和实例

可使用类来模拟现实世界中的很多情景。类编写好后，你的大部分时间将花在根据类创建的实例上。你需要执行的一个重要任务是修改实例的属性。可以直接修改实例的属性，也可以编写方法以特定的方式进行修改。

##### 2.1Car类

```python
class Car:
    """一次模拟汽车的简单尝试。"""
    
    def __init__(self,make,model,year):
        """初始化描述汽车的属性。"""
        self.make = make
        self.model = model
        self.year = year
        
    def get_descriptive_name(self):
        """返回整洁的描述性信息。"""
        long_name = f"{self.year} {self.make} {self.model}"
        return long_name.title()
    
my_new_car = Car('audi','a4','2019')
print(my_new_car.get_descriptive_name())

#运行结果：2019 Audi A4
```

##### 2.2给属性指定默认值

创建实例时，有些属性无需通过形参来定义，可在方法 ____ init ____ () 中为其指定默认值。

示例：

```python
class Car:
    """一次模拟汽车的简单尝试。"""
    
    def __init__(self,make,model,year):
        """初始化描述汽车的属性。"""
        self.make = make
        self.model = model
        self.year = year
        self.odometer_reading = 0
        
    def get_descriptive_name(self):
        """返回整洁的描述性信息。"""
        long_name = f"{self.year} {self.make} {self.model}"
        return long_name.title()
    
    def read_odometer(self):
        """打印一条指出汽车里程的消息。"""
        print(f"This car has {self.odometer_reading} miles on it.")
    
my_new_car = Car('audi','a4','2019')
print(my_new_car.get_descriptive_name())
my_new_car.read_odometer()

#运行结果：
#2019 Audi A4
#This car has 0 miles on it.
```

##### 2.3修改属性的值

我们能以三种方式修改属性的值：直接通过实例进行修改，通过方法进行设置，以及通过方法进行递增（增加特定的值）。

###### 2.3.1  直接修改属性的值

要修改属性的值，最简单的方式是通过实例来直接访问它。

```python
class Car:
    """一次模拟汽车的简单尝试。"""
    
    def __init__(self,make,model,year):
        """初始化描述汽车的属性。"""
        self.make = make
        self.model = model
        self.year = year
        self.odometer_reading = 0
        
    def get_descriptive_name(self):
        """返回整洁的描述性信息。"""
        long_name = f"{self.year} {self.make} {self.model}"
        return long_name.title()
    
    def read_odometer(self):
        """打印一条指出汽车里程的消息。"""
        print(f"This car has {self.odometer_reading} miles on it.")
    
my_new_car = Car('audi','a4','2019')
print(my_new_car.get_descriptive_name())

my_new_car.odometer_reading = 23
my_new_car.read_odometer()

#运行结果：
#2019 Audi A4
#This car has 23 miles on it.
```

使用句点表示法直接访问并设置汽车的属性odometer_reading。这行代码让Python在实例my_new_car中找到属性odometer_reading，并将其值设置为23。有时候需要像这样直接访问属性，但其他时候需要编写对属性进行更新的方法。

###### 2.3.2  通过方法修改属性的值

如果有方法能替我们更新属性，将大有裨益。这样无需直接访问属性，而可将值传递给方法，由它在内部进行更新。

示例：

```python
class Car:
    """一次模拟汽车的简单尝试。"""
    
    def __init__(self,make,model,year):
        """初始化描述汽车的属性。"""
        self.make = make
        self.model = model
        self.year = year
        self.odometer_reading = 0
        
    def get_descriptive_name(self):
        """返回整洁的描述性信息。"""
        long_name = f"{self.year} {self.make} {self.model}"
        return long_name.title()
    
    def read_odometer(self):
        """打印一条指出汽车里程的消息。"""
        print(f"This car has {self.odometer_reading} miles on it.")
        
    def update_odometer(self,mileage):
        """
        将里程表读数设置为指定的值。
        禁止将里程表往回调。
        """
        if mileage >= self.odometer_reading:
            self.odometer_reading = mileage
        else:
            print("You can't roll back an odometer!")
    
my_new_car = Car('audi','a4','2019')
print(my_new_car.get_descriptive_name())

my_new_car.update_odometer(23)
my_new_car.read_odometer()

#运行结果：
#2019 Audi A4
#This car has 23 miles on it.
```

###### 2.3.3  通过方法对属性的值进行递增

有时候需要将属性值递增特定的量，而不是将其设置全新的值。

实例：

```python
class Car:
    """一次模拟汽车的简单尝试。"""
    
    def __init__(self,make,model,year):
        """初始化描述汽车的属性。"""
        self.make = make
        self.model = model
        self.year = year
        self.odometer_reading = 0
        
        
    def get_descriptive_name(self):
        """返回整洁的描述性信息。"""
        long_name = f"{self.year} {self.make} {self.model}"
        return long_name.title()
    
    
    def read_odometer(self):
        """打印一条指出汽车里程的消息。"""
        print(f"This car has {self.odometer_reading} miles on it.")
        
        
    def update_odometer(self,mileage):
        """
        将里程表读数设置为指定的值。
        禁止将里程表往回调。
        """
        if mileage >= self.odometer_reading:
            self.odometer_reading = mileage
        else:
            print("You can't roll back an odometer!")


    def increment_odometer(self,miles):
        """将里程表读数增加特定的量。"""
        self.odometer_reading += miles
        
        
my_used_car = Car('subaru','outback','2015')
print(my_used_car.get_descriptive_name())

my_used_car.update_odometer(23_500)
my_used_car.read_odometer()

my_used_car.increment_odometer(100)
my_used_car.read_odometer()

#运行结果：
#2015 Subaru Outback
#This car has 23500 miles on it.
#This car has 23600 miles on it.
```

还可修改这个方法，禁止增量为负值，从而防止有人利用它来回调里程表。



**注意：** 你可以使用类似的方法来控制用户修改属性值的方式，但能够访问程序的人都可以通过直接访问属性来将里程表修改为任何值 。要确保安全,除了进行类似于前面的基本检查外,还需特别注意细节。

#### 3.继承

编写类时，并非总是从空白开始。如果要编写的类是另一个现成类的特殊版本，可使用继承。一个类继承另一个类时，将自动获得另一个类的所有属性和方法。原有的类称为父类，而新类称为子类。子类继承了父亲的所有属性和方法，同时还可以定义自己的属性和方法。

##### 3.1  子类的方法 __ init__（）

在既有类的基础上编写新类时，通常需要调用父类的方法__ init__ （）。这将初始化在父类__ init__（）方法中定义的所有属性，从而让子类包含这些属性。

示例：

```python
class Car:
    """一次模拟汽车的简单尝试。"""
    
    def __init__(self,make,model,year):
        """初始化描述汽车的属性。"""
        self.make = make
        self.model = model
        self.year = year
        self.odometer_reading = 0
        
        
    def get_descriptive_name(self):
        """返回整洁的描述性信息。"""
        long_name = f"{self.year} {self.make} {self.model}"
        return long_name.title()
    
    
    def read_odometer(self):
        """打印一条指出汽车里程的消息。"""
        print(f"This car has {self.odometer_reading} miles on it.")
        
        
    def update_odometer(self,mileage):
        """
        将里程表读数设置为指定的值。
        禁止将里程表往回调。
        """
        if mileage >= self.odometer_reading:
            self.odometer_reading = mileage
        else:
            print("You can't roll back an odometer!")


    def increment_odometer(self,miles):
        """将里程表读数增加特定的量。"""
        self.odometer_reading += miles
        
    
class ElectricCar(Car):
    """电动汽车的独特之处。"""
    
    def __init__(self,make,model,year):
        """初始化父类的属性。"""
        super().__init__(make,model,year)
        

my_tesla = ElectricCar('tesla', 'model s', 2019)
print(my_tesla.get_descriptive_name())

#运行结果：2019 Tesla Model S
```

首先是父类的代码。创建子类时，父类必须包含在当前文件中，且位于子类前面。接着定义了子类ElectricCar。定义子类时，必须在圆括号内指定父类的名称。第42行接受创建Car实例所需的信息。super（）是一个特殊函数，让你能够调用父类的方法。第44行，让python调用Car类的方法—init—（），让ElectricCar实例包含这个方法中定义的所有属性。父类也称为超类（superclass），名称由此而来。

第47行，代码调用ElectricCar类中定义的方法 —init—（），后者让python调用父类Car中定义的方法，我们提供'tesla'、‘model s'和2019。

##### 3.2  给子类定义属性和方法

让一个类继承另一个类后，就可以添加区分子类和父类所需的新属性和新方法了。

下面添加一个电动汽车特有的属性（电瓶），以及一个描述该属性的方法。

```python
class Car:
    """一次模拟汽车的简单尝试。"""
    
    def __init__(self,make,model,year):
        """初始化描述汽车的属性。"""
        self.make = make
        self.model = model
        self.year = year
        self.odometer_reading = 0
        
        
    def get_descriptive_name(self):
        """返回整洁的描述性信息。"""
        long_name = f"{self.year} {self.make} {self.model}"
        return long_name.title()
    
    
    def read_odometer(self):
        """打印一条指出汽车里程的消息。"""
        print(f"This car has {self.odometer_reading} miles on it.")
        
        
    def update_odometer(self,mileage):
        """
        将里程表读数设置为指定的值。
        禁止将里程表往回调。
        """
        if mileage >= self.odometer_reading:
            self.odometer_reading = mileage
        else:
            print("You can't roll back an odometer!")


    def increment_odometer(self,miles):
        """将里程表读数增加特定的量。"""
        self.odometer_reading += miles
        
    
class ElectricCar(Car):
    """电动汽车的独特之处。"""
    
    def __init__(self,make,model,year):
        """
        初始化父亲的属性。
        再初始化电动汽车特有的属性。
        """
        super().__init__(make,model,year)
        self.battery_size = 75
        
    def describe_battery(self):
        """打印一条描述电瓶容量的消息。"""
        print(f"This car has a {self.battery_size}-kwh battery.")
        

my_tesla = ElectricCar('tesla', 'model s', 2019)
print(my_tesla.get_descriptive_name())
my_tesla.describe_battery()

```

第47行，添加了新属性self.battery_size，并设置其初始值（75）.根据ElectricCar创建的所有实例都将包含该属性，但所有Car实例都不包含它。第50行还添加了一个名为describe_battery(self)的方法，打印有关电瓶的信息。

对于ElectricCar类的特殊程度没有任何限制。模拟电动汽车时，可根据所需的准确程度添加任意数量的属性和方法。如果一个属性或方法是任何汽车都有的，而不是电动汽车特有的，就应将其加入到Car类，这样使用Car类的人将获得相应的功能，而ElectricCar类只包含处理电动汽车特有的属性和行为的代码。

##### 3.3  重写父类的方法

对于父类的方法，只要它不符合子类模拟的实物的行为，都可以进行重写。为此可在子类中定义一个与要重写的父类方法同名的方法。这样Python将不会考虑这个父类方法，而只关注你在子类中定义的相应方法。

重写后，在调用方法，python将忽略父类中的方法，使用继承可让子类保留从父类那里继承而来的精华，并剔除不需要的糟粕。

##### 3.4  将实例用作属性

使用代码模拟实物时，你可能发现自己给类添加的细节越来越多：属性和方法清单以及文件都越来越长。在这种情况下，可能需要将类的一部分提取出来作为一个独立的类。可以将大型类拆分成多个协同工作的小类。

示例：

```python
class Car:
    """一次模拟汽车的简单尝试。"""
    
    def __init__(self,make,model,year):
        """初始化描述汽车的属性。"""
        self.make = make
        self.model = model
        self.year = year
        self.odometer_reading = 0
        
        
    def get_descriptive_name(self):
        """返回整洁的描述性信息。"""
        long_name = f"{self.year} {self.make} {self.model}"
        return long_name.title()
    
    
    def read_odometer(self):
        """打印一条指出汽车里程的消息。"""
        print(f"This car has {self.odometer_reading} miles on it.")
        
        
    def update_odometer(self,mileage):
        """
        将里程表读数设置为指定的值。
        禁止将里程表往回调。
        """
        if mileage >= self.odometer_reading:
            self.odometer_reading = mileage
        else:
            print("You can't roll back an odometer!")


    def increment_odometer(self,miles):
        """将里程表读数增加特定的量。"""
        self.odometer_reading += miles
        
class Battery:
    """一次模拟电动汽车电瓶的简单尝试。"""
    
    def __init__(self,battery_size = 75):
        """初始化电瓶的属性。"""
        self.battery_size = battery_size
        
        
    def describe_battery(self):
        """打印一条描述电瓶容量的消息。"""
        print(f"This car has a {self.battery_size}-kwh battery.")
        
        
        
class ElectricCar(Car):
    """电动汽车的独特之处。"""
    
    def __init__(self,make,model,year):
        """
        初始化父亲的属性。
        再初始化电动汽车特有的属性。
        """
        
        super().__init__(make,model,year)
        self.battery = Battery()
        
        

my_tesla = ElectricCar('tesla', 'model s', 2019)
print(my_tesla.get_descriptive_name())
my_tesla.battery.describe_battery()

#运行结果：
#2019 Tesla Model S
#This car has a 75-kwh battery.
```

这里定义了一个名为Battery新类，它没有继承任何类，第41行方法中除self外，还有另一个形参battery_size。这个形参是可选的：如果没有给他提供值，电瓶的容量将被设置为75。在ElectricCar类中，添加了一个名为self.battery的属性。这行代码让python创建了一个新的Battery实例，并将该实例赋给属性self.battery。每当方法。每次调用init方法时，都将执行此操作，由此每一个ElectricCar实例都包含一个自动创建的Battery实例。

> my_tesla.battery.describe_battery()

这行代码让python在实例my_tesla中查找属性battery，并对存储在该属性中的Battery实例调用方法describe_battery()

#### 4.导入类

##### 4.1  导入单个类

下面第一行是一个模块级文档字符串，对该模块的内容做了简要的描述。你应该为自己创建的每个模块编写文档字符串。

```python
"""一个用于表示汽车的类。"""


class Car:
    """一次模拟汽车的简单尝试。"""
    
    def __init__(self,make,model,year):
        """初始化描述汽车的属性。"""
        self.make = make
        self.model = model
        self.year = year
        self.odometer_reading = 0
      
        
    def get_descriptive_name(self):
        """返回整洁的描述性名称。"""
        long_name = f"{self.year} {self.make} {self.model}"
        return long_name.title()
    
    
    def read_odometer(self):
        """打印一条信息，指出汽车的里程。"""
        print(f"This car has {self.odometer_reading} miles on it.")
        
        
    def update_odometer(self,mileage):
        """
        将里程表读数设置为指定的值。
        拒绝将里程表往回调。
        """
        if mileage >= self.odometer_reading:
            self.odometer_reading = mileage
        else:
            print("You can't roll back an odometer!")
            
            
    def increment_odometer(self,miles):
        """将里程表读数增加指定的量。"""
        self.odometer_reading += miles
```

```python
from car import Car

my_new_car = Car('audi','a4',2019)
print(my_new_car.get_descriptive_name())

my_new_car.odometer_reading = 23
my_new_car.read_odometer()

#运行结果：
#2019 Audi A4
#This car has 23 miles on it.
```

import语句让python打开模块car并导入其中的Car类。这样我们就可以使用Car类，就像它是在这个文件中定义的一样。

导入类是一种有效的编程方式。如果这个程序包含整个Class类，会非常长。通过将这个类移到一个模块中并导入该模块，依然可以使用其所有功能，但主程序文件变得整洁而易于阅读了。这还让你能够将大部分逻辑存储在独立的文件中。确定类像你希望的那样工作后，就可以不管那些文件，而专注于主程序的高级逻辑。

##### 4.2  在一个模块存储多个类

虽然同一个模块中的类之间应存在某种相关性，但可根据需要在一个模块中存储任意数量的类。

示例：

```python
class Car:
    """一次模拟汽车的简单尝试。"""
    
    def __init__(self,make,model,year):
        """初始化描述汽车的属性。"""
        self.make = make
        self.model = model
        self.year = year
        self.odometer_reading = 0
      
        
    def get_descriptive_name(self):
        """返回整洁的描述性名称。"""
        long_name = f"{self.year} {self.make} {self.model}"
        return long_name.title()
    
    
    def read_odometer(self):
        """打印一条信息，指出汽车的里程。"""
        print(f"This car has {self.odometer_reading} miles on it.")
        
        
    def update_odometer(self,mileage):
        """
        将里程表读数设置为指定的值。
        拒绝将里程表往回调。
        """
        if mileage >= self.odometer_reading:
            self.odometer_reading = mileage
        else:
            print("You can't roll back an odometer!")
            
            
    def increment_odometer(self,miles):
        """将里程表读数增加指定的量。"""
        self.odometer_reading += miles
        
        
class Battery:
    """一次模拟电动汽车电瓶的简单尝试。"""
    
    def __init__(self,battery_size = 75):
        """初始化电瓶的属性。"""
        self.battery_size = battery_size
        
        
    def describe_battery(self):
        """打印一条描述电瓶容量的消息。"""
        print(f"This car has a {self.battery_size}-kwh battery.")
        
        
    def get_range(self):
        """打印一条描述电瓶续航里程的消息。"""
        if self.battery_size == 75:
            range = 260
        elif self.battery_size == 100:
            range = 315
            
        print(f"This car can go about {range} miles on a full charge.")
        
        
class ElectricCar(Car):
    """模拟电动汽车的独特之处。"""
    
    def __init__(self,make,model,year):
        """
        初始化父类的属性。
        在初始化电动汽车特有的属性。
        """
        super().__init__(make,model,year)
        self.battery = Battery()
```

```python
from car import ElectricCar

my_tesla = ElectricCar('tesla', 'model s', 2019)

print(my_tesla.get_descriptive_name())
my_tesla.battery.describe_battery()
my_tesla.battery.get_range()

#运行结果：
#2019 Tesla Model S
#This car has a 75-kwh battery.
#This car can go about 260 miles on a full charge.
```

输出与之前的相同，但大部分逻辑隐藏在一个模板中

##### 4.3  从一个模块中导入多个类

可根据需要在程序中导入任意数量的类。

例如：如果要在同一个程序中创建普通汽车和电动汽车，就需要将Car类和ElectricCar类都导入：

```python
from car import Car,ElectricCar

my_beetle = Car('volkswagen', 'beetle', 2019)
print(my_beetle.get_descriptive_name())

my_tesla = ElectricCar('tesla', 'roadster', 2019)
print(my_tesla.get_descriptive_name())

#运行结果：
#2019 Volkswagen Beetle
#2019 Tesla Roadster
```

在第一行从一个模块导入多个类时，用逗号分隔了各个类。导入必要的类后，就可根据需要创建每个类的任意数量实例。

##### 4.4  导入整个模块

还可以导入整个模块，再使用句点表示法访问需要的类。这种导入方式很简单，代码也易于阅读。因为创建类实例的代码都包含模块名，所以不会与当前文件使用的任何名称发生冲突。

```python
import car

my_beetle = car.Car('volkswagen', 'beetle', 2019)
print(my_beetle.get_descriptive_name())

my_tesla = car.ElectricCar('tesla', 'roadster', 2019)
print(my_tesla.get_descriptive_name())

#运行结果：
#2019 Volkswagen Beetle
#2019 Tesla Roadster
```

导入了整个模块后，使用语法module_name.ClassName访问需要的类。

##### 4.5  导入模块中的所有类

要导入模块中的每个类，可使用下面的语法：

> from module_name import *

不推荐使用这种导入方式，第一，如果只看文件开头的import语句，就能清楚地知道程序使用了哪些类，将大有裨益。然而这种导入方式没有明确地指出使用了模块中的哪些类。第二，这种方式还可能引发名称方面的迷惑。如果不小心导入了一个与程序文件中的其他东西同名的类，将引发难以诊断的错误。

需要从一个模块导入很多类时，最好导入整个模块，并使用语法module_name.ClassName来访问类。这样做时，虽然文件开头并没有列出用到的所有类，但你清楚地知道在程序的哪些地方使用了导入的模块，这也避免导入模块中的每个类可能引发的名称冲突。

##### 4.6  在一个模块中导入另一个模块

有时候，需要将类分散到多个模块中，以免模块太大或在同一个模块中存储不相关的类。将类存储在多个模块中时，你可能发现一个模块中的类依赖于另一个模块中的类。在这种情况下可在前一个模块中导入必要的类。

```python
from car import Car
from electric_car import ElectricCar
```

ElectricCar类需要访问其父类Car，因此先将Car类导入该模块中。

##### 4.7  使用别名

使用模块来组织项目代码时，别名大有裨益。导入类时，也可为其指定别名。

示例：

```python
from electric_car import ElectricCar as EC
```

##### 4.8  自定义流程

一开始应让代码结构尽可能简单。先尽可能在一个文件中完成所有的工作，确定一切都能正常运行后，在将类移到独立的模块中。如果你喜欢模块和文件的交互方式，可在项目开始时就尝试将类存储到模块中。先找出让你能够编写出可行代码的方式，再尝试改进代码。

#### 5.python标准库

python标准库是一组模块，我们安装的python都包含它。可以使用标准库中的任何函数和类，只需在程序开头包含一条简单的import语句即可。下面看看模块random,它在你模拟很多现实情况时很有用。

函数randint()，它将两个整数作为参数，并随机返回一个位于这两个整数之间（含）的整数。

```python
from random import randint
num = randint(1,6)
print(num)

#运行结果：

```

![](../Pictures/Screenshots/屏幕截图 2023-08-01 143818.png)

函数choice()，它将一个列表或元组作为参数，并随机返回其中的一个元素：

```python
from random import choice
players =['charles','martina','michael','florence','eli']

first_up =choice(players)
print(first_up)
```

创建与安全相关的应用程序时，不要使用模块random，但该模块可以很好地用于创建众多有趣的项目。

**注意：** 还可以从其他地方下载外部模块。

#### 6.类编码风格

类名应采用驼峰命名法，即将类名中的每个单词的首字母都大写，而不使用下划线。实例名和模块名都采用小写，并在单词间加上下划线。

对于每个类，都应紧跟在类定义后面包含一个文档字符串。这种字符串简要地描述类的功能，并遵循编写函数地文档字符串时采用的格式约定。每个模块也应都包含一个文档字符串，对其中的类可用于做什么进行描述。

可使用空行来组织代码，但不要滥用。在类中，可使用一个空行来分隔方法；而在模块中，可使用两个空行来分隔类。

需要同时导入标准库中的模块和你编写的模块时，先导入标准库模块的import语句，再添加一个空行，然后编写导入你自己编写的模块的import语句。在包含多条import语句的程序中，这种做法让人更容易明白程序使用的各个模块都来自何处。

### 第9章  文件和异常

#### 1.从文件中读取数据

要使用文本文件中的信息，首先需要将信息读取到内存中。为此，可以一次性读取文件全部内容，也可以以每次一行的方式逐步读取。

##### 1.1  读取整个文件

要读取文件，需要一个包含几行文本的文件。下面首先创建一个文件，它包含精确到小数点后30位的圆周率，且在小数点后每10位处换行：

如图所示：

![image-20230801160920578](../AppData/Roaming/Typora/typora-user-images/image-20230801160920578.png)

下面的程序打开并读取这个文件，再将其内容显示到屏幕上：

```python
with open('pi_digits.txt') as file_object:
    contents = file_object.read()
print(contents)

#运行结果：
#3.1415926535
#  8979323846
#  2643383279
#
```

要以任何方式使用文件，哪怕仅仅是打印其内容，都得先打开文件，才能访问它。函数open()接受一个参数：要打开的文件的名称。python在当前执行的文件所在的目录中查找指定文件。函数open（）返回一个表示文件的对象。在这里，open('pi_digits.txt')返回一个表示文件pi_digits.txt的对象，python将对象赋给file_object供以后使用。

关键字with在不再需要访问文件后将其关闭。在这个程序中，注意到我们调用了open（），但没有调用close（）。也可以调用open（）和close（）来打开和关闭文件，但这样做时，如果程序存在bug导致方法close（）未执行，文件将不会关闭。这看似微不足道，但未妥善关闭文件有可能导致数据丢失或受损。如果在程序中过早调用close（），你会发现需要使用文件时它已经关闭（无法访问），这会导致更多的错误。并非在任何情况下都能轻松确定关闭文件的恰当时机，但通过前面的结构，让python自己确定：你只管打开文件，并在需要时使用它，python自会在合适的时候自动将其关闭。

有了表示pi_digits.txt的文件对象后，使用方法read（）读取这个文件的全部内容，并将其作为一个个长长的字符串赋给变量contents。这样，通过打印contents的值，就可将这个文本文件的全部内容显示出来。

相比于原始文件，该输出唯一不同的地方就是末尾多了一个空行。因为read（)到达文件末尾时返回一个空字符串，而将这个空字符串显示出来时就是一个空行。要删除多出来的空行，可在函数调用print（）中使用rstrip（）

。方法rstrip（）删除字符串末尾的空白。

##### 1.2  文件路径

将类似于pi_digits.txt的简单文件名传递给函数open（）时，python将在当前执行的文件所在的目录中查找。

要让python打开不与程序文件位于同一个目录中的文件，需要提供文件路径，让python 去系统的特定位置查找。

例如，将程序文件存储在了文件夹python_work中，而该文件夹中有一个名为text_files的文件夹用于存储程序文件操作的文本文件。这个时候可以这样编码：

> with open('text_files/filename.txt') as file_object:

使用相对文件路径来打开其中的文件。该位置是相对于当前运行的程序所在目录的。

注意：显示文件路径时，windows系统使用反斜杠（\）而不是斜杠（/），但在代码中依然可以使用斜杠。

还可以将文件在计算机中的准确位置告诉python，这样就不用担心当前运行的程序存储在什么地方了。这称为绝对文件路径。在相对文件路径行不通时，可使用绝对路径。

绝对路径通常比相对路径长，因此将其赋给一个变量，再将该变量传递给open（）会有帮助：

> file_path = '/home/ehmatthes/other_files/text_files/filename.txt'
>
> with open(file_path) as file_object:

通过绝对路径，可读取系统中任何地方的文件。就目前而言，最简单的做法是，要么将数据文件存储在程序文件所在的目录，要么将其存储在程序文件所在目录下的一个文件夹中。

注意：如果在文件路径中直接使用反斜杠，将引发错误，因为反斜杠用于对字符串中的字符进行转义。例如\t就是制表符。如果一定要使用反斜杠，可对路径中的每个反斜杠都进行转义。C:\\\path\\\to\\\file.txt

##### 1.3  逐行读取

读取文件时，常常需要检查其中的每一行：可能要在文件中查找特定的信息，或者要以某种方式修改文件中的文本。

要以每次一行的方式检查文件，可对文件对象使用for循环：

```python
filename = 'pi_digits.txt'

with open(filename) as file_object:
    for line in file_object:
        print(line)
        
#运行结果：
#3.1415926535
#
#  8979323846
#
#  2643383279
```

将要读取的文件的名称赋给变量filename。这是使用文件时的一种常见做法。变量filename表示的并非实际文件——它只是一个让python知道到哪里去查找文件的字符串，因此可以轻松地将‘pi_digits.txt'替换为要使用的另一个文件的名称。调用open（）后，将一个表示文件及其内容的对象赋给了变量file_object。这里也使用了关键字with，让python妥善的打开和关闭文件。为查看文件的内容，通过对文件对象执行循环来遍历文件中的每一行。

结果发现空白行更多了。因为在这个文件中，每行的末尾都有一个看不见的换行符，而函数调用print（）也会加上一个换行符，因此每行末尾都有两个换行符：一个来自文件，另一个来自函数调用print（）。要消除多余的空白行，可在函数调用print（）中使用rstrip（）

```python
filename = 'pi_digits.txt'

with open(filename) as file_object:
    for line in file_object:
        print(line.rstrip())
        
#运行结果：
#3.1415926535
#  8979323846
#  2643383279
```

##### 1.4  创建一个包含文件各行内容的列表

使用关键字with时，open（）返回的文件对象只在with代码块内可用。如果要在with代码块外访问文件的内容，可在with代码内将文件的各行存储在一个列表中，并在with代码块外使用该列表：可以立即处理文件的各个部分，也可以推迟到程序后面再处理。

示例：

```python
filename = 'pi_digits.txt'

with open(filename) as file_object:
    lines = file_object.readlines()
    
for line in lines:
    print(line.rstrip())
    
#运行结果：
#3.1415926535
#  8979323846
#  2643383279
```

方法readlines()从文件中读取每一行，并将其存储在一个列表中。接下来列表赋给变量lines。在with代码块外，依然可以使用这个变量。

##### 1.5  使用文件内容

将文件读取到内存中后，就能以任何方式使用这些数据了。

下面以简单的方式使用圆周率的值。首先创建一个字符串，它包含文件存储的所有数字，且没有任何空格。

```python
filename = 'pi_digits.txt'

with open(filename) as file_object:
    lines = file_object.readlines()
    
pi_string = ''
for line in lines:
    pi_string += line.strip()
    
print(pi_string)
print(len(pi_string))

#运行结果：
#3.141592653589793238462643383279
#32
```

注意：  读取文本文件时，python将其中的所有文件都解读为字符串。如果读取的是数，并要将其作为数值使用，就必须使用函数int()将其转换为整数或使用函数float()将其转换为浮点数。

##### 1.6  包含一百万位的大型文件

```python
filename = 'pi_million_digits.txt'

with open(filename) as file_object:
    lines = file_object.readlines()

pi_string = ''
for line in lines:
    pi_string += line.strip()
    
print(f"{pi_string[:52]}...")
print(len(pi_string))

#运行结果：
#3.14159265358979323846264338327950288419716939937510...
#1000002
```

检查圆周率中是否包含自己的生日：

首先，将生日表示为一个由数字组成的字符串，再检查这个字符串是否包含在pi_string中：

```python
filename = 'pi_million_digits.txt'

with open(filename) as file_object:
    lines = file_object.readlines()

pi_string = ''
for line in lines:
    pi_string += line.strip()
    
birthday = input("Enter your birthday, in the form mmddyy: ")
if birthday in pi_string:
    print("You birthday appears in the first million digits of pi!")
else:
    print("You birthday does not appear in the first million digits of pi.")
    
#运行结果：
#Enter your birthday, in the form mmddyy: 120372
#You birthday appears in the first million digits of pi!
```

#### 2.写入文件

保存数据最简单的方式之一就是将其写入文件中。通过将输出写入文件，即便关闭包含程序输出的终端窗口，这些输出也依然存在：可以在程序运行结束后查看这些输出，可以与别人分享输出文件，还可以编写程序来将这些输出读取到内存中并进行处理。

##### 2.1  写入空文件

将文本写入文件，在调用open()时需要提供另一个实参，告诉python你要写入打开的文件。

示例：

```python
filename = 'programming.txt'

with open(filename,'w') as file_object:
    file_object.write("I love programming.")
    
#运行结果：

```

<img src="../AppData/Roaming/Typora/typora-user-images/image-20230802085642509.png" alt="image-20230802085642509" style="zoom: 50%;" />

调用open()时，提供了两个实参。第一个实参也是要打开的文件的名称，第二个实参（‘w’）告诉python，要以写入模式打开这个文件。打开文件时，可指定读取模式（‘r’）、写入模式（‘w’）、附加模式（‘a’）或读写模式（‘r+’）。如果省略了模式实参，python将以默认的只读模式打开文件。

如果要写入的文件不存在，函数open（）将自动创建它。然而，以写入模式（‘w’）打开文件时注意，因为如果指定的文件已经存在，python将在返回文件对象前清除该文件的内容。

注意：python只能将字符串写入文本文件，要将数值数据存储到文本文件中，必须先使用函数str（）将其转换为字符串格式。

##### 2.2  写入多行

函数write()不会在写入的文本末尾添加换行符，因此如果写入多行时没有指定换行符，结果不会换行。

要让每个字符串都单独占一行，需要在方法调用write()中包含换行符。还可以使用空格、制表符和空行来设置这些输出格式。

##### 2.3  附加到文件

如果要给文件添加内容，而不是覆盖原有的内容，可以以附加模式打开文件。以附加模式打开文件时，python不会在返回文件对象前清空文件内容，而是将写入文件的行添加到文件末尾。如果指定的文件不存在，python将为你创建一个空文件。

#### 3.异常

Python使用称为异常的特殊对象来管理程序执行期间发生的错误。每当发生让Python不知所措的错误时，它都会创建一个异常对象。如果你编写了处理该异常的代码，程序将继续运行；如果未对异常进行处理，程序将停止并显示traceback，其中包含有关异常的报告。

异常是使用try-except代码块处理的。try-except代码块让python执行指定的操作，同时告诉python发生异常时怎么办。使用try-except代码块时，即便出现异常，程序也将继续运行：显示您编写的友好的错误消息，而不是令用户迷惑的traceback。

##### 3.1  处理ZeroDivisionError异常

> print(5/0)

![image-20230802092943631](../AppData/Roaming/Typora/typora-user-images/image-20230802092943631.png)

红色单词指出的错误是：ZeroDivisionError是个异常对象。python无法按照要求做时，就会创建这种对象。这种情况下，python将停止运行程序，并指出引发了哪种异常，而我们可根据这些信息对程序进行修改。

下面来告诉python，发生这种错误时该怎么办。这样再发生此类错误，就有备无患了。

##### 3.1  使用try-except代码块

当你认为可能会发生错误时，可编写一个try-except代码块来处理可能引发的异常。

```python
try:
    print(5/0)
except ZeroDivisionError:
    print("You can't divide by zero!")
    
#运行结果：You can't divide by zero!
```

将导致错误的代码行print（5/0）放在一个try代码块中，如果try代码块中的代码运行起来没有问题。python将跳过except代码块；如果try代码块中的代码导致了错误，python将查找与之匹配的except代码块并运行其中的代码。

如果try-except代码块后面还有其他代码，程序将接着运行，因为已经告诉了Python如何处理这种错误。

##### 3.2  使用异常避免崩溃

发生错误时，如果程序还有工作尚未完成，妥善地处理错误就尤其重要。这种情况经常出现在要求用户提供输入的程序中；如果程序能够妥善地处理无效输入，就能再提示用户提供有效的输入，而不至于崩溃。

示例：执行除数为0的除法运算时，它就崩溃了。

```python
print("Give me two numbers, and I'll divide them.")
print("Enter 'q' to quit.")

while True:
    first_number = input("\nFirst number: ")
    if first_number == 'q':
        break
    second_number = input("Second number: ")
    if second_number == 'q':
        break
    
    answer = int(first_number) / int(second_number)
    print(answer)
```

![image-20230802101328701](../AppData/Roaming/Typora/typora-user-images/image-20230802101328701.png)

##### 3.3  else代码块

通过将可能引发错误的代码放在try_except代码块中，可提高程序抵御错误的能力。错误是执行除法运算的代码导致的，因此需要将它放到try_except代码块中。

示例：

```python
print("Give me two numbers, and I'll divide them.")
print("Enter 'q' to quit.")

while True:
    first_number = input("\nFirst number: ")
    if first_number == 'q':
        break
    second_number = input("Second number: ")
    if second_number == 'q':
        break
    
    try:
        answer = int(first_number) / int(second_number)
    except ZeroDivisionError:
        print("You can't divide by 0!")
    else:
        print(answer)
        
```

如果try代码块因除零错误而失败，就打印一条友好消息，告诉用户如何避免这种错误。

工作原理：

python尝试执行try代码块中的代码，只有可能引发异常的代码才需要放在try语句中。有时候，有一些仅在try代码块成功执行才需要运行的代码，这些代码应放在else代码块中。except代码块告诉python，如果尝试运行try代码块中的代码时引发了指定的异常该怎么办。

通过预测可能发生错误的代码，可编写健壮的程序。它们即便面临无效数据或缺少资源，也能继续运行，从而抵御无意的用户错误和恶意的攻击。

##### 3.4  处理FileNotFoundError异常

使用文件时，一种常见的问题就是找不到文件：文件可能在其他地方，文件名可能不正确，或者这个文件根本就不存在。对于所有这些情形都可使用try-except代码块以直观的方式处理。

```python
filename = 'alice.txt'

with open(filename,encoding='utf-8') as f:
    contents = f.read()
```

使用变量f来表示文件对象，给参数encoding指定了值，在系统的默认编码与要读取文件使用编码不一致时，必须这样做。

Python无法读取不存在的文件，因此引发异常。

修改：

```python
filename = 'alice.txt'

try:
    with open(filename,encoding='utf-8') as f:
        contents = f.read()
except FileNotFoundError:
    print(f"Sorry, the  file {filename} does not exit.")
    
#运行结果：Sorry, the  file alice.txt does not exit.
```

##### 3.5  分析文本

你可以分析整本书的文件文本。

示例：

```python
filename = 'alice.txt'

try:
    with open(filename,encoding='utf-8') as f:
        contents = f.read()
except FileNotFoundError:
    print(f"Sorry, the  file {filename} does not exit.")
else:
    #计算该文件大致包含多少个单词。
    words = contents.split()
    num_words = len(words)
    print(f"The file {filename} has about {num_words} words.")
    
#运行结果：The file alice.txt has about 29465 words.
```

方法split（）可以根据字符串创建一个单词列表，以空格为分隔符将字符串分拆成多个部分，并将这些部分都存储到一个列表中。结果是一个包含字符串中所有单词的列表，虽然有些单词可能包含标点，但大致可以计算一共多少个单词。

##### 3.6  使用多个文件

```python
def count_words(filename):
    """计算一个文件大致包含多少个单词。"""
    try:
        with open(filename,encoding='utf-8') as f:
            contents = f.read()
    except FileNotFoundError:
        print(f"Sorry, the  file {filename} does not exit.")
    else:
        #计算该文件大致包含多少个单词。
        words = contents.split()
        num_words = len(words)
        print(f"The file {filename} has about {num_words} words.")
        
filenames = ['alice.txt','siddhartha.txt','moby_dick.txt','little_women.txt']
for filename in filenames:
    count_words(filename)
    
#运行结果：
#The file alice.txt has about 29465 words.
#Sorry, the  file siddhartha.txt does not exit.
#The file moby_dick.txt has about 215830 words.
#The file little_women.txt has about 189079 words.
```

##### 3.7  静默失败

在前一个示例中，我们告诉用户有一个文件找不到。但并非每次捕获到异常都需要告诉用户，有时候你希望程序在发生异常时保持静默，就像没有发生一样继续运行。要让程序静默失败，可像通常那样编写try代码块，但在except（）代码块中明确地告诉python什么都不要做。python有一个pass语句，可用于让python在代码块中什么都不要做。

```python
def count_words(filename):
    """计算一个文件大致包含多少个单词。"""
    try:
        with open(filename,encoding='utf-8') as f:
            contents = f.read()
    except FileNotFoundError:
        pass
    else:
        #计算该文件大致包含多少个单词。
        words = contents.split()
        num_words = len(words)
        print(f"The file {filename} has about {num_words} words.")
        
filenames = ['alice.txt','siddhartha.txt','moby_dick.txt','little_women.txt']
for filename in filenames:
    count_words(filename)
    
#运行结果：
#The file alice.txt has about 29465 words.
#The file moby_dick.txt has about 215830 words.
#The file little_women.txt has about 189079 words.
```

比之前变化地就是pass，出现FileNot-FoundError异常时，将执行except代码块中的代码，但什么都不会发生。这种错误发生时，不会出现traceback，也没有任何输出。

pass语句还充当到了占位符，提醒你在程序的某个地方什么都没做，并且以后也需要在这里做些什么，用户读不到，但我们可以读到它，进而处理所有找不到文件的问题。

#### 4.存储数据

很多程序要求用户输入某种信息，如让用户存储游戏首选项或提供要可视化的数据。不管关注点是什么，程序都把用户提供的信息存储在列表和字典等数据结构中。用户关闭程序时，几乎总是要保存他们提供的信息。一种简单的方式是，使用模块json来存储数据。

模块json让你能够将简单的python数据结构存储到文件中，并在程序再次运行时加载该文件中的数据。你可以使用json在python程序之间分享数据。

##### 4.1  使用json.dump()和json.load()

函数json.dump()接受两个实参：要存储的数据，以及可用于存储数据的文件对象。

先导入模块json，再创建一个数字列表。接着指定了要将数字列表存储到哪个文件中。通常使用文件拓展名.json来指出文件存储的数据为JSON格式。接下来，以写入模式打开这个文件，让json能够将数据写入其中。使用函数json.dump将数字列表存储到文件numbers.json中。

```python
import json

numbers = [2,3,5,7,11,13]

filename = 'numbers.json'
with open(filename,'w') as f:
    json.dump(numbers,f)
```

在编写一个程序，使用json.load()将列表读取到内存中：

```python
import json

filename = 'numbers.json'

with open(filename) as f:
    numbers =json.load(f)
    
print(numbers)

#运行结果：[2, 3, 5, 7, 11, 13]
```

确保要读取的文件。以读取方式打开该文件，因为python只需要读取它。使用函数json.load()加载存储在number.json中的信息，并将其赋给变量numbers。最后，打印恢复的数字列表。

这是一种在程序之间共享数据的简单方式。

##### 4.2  保存和读取用户生成的数据

使用json保存用户生成的数据大有裨益，因为如果不以某种方式存储，用户的信息会在程序停止运行时丢失。

```python
import json

username = input("What is your name? ")

filename = 'username.json'

with open(filename,'w') as f:
    json.dump(username,f)
    print(f"We'll remember you when you come back,{username}!")  
```

```python
import json

filename = 'username.json'

with open(filename) as f:
    username = json.load(f)
    print(f"Welcome back,{username}!")
```

两个程序合并到一个程序中

```python
import json

#如果以前存储了用户名，就加载它。
#否则，提示用户输入用户名并存储它。
filename = 'username.json'
try:
    with open(filename) as f:
        username = json.load(f)
except FileNotFoundError:
    username = input("What is your name?")
    with open(filename,'w') as f:
        json.dump(username,f)
        print(f"We'll remember you when you come back,{username}!")
else:
    print(f"Welcome back,{username}!")
```

##### 4.3 重构

你经常会遇到这样的情况：代码能够正确的运行，但通过将其划分为一系列完成具体工作的函数，还可以改进。这样的过程称为重构。重构让代码更清晰、更易于理解、更容易拓展。

### 第10章  测试代码

编写函数或类时，还可为其编写测试。通过测试，可确定代码面对各种输入都能够按要求的那样工作。

#### 1.测试函数

要学习测试，必须有要测试的代码。

##### 1.1  单元测试和测试用例

python标准库中的模块unittest提供了代码测试工具。单元测试用于核实函数的某个方面没有问题。 测试用例是一组单元测试，它们一道核实函数在各种情形下的测试。全覆盖的测试用例包含一整套单元测试，涵盖了各种可能的函数使用方式。对于大型项目，要进行全覆盖测试可能很难。通常最初只要针对代码的重要行为编写测试即可，等项目被广泛使用时，再考虑全覆盖。

##### 1.2  可通过测试

你需要一段时间才能习惯创建测试用例的语法，但创建测试用例之后，再添加针对函数的单元测试就很简单了。要为编写的函数编写测试用例，可先导入模块unittest和要测试的函数，再创建一个继承unittest.TestCase的类，并编写一系列方法对函数行为的不同方面进行测试。
