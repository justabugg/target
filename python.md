第一个 一个好玩的循环  
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
同理  
  

第二个 tuple虽然是不变对象，但试试把(1, 2, 3)和(1, [2, 3])放入dict或set中，并解释结果。  
  

第三个 set创建要用一个list作为输入集合可是直接在交互式输入a={1,2,1,1,1}也能建一个{1，2}的set  
  




