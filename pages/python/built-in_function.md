---
title: python内置函数
keywords: sample
summary: "Python Build-in Function"
sidebar: python_sidebar
permalink: python_build-in_function.html
folder: python
---

#### map、reduce、filter
### map 对每个序列使用function进行操作
官方解释:
```
def map(function, sequence, *sequence_1):
    """
    map(function, sequence[, sequence, ...]) -> list
    Return a list of the results of applying the function to the items of
    the argument sequence(s).  If more than one sequence is given, the
    function is called with an argument list consisting of the corresponding
    item of each sequence, substituting None for missing values when not all
    sequences have the same length.  If the function is None, return a list of
    the items of the sequence (or a list of tuples if more than one sequence).
    """
    return []
```
实战演练:
```
print map(lambda x:x+3,[1,2,3])
print map(lambda x:x+3,(1,2,3))
print map(lambda x:x+3,{1,2,3})

[4, 5, 6]
```


{% include links.html %}
