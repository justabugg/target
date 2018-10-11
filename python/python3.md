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

3.装饰器的实战用法
=====
装饰器实在是挺好的一个方法，但是深入一看发现自己其实并不懂，现在看[这一篇](https://blog.csdn.net/xiangxianghehe/article/details/77170585)<br>
再做三个练习<br>
		1.请编写一个decorator，能在函数调用的前后打印出'begin call'和'end call'的日志。
		2.编写一个decorator，不管有无参数输入都可以输出
		3.编写一个decorator，可以输出函数执行的时间
写在test里