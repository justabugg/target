第一个  Mixin
======

解答
----
参考[1](http://www.cnblogs.com/xybaby/p/6484262.html)
参考[2](https://www.cnblogs.com/aademeng/articles/7262520.html)
注意菱形继承，对于计算机来说很复杂
![images](https://images2015.cnblogs.com/blog/1089769/201703/1089769-20170301150214126-933245747.png)
其实涉及到了代码/功能的复用，不可能每个东西都再写一遍某种功能，如果定义在一个类的话有些也不一定有这项功能，所以就出现了mixin<br>
在定义时记得加mixin，只是标记一下告诉人们这个类是为了实现功能而定的，而不是作为单一父类继承的。


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

解答
---
我像个憨批， 明明是
```
s！=0  
```

第四个 logging
=========
文中讲的其实比较浅，google上有更全面的，貌似挺有用但是暂时看不懂，mark


第五个
