---
title: 二分查找法
keywords: sample
summary: "python 二分查找法"
sidebar: python_sidebar
permalink: python_binary_search.html
folder: python
---

### 二分查找法必须是针对有序序列才有效
#### 算法查找过程(查找列表为list[first,...,last])
1. 确定列表中间位置m
2. 将需要查找的值T和list[m]比较，如果相等，则直接返回；如果不相等，继续二分查找。
   * 如果 T > list[m] , 则下次查找区间为list[m+1,....,last]
   * 如果 T < list[m] , 则下次查找区间为list[first,...,m-1]

#### 代码实现如下：
<pre><code>#-*-coding:utf-8-*-

def binarySearch(list,t):
    first = 0
    last = len(list)-1
    while first < last:
        mid = (first+last)/2
        if list[mid] < t:
            first = mid + 1
        elif list[mid] > t:
            last = mid -1
        else:
            print "The value index is: {}".format(list.index(t))
            return list[mid]

if __name__ == "__main__":
    print binarySearch([1,2,3,34,56,57,78,87],57)</code></pre>

#### 执行结果如下：
<pre><code>
The value index is: 5
57</code></pre>
{% include links.html %}
