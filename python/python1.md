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
在讨论区有个人用了nonloca，谷歌了一下<br>
**首先，要明确 nonlocal 关键字是定义在闭包里面的。**<br>
```
请看以下代码：

x = 0
def outer():
    x = 1
    def inner():
        x = 2
        print("inner:", x)

    inner()
    print("outer:", x)

outer()
print("global:", x)

# inner: 2
# outer: 1
# global: 0
```
加入nonlocal<br>
```
x = 0
def outer():
    x = 1
    def inner():
        nonlocal x
        x = 2
        print("inner:", x)

    inner()
    print("outer:", x)

outer()
print("global:", x)

结果

#inner: 2
#outer: 2
#global: 0
```
加了nonlocal就说明该变量在整个大函数里有效<br>
**global**
```
x = 0
def outer():
    x = 1
    def inner():
        global x
        x = 2
        print("inner:", x)

    inner()
    print("outer:", x)

outer()
print("global:", x)

结果

#inner: 2
#outer: 1
#global: 2
```

global 是对整个环境下的变量起作用，而不是对函数类的变量起作用。

接nonlocal
------
```
def fun1():
    x = 5
    def fun2():
        x *= 2
        return x
    return fun2()
```
**报错** UnboundLocalError: local variable 'x' referenced before assignment<br>
对于fun1函数，x为局部变量。对于fun2函数，x为非全局的的外部变量。当在fun2中对x进行修改时，会将x视为fun2的局部变量，屏蔽掉fun1中对x的定义；如果仅仅在fun2中对x进行读取，则不会出现这个错误。

**修改后**<br>
```
def fun1():
    x = 5
    def fun2():
        nonlocal x
        x *= 2
        return x
    return fun2()
 
fun1()
Out[14]: 10
```

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

第十八个 if __name__=='__main__'
-----------
google


第十九个
-----------
file like object


第二十个
--------
枚举类最后的习题