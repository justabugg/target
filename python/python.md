第一个 一个好玩的循环<br> 
===
```
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
  

第二个
====
 tuple虽然是不变对象，但试试把(1, 2, 3)和(1, [2, 3])放入dict或set中，并解释结果<br>


第三个 
====
set创建要用一个list作为输入集合可是直接在交互式输入a={1,2,1,1,1}也能建一个{1，2}的set  


第四个
===
 代码的最优解 这样说不准确 应该有相对最优解 反正现在我的水平 代码不太好看  
以下函数允许计算两个数的乘积，请稍加改造，变成可接收一个或多个数并计算乘积：  


第五个 尾递归
===
尾递归问题  
  

第六个  汉诺塔
====
他喵的搞半天我还以为多复杂 就一个简单的递归函数 重述一下  
(妈的 代码打一半忘了我怎么想的了 重新来了半天，老子的思想深奥起来自己都不懂)  
现在想通了  
第一步 把a上的n-1个盘子通过c移到b  
第二部 把a的第n个盘子移到c  
第三步 把b上的n-1个盘子通过a移到c，过程不管 因为这是下一层循环的问题  
代码实现  
```
def move(n,a,b,c):  
  if n==1:  
    print(a,'to',c)
  else:
    move(n-1,a,c,b)  
    move(1,a,b,c)
    move(n-1,b,a,c)
```

第七个
====
isinstance！


第八个 斐波拉契
===
斐波拉契数列 后一个等于前两个数之和<br>
首先定义了a，b来加起来作为第三个输出，这样就是a，b，a+b 达到了目的<br>
其次 定义函数的执行次数 需要用一个n来协调<br>
这是一般的方法
```
def fib(max):
  while n<max:
    return b
    a=b
    b=a+b
  return'ok'
```
这是generator的方法
```
def fib(max):
  while n<max:
    yield b
    a=b
    b=a+b
  return'ok'
```

第九个 杨辉三角
===
杨辉三角问题<br>


第十个 reduce和map结合的问题
======
用这个方法定义一个把str转为int的函数<br>
首先要把str转成单独的数字，再用x\*10＋y变成一整个数<br>
```
from functools import reduce
def fn(x,y):
  return x*10+y

def char(x):
  l={'0': 0, '1': 1, '2': 2, '3': 3, '4': 4, '5': 5, '6': 6, '7': 7, '8': 8, '9': 9}
  return l[x]

reduce(fn,map(char,'1233213'))
```

第十一个 埃氏筛法
=====
计算素数的一个方法是埃氏筛法，它的算法理解起来非常简单：

首先，列出从2开始的所有自然数，构造一个序列：

2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, ...

取序列的第一个数2，它一定是素数，然后用2把序列的2的倍数筛掉：

3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, ...

取新序列的第一个数3，它一定是素数，然后用3把序列的3的倍数筛掉：
现在实现
```
先构造一个从3开始的奇数序列
def jishu():
  n=1
  while True:
    n=n+2
    yield n

定义一个筛选函数
def choice():
  return lambad x:x%n>0
最后定义生成器
def aishi():
  yield 2
  while True:
    n=next(jishu)
    yield n
    jishu=filter(choice,jishu)
最后因为输出是无限的generation
用for b in aishi():
  if b <1000:
    print(b)
  else:
    break
```


第十二个 回文数
=====


第十三个 冒泡排序
====
