---
title: python内置函数
keywords: sample
summary: "Python Build-in Function"
sidebar: python_sidebar
permalink: python_build-in_function.html
folder: python
---
#### map()
map()函数接收两个参数,一个是函数,一个是序列(List或Tuple),map将传入的函数依次作用到序列的每个元素,并把结果作为新的list返回
官方解释:
```
def map(function, sequence, *sequence_1):
    """
    map(function, sequence[, sequence, ...]) -> list
    Return a list of the results of applying the function to the items of the argument sequence(s).  
    If more than one sequence is given, the function is called with an argument list consisting of the corresponding 
    item of each sequence, substituting None for missing values when not all sequences have the same length.  
    If the function is None, return a list of the items of the sequence(or a list of tuples if more than one sequence).
    """
    return []
```
实战演练:
```
将传入的list依次加3返回一个新的列表：
print map(lambda x:x+3,[1,2,3])
print map(lambda x:x+3,(1,2,3))
print map(lambda x:x+3,{1,2,3})
print map(str, [1, 2, 3, 4, 5, 6, 7, 8, 9])   int --> str
print map(int,['1', '2', '3', '4', '5', '6', '7', '8', '9']) str --> int
[4, 5, 6]
['1', '2', '3', '4', '5', '6', '7', '8', '9']
[1, 2, 3, 4, 5, 6, 7, 8, 9]
```
#### reduce()
reduce 核心理念:前一次的运算结果结果，作为后一次运算的输入
reduce 把一个函数作用在一个序列[x1, x2, x3…]上,这个函数必须接收两个参数,reduce把结果继续和序列的下一个元素做累积计算
reduce(f, [x1, x2, x3, x4]) = f(f(f(x1, x2), x3), x4)  
官方解释:
```
def reduce(function, sequence, initial=None): 
    """
    reduce(function, sequence[, initial]) -> value
    Apply a function of two arguments cumulatively to the items of a sequence,from left to right, 
    so as to reduce the sequence to a single value.
    For example, reduce(lambda x, y: x+y, [1, 2, 3, 4, 5]) calculates ((((1+2)+3)+4)+5).  
    If initial is present, it is placed before the items of the sequence in the calculation, 
    and serves as a default when the sequence is empty.
    """
    pass
```
实战演示:
```
print reduce(lambda x,y:x+y,[1,2,3,4,5])  #一个序列求和
print reduce(lambda x,y:x*10+y,[1,2,3,4]) #将[1,2,3,4] --> 1234
15
1234
```
#### filter()
filter()把传入的函数依次作用于每个元素,然后根据返回值是True还是False决定保留还是丢弃该元素,True保留,False丢弃
官方解释:
```
def filter(function_or_none, sequence): 
    """
    filter(function or None, sequence) -> list, tuple, or string
    Return those items of sequence for which function(item) is true.  
    If function is None, return the items that are true.  
    If sequence is a tuple or string, return the same type, else return a list.
    """
    pass
```
实战演练:
```
print filter(lambda x:x%2==0,[2,4,6,8,11])  #找出序列中的所有偶数
print filter(lambda x:x and x.strip(), ['A', '', 'B', None, 'C', '  ','A B C']) #清除一个序列中的空字符串
[2, 4, 6, 8]
['A', 'B', 'C', 'A B C']
```
{% include links.html %}
