第一个 
===
一个好玩的循环<br>  
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


第五个 
===
尾递归问题  
  

第六个 
====
汉诺塔问题
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


第八个
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

第九个
===
杨辉三角问题<br>


