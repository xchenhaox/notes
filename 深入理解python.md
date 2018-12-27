```bash
tar -cvf abc.tar *.py
tar -zcvf abc.tar.gz *.py
tar -zxvf abc.tar.gz
tar -zxvf abc.tar.gz -C ./test  # 指定解压路径

tar -jcvf hij.tar.bz2 *.py
tar -jxvf hij.tar.bz2 *.py

zip abc.zip *.py
unzip abc.zip
unzip -d ./test abc.zip  # 指定解压路径

cal  # 日历
cal -y 2018

ps -aux
top
htop
kill -9 9822  # -9 代表强制

# 手动设置 IP 地址
sudo ifconfig ens33 172.16.7.139

sudo -s  # Ubuntu 切换到 root

gedit a.py


find ./ name "[A-Z]" -size +4k -size -5M -perm 0777

gzip -r test.tar test.tar.gz
gzip -d test.tar.gz

useradd -d /home/abc abc -g test m
userdel -r abc
usermod -G xxx dongGe
groups dongGe

# 为创建的普通用户添加 sudo 权限
sudo usermod -a -G adm 用户名
sudo usermod -a -G sudo 用户名

# usermod -g 与 -G 的区别
# -g 用来制定这个用户默认的用户组
# -G 一般配合 -a 来完成向其它组添加

chmod u+x test.txt
chmod g-w test.txt
chmod o+w test.txt
chmod u=rw,g=x,o=r 1.py
chmod u=,g=,o= hy.txt
chmod u=rwx,g=rx,o=r fi.txt
chmod u=7,g=5,o=4 fi.txt
chmod 751 fi.txt
chmod 777 test/ -R

# chown chgrp

date '+%y,%m,%d,%H,%M,%S'

df -m
du -s temp/ -h


scp -r 源文件或目录  目标文件或目录
scp -r root@192.168.1.100:/home/root/QQ_dir/ ./mytest/lisi

# 本地文件复制到远程：
scp FileName RemoteUserName@RemoteHostIp:RemoteFile
scp FileName RemoteHostIp:RemoteFolder
scp FileName RemoteHostIp:RemoteFile
# 本地目录复制到远程：
scp -r FolderName RemoteUserName@RemoteHostIp:RemoteFolder
scp -r FolderName RemoteHostIp:RemoteFolder


# 远程文件复制到本地：
scp RemoteUserName@RemoteHostIp:RemoteFile FileName
scp RemoteHostIp:RemoteFolder FileName
scp RemoteHostIp:RemoteFile FileName
# 远程目录复制到本地：
scp -r RemoteUserName@RemoteHostIp:RemoteFolder FolderName
scp -r RemoteHostIp:RemoteFolder FolderName
```





---

```python
#!/usr/bin/python
#coding=utf-8

# 推荐使用 # -*- coding:utf-8 -*-

print("哈哈")



# 单行注释

'''
多行注释
'''

# 获取变量类型 type(变量名)

age = 10
print("我今年%d岁"%age)

age = 18
name = "xiaohua"
print("我的姓名是%s,年龄是%d"%(name,age))

print("12345\n") # 换行

password = raw_input("请输入密码:")
print '您刚刚输入的密码是:', password
raw_input()会把用户输入的任何值都作为字符串来对待

input()函数与raw_input()类似，但其接受的输入必须是表达式。

python3 中只有 input() 没有 raw_input()
python3中的input与python2中的raw_input()功能一样
```

```
常用的格式符号
下面是完整的，它可以与％符号使用列表:

格式符号	转换
%c	字符
%s	通过str() 字符串转换来格式化
%i	有符号十进制整数
%d	有符号十进制整数
%u	无符号十进制整数
%o	八进制整数
%x	十六进制整数（小写字母）
%X	十六进制整数（大写字母）
%e	索引符号（小写'e'）
%E	索引符号（大写“E”）
%f	浮点实数
%g	％f和％e 的简写
%G	％f和％E的简写


常用的数据类型转换
函数	说明
int(x [,base ])	将x转换为一个整数
long(x [,base ])	将x转换为一个长整数
float(x )	将x转换到一个浮点数
complex(real [,imag ])	创建一个复数
str(x )	将对象 x 转换为字符串
repr(x )	将对象 x 转换为表达式字符串
eval(str )	用来计算在字符串中的有效Python表达式,并返回一个对象
tuple(s )	将序列 s 转换为一个元组
list(s )	将序列 s 转换为一个列表
chr(x )	将一个整数转换为一个字符
unichr(x )	将一个整数转换为Unicode字符
ord(x )	将一个字符转换为它的整数值
hex(x )	将一个整数转换为一个十六进制字符串
oct(x )	将一个整数转换为一个八进制字符串
```




***变量类型***

- 数值型 Numbers
    + int
    + long
    + float
    + complex
- 布尔型 Boolean
    + True
    + False
- 字符串 String
- 列表 List
- 元组 Tuple
- 字典 Dictionary

***关键字***

```
import keyword
keyword.kwlist

and     as      assert     break     class      continue    def     del
elif    else    except     exec      finally    for         from    global
if      in      import     is        lambda     not         or      pass
print   raise   return     try       while      with        yield
```


***运算符***

算术运算符

```
+
-
*
/
%
// 取整除 9//2 => 4, 9.0//2.0 => 4.0
** 幂
```

赋值运算符

```
=
+=
-=
*=
/=
%=
**=
//=
```

关系运算符

```
==
<>
!=
<=
>=
```

关系运算符

```
and
or
not

```




***判断***

```
if age >= 18:
    print "成年"


if 条件:
   xxx
else:
   yyy


if xxx1:
    事情1
elif xxx2:
    事情2
elif xxx3:
    事情3
else:
    事情4    



import random

player = input('请输入：剪刀(0)  石头(1)  布(2):')

player = int(player)

computer = random.randint(0,2)

# 用来进行测试
#print('player=%d,computer=%d',(player,computer))

if ((player == 0) and (computer == 2)) or ((player ==1) and (computer == 0)) or ((player == 2) and (computer == 1)):
    print('获胜，哈哈，你太厉害了')
elif player == computer:
    print('平局，要不再来一局')
else:
    print('输了，不要走，洗洗手接着来，决战到天亮')
        
        
        
i = 0
while i<10000:
    print("媳妇儿，我错了")
    i+=1    




#encoding=utf-8

i = 1
sum = 0
while i<=100:
    sum = sum + i
    i += 1

print("1~100的累积和为:%d"%sum)




#encoding=utf-8

i = 1
sum = 0
while i<=100:
    if i%2 == 0:
        sum = sum + i
    i+=1

print("1~100的累积和为:%d"%sum)




for 临时变量 in 列表或者字符串等:
    循环满足条件时执行的代码
else:
    循环不满足条件时执行的代码
    
    
name = 'dongGe'
for x in name:
    print(x)
    
    
name = ''
for x in name:
    print(x)
else:
    print("没有数据")
    

break/continue只能用在循环中，除此以外不能单独使用
break/continue在嵌套循环中，只对最近的一层循环起作用





    b = "hello itcast.cn"
    或者
    b = 'hello itcast.cn' 
    
    
    
name = 'abcdef'

print(name[0])
print(name[1])
print(name[2])




切片是指对操作的对象截取其中一部分的操作。字符串、列表、元组都支持切片操作。

切片的语法：[起始:结束:步长]
注意：选取的区间属于左闭右开型，即从"起始"位开始，到"结束"位的前一位结束（不包含结束位本身)。




 name = 'abcdef'
 print(name[0:3]) # 取 下标0~2 的字符 

print(name[2:]) # 取 下标为2开始到最后的字符


print(name[1:-1]) # 取 下标为1开始 到 最后第2个  之间的字符 


>>> a = "abcdef"
 >>> a[:3]
 'abc'
 >>> a[::2]
 'ace'
 >>> a[5:1:2] 
 ''
 >>> a[1:5:2]
 'bd'
 >>> a[::-2]
 'fdb' 
 >>> a[5:1:-2]
 'fd'
 
 想一想
（面试题）给定一个字符串aStr, 请反转字符串
```


```
# 字符串常见操作
mystr = 'hello world'

# 检测 wor 是否包含于 mystr 当中：mystr.find(str, start=0, end=len(mystr))
# 如果是则返回开始处的索引值，否则返回 -1
mystr.find('wor') 

# 跟find()方法一样，只不过如果str不在 mystr中会报一个异常.
mystr.index(str, start=0, end=len(mystr))

# 返回 str在start和end之间 在 mystr里面出现的次数
mystr.count(str, start=0, end=len(mystr))

# 把 mystr 中的 str1 替换成 str2,如果 count 指定，则替换不超过 count 次.
mystr.replace(str1, str2,  mystr.count(str1))

# 以 str 为分隔符切片 mystr，如果 maxsplit有指定值，则仅分隔 maxsplit 个子字符串
mystr.split(str=" ", 2) 

# 把字符串的第一个字符大写
mystr.capitalize()

# 把字符串的每个单词首字母大写
>>> a = "hello itcast"
>>> a.title()
'Hello Itcast'

# 检查字符串是否是以 obj 开头, 是则返回 True，否则返回 False
mystr.startswith(obj)

# 检查字符串是否以obj结束，如果是返回True,否则返回 False.
mystr.endswith(obj)

# 转换 mystr 中所有大写字符为小写
mystr.lower()

# 转换 mystr 中的小写字母为大写
mystr.upper()

# 返回一个原字符串左对齐,并使用空格填充至长度 width 的新字符串
mystr.ljust(width)
mystr.rjust(width)
mystr.center(width)


mystr.lstrip()
mystr.rstrip()
# 删除mystr字符串两端的空白字符
>>> a = "\n\t itcast \t\n"
>>> a.strip()
'itcast'




类似于 find()函数，不过是从右边开始查找.

mystr.rfind(str, start=0,end=len(mystr))

似于 index()，不过是从右边开始.

mystr.rindex( str, start=0,end=len(mystr))

把mystr以str分割成三部分,str前，str和str后

mystr.partition(str)


类似于 partition()函数,不过是从右边开始.
mystr.rpartition(str)

按照行分隔，返回一个包含各行作为元素的列表

mystr.splitlines()

如果 mystr 所有字符都是字母 则返回 True,否则返回 False

mystr.isalpha() 

如果 mystr 只包含数字则返回 True 否则返回 False.

mystr.isdigit()

如果 mystr 所有字符都是字母或数字则返回 True,否则返回 False

mystr.isalnum()  

如果 mystr 中只包含空格，则返回 True，否则返回 False.

mystr.isspace()   

mystr 中每个字符后面插入str,构造出一个新的字符串

mystr.join(str)



（面试题）给定一个字符串aStr，返回使用空格或者'\t'分割后的倒数第二个子串  
```

推荐 python 电子书
链接：http://pan.baidu.com/s/1dFI4p7V 密码：7es5






```
 namesList = ['xiaoWang','xiaoZhang','xiaoHua']

列表中的元素可以是不同类型的

    testList = [1, 'a']
    
    namesList = ['xiaoWang','xiaoZhang','xiaoHua']
    print(namesList[0])
    
    
    namesList = ['xiaoWang','xiaoZhang','xiaoHua']
    for name in namesList:
        print(name)
        
        
    namesList = ['xiaoWang','xiaoZhang','xiaoHua']

    length = len(namesList)

    i = 0

    while i<length:
        print(namesList[i])
        i+=1
        

# 增        
nameList.append('dawang')

list2 = ['hello', 'world']
nameList.extend(list2) // ['xiaoWang','xiaoZhang','xiaoHua', 'hello', 'world'] 

# insert(index, object)
nameList.insert(1, 'abc')
// ['xiaoWang', 'abc', 'xiaoZhang','xiaoHua', 'hello', 'world']

# 改
nameList[1] = 'great'
// ['xiaoWang', 'great', 'xiaoZhang','xiaoHua', 'hello', 'world']

# 查
// in, not in
if 'great' in nameList:
    print("yes")

// index, count
a = ['a', 'b', 'c', 'a', 'b']
a.index('a', 1, 3) // 左闭右开，找不到出错
a.index('a', 1, 4) // 3
a.count('b') // 2
a.count('d') // 0

# 删
// del, pop, remove

del nameList[2]
nameList.pop()
nameList.remove('hello')

# 排序
// sort, reverse
a = [1, 4, 2, 3]
a.reverse() // [3, 2, 4, 1]
a.sort() // [1, 2, 3, 4]
a.sort(reverse=True) // [4, 3, 2, 1]


#encoding=utf-8

import random

# 定义一个列表用来保存3个办公室
offices = [[],[],[]]

# 定义一个列表用来存储8位老师的名字
names = ['A','B','C','D','E','F','G','H']

i = 0
for name in names:
    index = random.randint(0,2)    
    offices[index].append(name)


len(namnes)
```

```
# 元组
# 元组的元素不能修改
tuple=('hello', 100, 3.14)
print(tuple[0])

a = ('a', 'b', 'c', 'a', 'b')
a.index('a', 1, 3) // 报错
a.index('a', 1, 4) // 3
a.count('b') // 2
a.count('d')

```



```
info = {'name':'班长', 'id':100, 'sex':'f', 'address':'地球亚洲中国北京'}
print(info['name'])
print(info['age']) // 访问不存在的键 报错
在我们不确定字典中是否存在某个键而又想获取其值时，可以使用get方法，还可以设置默认值：

>>> age = info.get('age')
>>> age #'age'键不存在，所以age为None
>>> type(age)
<type 'NoneType'>
>>> age = info.get('age', 18) # 若info中不存在'age'这个键，就返回默认值18
>>> age
18


# 修改
info['id'] = 99

# 新增
info['weight'] = 120

# 清空/删除
info.clear() # 清空

del info['name']

del info # 删除整个字典


dict = {"name": 'zhangsan', "sex": 'm'}
len(dict) // 2
dict.keys() // ['name', 'sex']
dict.values()  // ['zhangsan', 'm']
dict.items() // [('name', 'zhangsan'), ('sex', 'm')]
dict.has_key('name') // True

for key, value in dict.items():
    print(key, value)


>>> chars = ['a', 'b', 'c', 'd']
>>> for i, chr in enumerate(chars):
...     print i, chr
...
0 a
1 b
2 c
3 d
```


```
字符串/列表/元组：+/*/in/not in
字典：in/not in/  in在对字典操作时，判断的是字典的键

```

```
内置函数
cmp(item1, item2)  cmp在比较字典数据时，先比较键，再比较值
len(item)
max(item)  在比较字典数据时，只比较键
min(item)
del(item) // del a[0] 或 del(a[0])
```

```
引用
>>> a = [1, 2]
>>> b = a
>>> id(a)
139935018544808
>>> id(b)
139935018544808
>>> a.append(3)
>>> a
[1, 2, 3]
>>> id(a)
139935018544808
>>> id(b)       # 注意a与b始终指向同一个地址
139935018544808





可变类型，值可以改变：

列表 list
字典 dict
不可变类型，值不可以改变：

数值类型 int, long, bool, float
字符串 str
元组 tuple
```


```
    # 定义一个函数，能够完成打印信息的功能
    def printInfo():
        print '------------------------------------'
        print '         人生苦短，我用Python'
        print '------------------------------------'
        
        
    # 调用
     printInfo()


函数的文档说明
>>> def test(a,b):
...     "用来完成对2个数求和"
...     print("%d"%(a+b))
... 
>>> 
>>> test(11,22)
33
如果执行，以下代码

>>> help(test)
能够看到test函数的相关说明

Help on function test in module __main__:

test(a, b)
    用来完成对2个数求和
(END)

```



```python
import this
```

python 家族：

- C 语言实现：CPython，扩展可用 C/C++
- Java 实现：Jython，扩展可用 Java
- .Net 实现：IronPython，扩展可用 C#

python 能干什么？

- 科学计算
- 图形化开发
- 系统脚本
- web 服务器
- 网络爬虫
- 服务器集群自动化运维

ipython 解释器

```ipython
import requests
res=requests.get("http://www.baidu.com")
savefile=open("baidu.html", "w")
savefile.write(res.content)
savefile.close()
%history
```

```shell
cat baidu.html
```

```python
a = 123
b = 123
c = 123
print a
print b
print c
b = 789
print a
print b
print c
id(a)
id(b)
id(c)


a=1
c=2
id(a)
id(c)
e=123
id(e) #123 地址空间单元没有马上释放
def e
f=123
id(f)
```

```shell
# 中文的话要加上指定编码
# # -- coding:UTF-8 -- 或者 #coding=utf-8
vim test.py
cat test.py
  #! /usr/bin/python
  #coding=utf-8
  
  import requests
  res=requests.get("http://www.baidu.com")
  savefile=open("baidu.html", "w")
  savefile.write(res.content)
  savefile.close()
  # 二三四五六

```

### 简单函数

```python
def add(x, y):
  z = x + y
  return z

res = add(3, 5)
print res
# 8
```

### 局部变量与全局变量
```python
# 局部变量作用域覆盖全局变量
def p_num():
    num=5
    print num

num=10
p_num()
print num
# 5 10
```
```python
# 函数内有局部变量定义，解释器不使用全局变量，局部变量的定义晚于被引用，报错
def p_num:
    print num
    num=5
    print num

num=10
p_num()
print num
# 结果出错
```
```python
# 函数内部可以直接访问全局变量
def p_num():
    print num

num=10
p_num()
print num
# 10 10
```
```python
# 函数内部修改全局变量，使用 global 关键字
def p_num():
    global num
    print num
    num = 20
    print num

num=10
p_num()
print num
```

### 特殊变量
```
_xxx from module import (无法导入）
__xxx__ 系统定义的变量
__xxx 类的本地变量
```
### 表达式
#### 算术表达式
```
+a
-a
a + b
a - b
a ** b
a * b
a / b 真正除，浮点数保留小数
a // b  a除以b，向下取整
a % b
```
#### 逻辑表达式
```
not a
a and b
a or b
a is b  a和b是同一个对象
a is not b  a和b不是同一个对象
```
#### 关系表达式
```
==
!=
<> 废弃
>
<
>=
<=
```
#### 位运算
```
~a
a << n
a >> n
a & b
a | b
a ^ b
```
### 语法格式
缩进表示关系，函数、分支、循环语句后面带 ":"
### 分支语句
```python
a = 10
b = 5

if a > b:
    print "aaa"
    # print("aaa") python3 写法
    if a == 10:
        print "a=10"
else
    print "bbb"

if a > b:
    print "a>b"
elseif a==b:
    print "a==b"
else:
    print "a<b"

```
### 循环语句
```
while 判断条件:
    执行语句

for iterating_var in sequence:
    执行语句
```
```python
var = 1
while var == 1:
    num = raw_input("Enter a number: ")
    print "You enterd: %d", num
    
    print "Good bye!"
```
```python
for letter in 'Python':
    print "Current Letter: ", letter

fruits = ['banana', 'apple', 'mango']
for fruit in fruits:
    print 'Current fruit: ', fruit
```

在 Python 中，for ... else 表示这样的意思：for 中的语句和普通的没有区别，else 中的语句会在循环正常执行完（即 for 不是通过 break 跳出而中断的）的情况下执行，while ... else 也是一样

```python
count = 0
while count < 5:
    print(count, " is less than 5")
    count = count + 
else:
    print(count, " is not less than 5")


fruits = ['banana', 'apple', 'mango']
for fruit in fruits:
    print "Current fruit: ", fruit
    if fruit == 'apple':
        break
else:
    print "ok"
```

### list 列表
```ipython
demolist = [1, 2, 3, 4]
type(demolist)
#list

print demolist
#[1, 2, 3, 4]

demolist[0]
#1

demolist[1]=10
print demolist
#[1, 10, 3, 4]

del demolist[2]
print demolist
#[1, 10, 4]

demolist.pop()
#4

demolist
#[1, 10]

demolist.append(20)
demolist
#[1, 10, 20]

demolist.append('hello')
demolist.append(1,23)
demolist.append([1, 3, 'b'])

len(demolist)
#7

#列表拼接
demolist + [100, 200]

#相当于对其中元素拷贝一份
demolist * 2

20 in demolist
#True

212 in demolist
#False

testlist=['sp', 'qq', 'am']
testlist[2]
#am
testlist[-2]
#qq
testlist[1:]
#['qq', 'am']
testlist[0:1]
#['sp', 'qq']
```
```
# 列表函数 & 方法
函数
cmp(list1, list2)
len(list)
max(list)
min(list)
list(seq) 将元组转换为列表

方法
list.append(obj)
list.count(obj) 统计某个元素在列表中出现的次数
list.extend(seq) 在列表末尾一次性追加另一个序列中的多个值（用新列表扩展原来的列表）
list.index(obj)
list.insert(index, obj)
list.pop() 移除列表中的一个元素（默认最后一个元素）
list.remove(obj)
list.reverse()
list.sort([func])
```

### 元组
元组与列表类似，不同之处在于元组的元素不能修改。也可以进行分片和连接操作。元组使用小括号，列表使用方括号。相当于只读的列表

```python
aTuple=('et', 77, 99,9)
aTuple[2]
#99.9
aTuple[1:2]
#(77, 99.9)
```

### 字典
映射数据类型，由 key-value 构成，类似于关联数组或哈希表。key 一般以数字和字符串居多，值则可以是任意类型的 python 对象，如其他容器模型。字典元素用大括号 {}。

```python
dict = {'Alice': '2341', 'Beth': '9102', 'Cecil': '3258}

dict['Beth']
#2341

for key in dict
    print key, dict[key]

dict.keys()
dict.values()

dict['Alice']=100
del dict['Cecil']

dict.clear()
del dict

```

```
cmp(dict1, dict2)
len(dict)
str(dict)
type(variable)

dict.clear()
dict.copy()
dict.fromkeys()
dict.get(key, default=None)
dict.has_key(key)
dict.items()
dict.keys()
dict.setdefault(key, default=None)
dict.update(dict2)
dict.values()

```


## 字符串处理函数

```python
var1 = 'Hello world1'
var2 = "Python Programing"
var3 = '''hello world'''
var4 = """hello world"""

#三引号允许一个字符串跨多行，字符串中可以包含换行符、制表符以及其他特殊字符

type(var1)
#str

print "hello \"dear\""
print '''hello "dear"'''

var1[0]
#H
var1[-2]
#d

var1[0:4]
#Hello

id(var1)


var1='test'
id(var1)
#更新不是在原地址空间，而是开辟了一个新的地址空间
```

```
+ 字符串拼接    a + b：HelloPython
* 重复输出字符串    a * 2：HelloHello
[n] 通过索引获取字符    a[1]：e
[m:n] 截取字符串中的一部分    a[1:4]：ell
in 成员运算符    'e' in a：True
not in
r/R 原始字符串    print 'hello\n\n'
                print r'hello\n\n'
                
print "My name is %s and weight and is %d kg!" % ("Zara", 60)
```

#### 字符串各种函数
```ipython
mystr = 'hello world test'

mystr.find(str, start=0, end=len(mystr))
mystr.index(str, start=0, end=len(mystr)) #找不到时报异常
mystr.count(str, start=0, end=len(mystr))

help(mystr.find)

mystr.decode(encoding='UTF-8', errors='strict')
mystr.encode(encoding='UTF-8', errors='strict')
mystr.replace(str1,. str2, mystr.count(str1))
mystr.split(str=" ", 2)


type(mystr)
#str
mystr.decode(encoding='UTF-8')
#u'hello world test'
s2=mystr.decode(encoding='UTF-8')
type(s2)
#unicode

mystr.captitalize()
mystr.center(width)

mystr.replace('test', 'yes')


mystr.split(' ')
mylist=mystr.split(' ', 2)

type(mylist)

mylist.sort()

mystr.center(50)

mystr.endswith('test')
mystr.startswith('hello')

mystr.expandtabs()

mystr.isalnum()
mystr.isalpha()

mystr.isdecimal()
mystr.isdigit()

mystr.islower()
mystr.isnumeric()
mystr.isspace()
mystr.istitle()
mystr.isupper()

mystr.lower()
mystr.upper()

mystr.join()
mystr.ljust(width)
mystr.rjust(width)
mystr.lstrip()
mystr.rstrip()
mystr.rfind(str, start=0, end=len(mystr))
mystr.partition(str)
mystr.rpartition(str)


mystr.splitlines()
mystr.zfill(width)
```

```
def functionname (paramters):
    "注释"
    function_suite
    return [expression]
```

test.py

```python
#! /usr/bin/python

def printname(str):
    "print your name by str"
    print str
    return
```
```ipython
import test
test.printname('cpp')
help(test.printname)
```
### 按值/引用传参
```python
#! /usr/bin/python

def changeme(mylist):
    "修改传入的列表"
    mylist.append([1, 2, 3, 4])
    print "函数内取值：", mylist
    return
```

### 参数
test.py

```python
#! /usr/bin/python
# coding=utf-8

def changeme(a, b)
    print a
    return
```
```ipython
import test
test.changeme(1, 2)
#1

#命名参数
test.changeme(b=1, a=2)
#2
```

```python
#! /usr/bin/python
# coding=utf-8

def arglist(a, *b)
    print a
    print b
    return
    
def arglist2(a, **b)
    print a
    print b
    return
```

```ipython
import test
test.arglist(1, 2, 3, 4, 5, 6, 7, 8, 9)
#1
#(2, 3, 4, 5, 6, 7, 8, 9)

test.arglist2('aa', x=12, y=34)
#aa
#{'x': 12, 'y': 34}
```

### 匿名函数
```ipython
sum = lambda a, b: a+b
sum(10, 20)
#30
type(sum)
#function
```
### return 语句
```python
#! /usr/bin/python
# coding=utf-8

def arglist():
    print "call arglist"
    return 1, 2, 3, 4, 5, 6
```

```ipython
import test
res=test.arglist()
print res
#(1, 2, 3, 4, 5, 6)

```




## 面向对象

```
class ClassName:
    '类的帮助信息'  #类文档字符串
    类变量         #类体 class_suite 由类成员，方法，数据属性组成
    def __init__(self, parameters):
    def 函数(self, ...)
    ... ...
```

demo.py

```python
#! /usr/bin/python

class Employee:
    '''
    this is a test demo class
    
    '''
    
    classStr = "it is a test class"
    
    def __init__(self, name, pay):
        self.name = name
        self.pay = pay
    
    def hello(self):
        '''
        say hello
        '''
        print self.name
        print "say hello"
```
```ipython
import demo
worker = demo.Employee('xiaoming', 100000)
type(worker)
#instance

worker.hello()
#xiaoming
#say hello

helo(worker)

```

```
getattr()
hasattr()
setattr()
delattr()
```

### 内置类属性
```
__dict__
__doc__
__name__
__module__
__bases__
```

### 继承
demo.py

```python
#! /usr/bin/python

class Parent:
   parentAttr = 100
   def __init__(self):
       print "调用父类构造函数"
   def parentMethod(self):
       print "调用父类方法"
   def setAttr(self, attr):
       Parent.parentAttr = attr
   def getAttr(self):
       print "父类属性：", Parent.parentAttr

class Child(Parent):
   def __init__(self):
       Parent()
       print "调用子类构造方法"
   def childMethod(self):
       print "调用子类方法 child method"
```

```ipython
from demo import Parent, Child
p1=Parent()
p1.parentMethod()
p1.getAttr()
p1.setAttr(200)
p1.getAttr()

p2 = Child()
p2.childMethod()
p2.parentMethod()
p2.getAttr()
```

### 运算符重载
```python
#! /usr/bin/python

class Vector:
    def __init__(self, a, b):
        self.a = a
        self.b = b

    def  __str__(self):
        return 'Vector (%d, %d)' % (self.a, self.b)

    def  __add__(self, other):
        return Vector(self.a + other.a, self.b + other.b)

v1 = Vector(2, 10)
v2 = Vecotr(5, -2)
print v1 + v2
#Vector(7, 8)

```

```
__private_attrs 类的私有属性
    两个下划线开头，声明该属性为私有

__private_method 类的私有方法

```
```python

p1 = Vector()
dir(p1)
print p1._Parent__six
```

```python
class Student(Object):

    '类的方法'
    @classmethod
    def showClass():
        print 'class'

```

```python
import module1, module2
module1.method1()

from demo import Parent, Child

from demo import *

import os
#PYTHONPATH
```

```python
from demo import *

dir(Parent)
help(Parent)

globals() #全局变量
locals()  #局部变量

```

### 模块发布
```
setup.py
suba/
    aa.py
    bb.py
    __init__.py
subb/
    cc.py
    dd.py
    __init.py

#setup.py
from distutils.core import setup

setup(name="xwp", version="1.0", description="xwp's module", author="xingwenpeng", py_modules=['suba.aa', 'suba.bb', 'subb.cc', 'subb.dd'])


$ python setup.py build
$ python setup.py sdist
# 生成一个压缩包 dist/xwp-1.0-tar.gz
$ cp dist/xwp-1.0-tar.gz ~/
$ cd ~/
$ tar zxvf xwp-1.0-tar.gz
$ cd xwp-1.0
$ python setup.py install

#python
import suba.aa
suba.aa.showaa()

```

```
Python 核心编程
Python Cookbook 中文版
Python 学习手册

```



## 文件操作
```ipython
buf=raw_input()
print buf
type(buf)
#str

#yourname=raw_input('plz input your name: ')
yourname=input('plz input your name: ')
print yourname

fp=open('hello.txt', 'w')
fp.write('hello world c++')
fp.close()

fp=open('hello.txt', 'r')
buf=fp.read()
fp.close()


fp=open('hello.txt', 'r+')
fp.mode
#r+
fp.name
#hello.txt
fp.closed
#False
fp.close()
fp.closed
#True

fp.open('hello.txt', 'r+')
fp.mode
buf=fp.read(100)
print buf
fp.write('and it')
fp.close()

fp.open('hello.txt', 'r+')
buf=fp.read() #指针跑到结尾
print buf
fp.write('abc') #结尾处添加
fp.flush()
fp.seek(0) #指针回到开头
buf=fp.read() #读到结尾，指针在结尾
print buf

help(fp)

#读写共用一个指针

#apt-get install ipython
```

```
文件操作模式
r
w 写，如果文件不存在则创建，如果文件存在则截断文件
a

r+ 读写
w+ 读写，如果文件不存在则创建，如果文件存在则截断文件
a+ 追加打开，读写，文件不存在则创建

```

### 应用案例
```python

import Image, ImageFont, ImageDraw

im = Image.open('./xwp.jpg')
draw = ImageDraw.Draw(im)

fontsize = min(im.siz) / 4
font = ImageFont.truetype('KhmerOS.ttf', fontsize)

draw.text((im.size[0] - fontsize, 0), '8', font=font, fill=(256, 0, 0))

im.save('./aaa.jpg', 'jpeg')
```
eog

%history

```python
import requests
r=requests.get('http://baidu.com')
print r.url
print r.text
print r.content


```

nc 123.57.211.212 9090
































