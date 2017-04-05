---
title: Ietrator
keywords: sample
summary: "Python Iterator"
sidebar: python_sidebar
permalink: python_iterator.html
folder: python
---

### 迭代相关概念
1. 可迭代对象(iteable):可用于for循环的对象
2. 迭代器(Iterator):可以被next()函数调用并不断返回下一个值的对象
### 内置函数:iter()可将所有的Iterable转变为Iterator
1. 内置函数iter()仅仅是调用了可迭代对象的__iter()方法[可迭代对象内部一定存在方法iter__()]
2. 内置函数next()仅仅是调用了迭代器的__next()方法[可迭代对象内部一定不存在方法next__(),但Itrator中一定存在这个方法]
3. for循环内部事实上就是先调用iter()把Iterable变成Iterator在进行循环迭代的
4. from collections import Iterator, Iterable 集合中方法：iterable需要包含有__iter()方法用来返回iterator，而iterator需要包含有next__()方法用来被循环

{% include links.html %}
