1.高级序列赋值语句模式:cat:
======
[全文](https://blog.csdn.net/gavin_john/article/details/49906095)


2.generator的yield中执行顺序:cat:
=======
```py
def function():
	pass test():
	for i in range(5):
		print('i=',i)
		yield i 
	print('ok')
>>>for b in test():
···  pass
i= 0
i= 1
i= 2
i= 3
i= 4
ok
```
很简单，要在循环内执行完再进行最后一步print<br>
***再使用时，用b=test(),再用next(b)会递增，可是直接next(test())不会变***:sob:

3.装饰器的实战用法:cat:
=====
装饰器实在是挺好的一个方法，但是深入一看发现自己其实并不懂，现在看[这一篇](https://blog.csdn.net/xiangxianghehe/article/details/77170585)<br>
再做三个练习<br>
		1.请编写一个decorator，能在函数调用的前后打印出'begin call'和'end call'的日志。
		2.编写一个decorator，不管有无参数输入都可以输出
		3.编写一个decorator，可以输出函数执行的时间
[写在这里](https://github.com/justabugg/test/blob/master/try/5.md)

4.python作为脚本语言的特殊性:cat:
======
很多编程语言需要一个入口如C，C++以及完全面对对象的JAVA，都必须要有一个main或者含main方法的主类作为入口。<br>
python不像编译型语言那样编译成二进制在运行，是动态的的逐行解释运行也就是从脚本第一行开始

5.面对对象编程中的获取对象信息:cat:
=======
暂时还没有遇到实际问题，但有人举例后期编写一个自己的方法模块，再根据用户输入方法调用，如果一直用if判断太繁琐，所以用获取判断是否存在，不存在再自己定义。
