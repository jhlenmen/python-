#	一、基础语法

//**速通**使用，笔记较为简略，以框架为主，结合搜索引擎使用:blush:，命名方式不是个好习惯切勿学习

###	输出

```python
print("我的国籍是%s" % country)
print("我的年龄是%d岁，我的国籍是%s" % (age, country))
----------------------------------------------------
str = "我的名字是{}，我的国籍是{}".format("张三", "中国")
print(str)
---------------------------------------------------
print(f"haolei{n}")


print("hhh",end="")#输出不换行
```

###	输入:                

 a=intput()                     （字符串



### 运行期间停一段时间

```python
time.sleep(时长) #需要在前边导入时间模块(import time)
#详细见  六.1
```

###	其他：

（规则同c，不需要大括号，根据行的对齐来决定范围)

####	选择

if a<b:       

 elif:      

else:

####	循环

while a<b:

for i in range(12): 

//2022-1/8

#	二、容器

//许多东西不一定要记下，**知道有这么一个用法**，**需要时进行查询即可**

```python
max()          min()
list(a)#将给定容器转换为列表	1
str(a)#将给定容器转换为字符串	0
tuple(a)#将给定容器转换为元组	1
set(a)#将给定容易转换为集合 1
字典转保留key舍弃value：1
都保留：0
sorted(容器,[reverse])排序(从小到大切回都变为列表对象)
```

###	列表

列表定义⬇⬇⬇

列表下标查询: 	   			a=a.index("")

列表插入n的位置：			a.insert(n," ")

尾部插入:							a.addend("")

列表元素删除：	  			del a[n]

取出(删除)后返回：			x=a.pop(n)

删除某元素在列表中的第一个匹配项:	a.remove()	

```python
my_list=[1,2,3,2,2]
my_list.remove(2)
print(my_list) #结果： [1,3,2,2]
```

清空列表内容：					a.clear()

统计指定元素数量:

```python
a=[1,1,1,2,3]

a.count(1)=3
```

统计所有元素: 						len(a)

for输出列表:

```python
a=[1,2,3,4,5]
for i in a:
    print{f"{i}"}
```

###	元组(tuple)

​	小括号,逗号,定义，单个定义需要写a=("1",)

index()        查询数据，返回下标

count()  	  统计某个

len()			统计所有

###	字符串

str="abcd"

a=str[2]=b

可用index()

```python
str="tom and jack"
a=index("and") #a=and
```

字符串中的**替换** *replace*

```python
str="tom and jack"
a=str.replace("and","or")#将原字符串中的"and"替换为"or"
```

**分割** *split*

```python
str="i can not do it too long time"
a=str.split(" ")#输出a得到   ['i','can','not','do','it','too','long','time']
#a为列表(list)类型
```

**去除**一些东西 *strip*

```python
str="tom and jack"
str.strip(and)#str="tom  jack"
```

***count()   len()都可以用***

###	序列切片

序列[起始下标:结束下标:步长]                 {小技巧：str[::-1]可使列表反转}

###	集合

{}     	类型名set         空集合set()         不允许重复，可以去重，不保证顺序

**添加**元素       					a.add("")
**移除**								 a.remove("")

**随机取**								a.pop()

**清空**									 a.clear()

**求差集**								 t=a.difference(b)```

在a集合中删除和b集合一样的，a变b不变     			      a.difference_update(b)

**并集**											a.union(b)

​							len()

###	字典

简单字典:     


a={"草药":1,"毒药":0}


空字典:     							   a={}         a=dict()

a={"草药":caoyao，"毒yao":duyao}

**嵌套**

| 种类   | dog  | cat  | chicken |
| ------ | ---- | ---- | ------- |
| eat    | 0    | 0    | 1       |
| no eat | 1    | 1    | 0       |

```python
a={							#用字典嵌套来表示上面的表格
    "eat"{
        "dog":0,
        "cat":0,
        "chicken":1
    }
    "no eat"{
        "dog":1,
        "cat":1,
        "chicken":0
    }
}


b=a["eat"]["chicken"]    # 取出a字典相当于表格二行四列的内容赋给b
```



嵌套取出⬆⬆⬆

常用操作字典

```python
a={"x":1，"y":0}
1: a[草药]  #获取key对应value值
2: a[x]=0   #更新/添加键值对
3: a.pop(key) #取出key对应value并删除此key键值对
4: a.clear()	 #清空
5: a.keys()    #获取全部key，可用for遍历
6: len(a)  #多少个元素
```

#	三、函数

###	定义函数

```python
def abc():
	#东西
class a:
   	def b():
        #东西
    def c():
        #东西
abc()#调用
a.b()#调用

global  #局部变全局
```

### 函数返回值

```python
def a()
	一堆东西
return 1，2
x,y=a()
```
###	参数传递
####	a**位置**参数

```python
def a(x,y,z)
	一堆东西
a(b,c,d)
```

####	b**关键字**参数

```python
def a(x,y,z)
	一堆东西
a(x="1",y="2",z="3")#顺序无所谓，可与位置参数混用
```

####	c**缺省**参数

```python
#默认参数
def a(x,y,z='1')#默认参数应该在最后
	一堆东西
a(1,2) #z有默认值，也可以传递参数覆盖默认值
```

####	d**不定长**参数

```python
#位置传递不定长
def a(*args)
	一堆东西
a(x,y,z)
#关键字传递
def a(**kargs)
	一堆东西
a(x='',b=,c=)#key=value
```

####	e**函数作为参数**传递

```python
def a(b)	#与传入数据不同，传入的是一种计算的逻辑
	c=b(x,y)
def b(x,y)
	return x+y
```

//2023-1-09

###	lambda匿名函数

定义方式          lambda 传入参数:东西

```python
 def abc(dog)
    result=dog(1,2)
    print(result)
 abc(lambda x,y:x+y)
```

#	四、文件操作

##	学习前看一眼这句话

“**例如此时已经在电脑D盘中存放了一个名为"测试.txt"的文件，编码格式为UTF-8,内容为"别卷辣"**”

###	打开

####	open函数()

```python
open(name,mode,encoding)
#name 目标文件的字符串(可包含文件具体路径)
#mode 设置访问模式，例如只读'r'，写入'w'，追加'a'
#encoding 编码格式，一般为UTF-8
```

####	文件读取

```python
read()读取
	f=open("D:\测试.txt","r",encoding="UTF-8")
    print(f.read(2))#"别卷"
    print(f.read(1))#"辣"
	#多次调用会接着
readlines()全部读
	lis=f.readlines()
read line()一次读一行
	line=f.readline()
```

####	for循环读取

```python
for line in f #f的东西是上边那个
	print(line)
```

####	关闭

```python
f.close()
```

####	单次读取后关闭

```python
with open("D:/测试.txt","r",encoding="UTF-8") as f:
```

###	写入

```python
#W模式r如果原有文件存在会清空#
f=open('新文件.txt','w',encoding="UTF-8") #不存在直接创建
f.write('行不行') #将内容写入了缓冲区
f.flush() #内容刷新
```

###	追加写入

把'w'换成'r',剩下同上⬆⬆⬆

#	五、异常

	###	常规异常

```python
try:
	可能出现异常的部分
except:
	上边出现异常的话就执行这里
```

###	捕获	指定/多个	异常

```python
try:
    ####
except NameError as e:  
    ###
    
NameError #变量未定义的异常
ZeroDivisionError #我忘了是个啥异常=-=
Exception #捕获所有异常
多个异常eg
except (NameError,ZeroDivisionError) as a:
```

###	异常的一些拓展语法

```python
try:
    print("2")
except Exception as e:
    print("bug")
else:
    print("no bug")
#2
#no bug
可以再加
finally:
    最后肯定会执行的地方，例如来个
    f.close()

```

异常可以传递，可以在后边在进行处理

#	六、python的模块和包

##	1模块

### 导入模块常用形式

```python
import 模块名
import 模块名 as 别名  #后续调用可以使用别名
from 模块名 import 类、变量、方法等 #导入模块中的某个功能
from 模块名 import * #导入全部功能，后续调用方便一些	
from 模块名 import 功能名 as 别名 #⬆
```

###	部分常用模块

```python
import time #时间模块
#再没啦，其他要用自己搜捏
```

###	自定义模块

创建一个python文件中写上函数，再另外一个python文件中可以用"import 文件名"的方式将其导入

eg:   文件1：abc.py

```python
def test(x,y)
	return x+y
```

文件2: 随便起名

```python
import abc
	abc.test(1,2) #导入了文件1作为模块 
```

```python
_all_变量
自定义模块中 #用*导入时只会导入_all_列表中对应的东西
_all_=['a']
def a()
	###
def b()
	###
```

## 2包

函数→模块→包

一个文件夹中有\_init_.py的一个文件，那么这个文件就是个包，文件里边的其他py就可以理解成这个包里的模组

**导入**

```python
import 包名.模组名
```

###	自定义包

就是弄个文件夹塞个\_init_.py的文件，然后再塞一堆模块

###	*第三方包

**常用包**:

```python
numpy						#科学计算
pandas						#数据分析
pyspark、apache——flink		#大数据计算
matplotlib、pyecharts		#图形可视化  (可以通过matlab简易实现一些需求)
tensorflow					#人工智能
mediapipe					#人体识别
```

**pip安装第三方包**

```python
win+r	→	cmd  #打开终端
pip install 包名		#终端执行，安装第三方包
pip install -i https://pypi.tuna.tsinghua.edu.cn/simple 包名称	#如果上边的安装失败的话(从国外很慢，有加速器有时候也不一定稳定)，可以尝试通过这个清华大学开源镜像网站安装第三方包。//还得是清华
//*也可以直接在pycharm中安装，不过用第一种方法都安不上这种直接也悬，清华开源镜像网站目前来说是对于初学者来说国内最稳的一个办法了，也可以在pycharm中将options改为上边清华开源镜像网站进行直接安装
```

//2023-1-10  16:46    python基础部分滴学习结束啦