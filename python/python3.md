1.高级序列赋值语句模式:cat:
======
[全文](https://blog.csdn.net/gavin_john/article/details/49906095)


2.generator的yield中执行顺序
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

