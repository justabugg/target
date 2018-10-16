第一个 一个好玩的循环:cat:
===
```python
n=1   
while n<=100:  
  if n>10:  
    break  
  print(n)  
  n=n+1  
print('end')   
在while循环里嵌套了一个if循环和break
n = 0  
while n < 10:  
    n = n + 1  
    if n % 2 == 0:  
        continue  
    print(n)  
```  
  

第二个:cat:
====
tuple虽然是不变对象，但试试把(1, 2, 3)和(1, [2, 3])放入dict或set中，并解释结果<br>
#### 解
运行后第一个可以加，第二个不可以：因为第一个中三个都是不变的对象，第二个中只有1是不变的，其中指向list不会变，可是list中的对象可以变


第三个:cat:
====
set创建要用一个list作为输入集合可是直接交互式输入a={1在,2,1,1,1}也能建一个{1，2}的set  
#### 解
s=set([1],[2]）这才叫把list传入了set，是错的，可变对象<br>
正确做法 s=set([2,4,5,6,6])没毛病和直接传一样

第四个:cat:
===
代码的最优解 这样说不准确 应该有相对最优解 反正现在我的水平 代码不太好看<br>
以下函数允许计算两个数的乘积，请稍加改造，变成可接收一个或多个数并计算乘积：  


第五个 尾递归:cat:
===
#### 解
有了新的领悟，在递归的时候因为栈的先入后出，在调用函数后不能及时返回导致栈溢出，尾递归则是每次及时返回，出栈<br>
[我的尝试](https://github.com/justabugg/test/blob/master/try/1.md)


  

第六个  汉诺塔 :cat:
====
他喵的搞半天我还以为多复杂 就一个简单的递归函数 重述一下  
(妈的 代码打一半忘了我怎么想的了 重新来了半天，老子的思想深奥起来自己都不懂)  
现在想通了  
第一步 把a上的n-1个盘子通过c移到b  
第二部 把a的第n个盘子移到c  
第三步 把b上的n-1个盘子通过a移到c，过程不管 因为这是下一层循环的问题  
代码实现  
```py
def move(n,a,b,c):  
  if n==1:  
    print(a,'to',c)
  else:
    move(n-1,a,c,b)  
    move(1,a,b,c)
    move(n-1,b,a,c)
```

第七个:sob:
====
isinstance！


第八个 斐波拉契  :cat:
===
斐波拉契数列 后一个等于前两个数之和<br>
首先定义了a，b来加起来作为第三个输出，这样就是a，b，a+b 达到了目的<br>
其次 定义函数的执行次数 需要用一个n来协调<br>
这是一般的方法
```py
def fib(max):
  n,a,b=0,0,1
  while n<max:
    return b
    a=b
    b=a+b
  return'ok'
```
这是generator的方法
```py
def fib(max):
  while n<max:
    yield b
    a=b
    b=a+b
  return'ok'
```

第九个 杨辉三角:cat:
===
杨辉三角问题<br>
(https://github.com/justabugg/test/blob/master/try/2.md)

第十个 reduce和map结合的问题:cat:
======
用这个方法定义一个把str转为int的函数<br>
首先要把str转成单独的数字，再用x\*10＋y变成一整个数<br>
```py
from functools import reduce
def fn(x,y):
  return x*10+y

def char(x):
  l={'0': 0, '1': 1, '2': 2, '3': 3, '4': 4, '5': 5, '6': 6, '7': 7, '8': 8, '9': 9}
  return l[x]

reduce(fn,map(char,'1233213'))
```

第十一个 埃氏筛法:cat:
=====
计算素数的一个方法是埃氏筛法，它的算法理解起来非常简单：

首先，列出从2开始的所有自然数，构造一个序列：

2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, ...

取序列的第一个数2，它一定是素数，然后用2把序列的2的倍数筛掉：

3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, ...

取新序列的第一个数3，它一定是素数，然后用3把序列的3的倍数筛掉：
现在实现
```py
#先构造一个从3开始的奇数序列
def jishu():
  n=1
  while True:
    n=n+2
    yield n

#定义一个筛选函数
def choice():
  return lambda x:x%n>0
#最后定义生成器
def aishi():
  yield 2
  while True:
    n=next(jishu)
    yield n
    jishu=filter(choice,jishu)
#最后因为输出是无限的generation
for b in aishi():
  if b <1000:
    print(b)
  else:
    break
```


第十二个 回文数:cat:
=====
```py
def huiwen(x):
  n=str(x)
  if n[:]==n[::-1]
    return n
```

第十三个 冒泡排序:sob:
====


第十四个 闭包引用循环变量:cat:
=====
用一个函数绑定参数
```py
def count():
    def f(j):
        def g():
            return j*j
        return g
    fs = []
    for i in range(1, 4):
        fs.append(f(i)) # f(i)立刻被执行，因此i的当前值被传入f()
    return fs

>>> f1, f2, f3 = count()
>>> f1()
1
>>> f2()
4
>>> f3()
9

```

第十五个 nonloca和global:sob:
========
[参考](https://blog.csdn.net/cn_wk/article/details/52723269)
[进一步参考](https://blog.csdn.net/xCyansun/article/details/79672634?utm_source=copy )
LEGB原则，当引用一个变量的时候，对这个变量的搜索是按找本地作用域(Local)、嵌套作用域(Enclosing function locals)、全局作用域(Global)、内置作用域(builtins模块)的顺序来进行的。
    但是在函数内部却是：“当在函数中给一个变量名赋值是(而不是在一个表达式中对其进行引用)，Python总是创建或改变本地作用域的变量名，除非它已经在那个函数中被声明为全局变量. ”
```py
x = 99
def func():
    x = 88   #按照原则 创建了一个本地作用域的标量
func()
print(x)     #输出99
```
改为
```py
x=99
def func():
    global x
    x=88
func()
print(x) 
```
用nonlocal可以改嵌套作用域中的变量
```py
def func():
    count = 1
    def foo():
        count = 12
    foo()
    print(count)
func()    #输出1
```
改为
```py
def func():
    count = 1
    def foo():
        nonlocal count
        count = 12
    foo()
    print(count)
func()     #输出12
```
***这里要注意，使用global关键字修饰的变量之前可以并不存在，而使用nonlocal关键字修饰的变量在嵌套作用域中必须已经存在。
第一，两者的功能不同。global关键字修饰变量后标识该变量是全局变量，对该变量进行修改就是修改全局变量，而nonlocal关键字修饰变量后标识该变量是上一级函数中的局部变量，如果上一级函数中不存在该局部变量，nonlocal位置会发生错误（最上层的函数使用nonlocal修饰变量必定会报错）。
第二，两者使用的范围不同。global关键字可以用在任何地方，包括最上层函数中和嵌套函数中，即使之前未定义该变量，global修饰后也可以直接使用，而nonlocal关键字只能用于嵌套函数中，并且外层函数中定义了相应的局部变量，否则会发生错误***



第十六个 返回函数之计数器:cat:
=====
即每次调用输出＋1<br>
根据要求，返回一个计数函数<br>
```py
def creatcounter():
  n=0
  def counter（）： #根据要求 这是计数函数
    n=n+1
    return n
  return

#看起来没错 但是像上面的十五最后一个例子  内部counter修改了n，这样会报错所以要加上nonlocal
 def creatcounter():
  n=0
  def counter（）： #根据要求 这是计数函数
    nonlocal n
    n=n+1
    return n
  return
  ```
这里涉及到从函数内部修改外部函数局部变量，一般三种：1把外部变量变成可变变量，2nonlocal，3global

第十七个 装饰器decoorator:cat:
===========
简单的装饰器容易理解 这里写一下三层嵌套的自定义装饰器<br>
```py
def log(text):
    def decorator(func):
         @functools.wraps(func)  #这一步是改函数的签名_name_
        def wrapper(*args, **kw):
            print('%s %s():' % (text, func.__name__))
            return func(*args, **kw)
        return wrapper
    return decorator

@log('execute')
def now():
  print('2018.9.11')  #这里相当于 now = log('execute')(now)
>>> now()
execute now():
2015-3-25
```

第十八个 if __name__=='__main__':cat: :dog:
-----------
[参考](https://blog.csdn.net/yjk13703623757/article/details/77918633/)
其实就是简单的认为，一个模块被导入时不运行此结构以下的代码

第十九个 file like object:sob:
-----------
鸭子类型，知道啥个意思，但是感觉有深入的用法，先码着

第二十个
--------
枚举类最后的习题