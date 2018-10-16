第一个  Mixin
======

#### 解答
参考一[重要的笔记C3](https://kevinguo.me/2018/01/19/python-topological-sorting/#%E4%B8%80%E4%BB%80%E4%B9%88%E6%98%AF%E6%8B%93%E6%89%91%E6%8E%92%E5%BA%8F)
参考[第二个参考](https://www.cnblogs.com/aademeng/articles/7262520.html)<br>
其实涉及到了代码功能的复用，不可能每个东西都再写一遍某种功能，如果定义在一个类的话有些也不一定有这项功能，所以就出现了mixin<br>
在定义时记得加mixin，只是标记一下告诉人们这个类是为了实现功能而定的，而不是作为单一父类继承的。
https://www.liaoxuefeng.com/discuss/001409195742008d822b26cf3de46aea14f2b7378a1ba91000/001535898869217a41f5fded4f846079504068ab308def9000

第二个 metaclass
==========
参考[1](http://blog.jobbole.com/21351/)


第三个 assert
=======
不知道为啥 我这个代码老不报AssertionError
```
def ass(n):
    s=int(n)
    assert n != 0,"mpmpmp"
    return 10/s

def main():
    ass('0')
main()
```

#### 解答
我像个憨批， 明明是
```
s！=0  
```

第四个 logging
=========
文中讲的其实比较浅，google上有更全面的，貌似挺有用但是暂时看不懂，mark


第五个  super()
=========
#### 解答
首先浅显的来说是调用父类的方法，当单继承时<br>
```
class A:
  def __init__(self):
    self.n = 2 
  def add(self, m):
    print('self is {0}@A.add'.format(self)) 
    self.n += m
class B(A):
    def __init__(self): 
      self.n = 3 
    def add(self, m):
      print('self is {0}@B.add'.format(self))
super().add(m) 
self.n += 3
```
第六个 C3算法
===========
 

第七个 strip()
=========
在IO编程的读文件的时候，迭代调用readline的时候删除末尾的\n<br>
#### 解答
```
for line in f.readlines():
    print(line.strip()) # 把末尾的'\n'删掉
```
也可以这样
```
while True:
  s=f.readline()
  if s==''
  print(f.strip())
```


第八个 try
====
这个在读文件的时候用了try....finally，我在想如果写一个会报错的文件，再结合之前的文件调试写一个try..except..finally怎么样，可是现在IO找不到路径(明明是对的啊)
#### 解答
emmm玄幻 其实路径就是 /usres/assboy/python project/IO.py<br>
其次这个就是读文件！并不是运行文件 所以就是显示了我的代码而已


第九个 os模块练习
========
1.利用os模块编写一个能实现dir -l输出的程序。<br>
2.编写一个程序，能在当前目录以及当前目录的所有子目录下查找文件名包含指定字符串的文件，并打印出相对路径。


第十个 class
====
#### 解答
JSON进阶的时侯讲到了class的实例无法直接用dump转换，除了用了slots的class的实例自带一个__dict__，就是一个dict可以直接用<br>
再把dict转成class
```
def dict2student(d):
    return Student(d['name'], d['age'], d['score'])
```

第十个 os.getpid和os.getppid
======




第十一个 p.close()
=======


第十二个 时间
=========
在写进程池的时候用了一个time,random模块<br>
#### 解答
大概是这样实现
```python
import time random
start=time.time()
time.sleep(random.random())
end=time.time()
print(end-start)
```


第十三个 子进程控制输入输出
======









[question1](https://www.liaoxuefeng.com/discuss/001409195742008d822b26cf3de46aea14f2b7378a1ba91000/00151937911313973d2490e71dc4f919b7f71c1616f3f8d000?page=1)
(GIL)(http://cenalulu.github.io/python/gil-in-python/)//.0