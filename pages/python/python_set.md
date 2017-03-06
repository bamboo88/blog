---
title: python
keywords: sample
summary: "Python Set"
sidebar: python_sidebar
permalink: python_set.html
folder: python
---

#### 官方文档：

#### https://docs.python.org/2.7/tutorial/datastructures.html
#### https://docs.python.org/3.5/tutorial/datastructures.html

### 列表非常适合利用顺序和位置定位某一元素（元素的顺序或内容经常发生改变时）

### 列表常见操作：

1. 增加(单个元素、多个元素、列表): append(),extend(),insert(),+ 加号
2. 删除(指定位置、指定元素)
3. 修改(排序、去重复(顺序问题)、某个元素)
4. 查找()

### 列表操作实例
一、使用方括号[]或list()创建空列表
* empty_list = [ ]
* empty_list = list()

二、使用list()将其他数据类型转换成列表
* 将字符串(引号包含的内容)转换为列表
* 将元祖转换为列表
* 使用split()可以根据分隔符将字符串切割成由若干子串组成的列表

三、使用join()将列表转换为字符串(join()是split()的逆过程)
* 将列表students转换为字符串：''.join(students)

四、给列表添加元素：使用extend() 或 += 合并列表(a[len(a):]=L)
* append()在原列表中追加单个元素
* insert(index,value)在指定位置插入元素
* extend():将列表添加到列表
* 加号,将两个列表相加得到新的list对象

五、删除元素
* del删除指定位置的元素(不带返回值)
* remove()删除具有指定值的第一个元素
* 使用pop()获取并删除指定位置的元素

六、列表排序
* sort():对原列表进行排序,会改变原列表的内容
* sortd():返回排好序的列表副本，原列表内容不变

七、使用reverse()对列表进行倒序排列


{% include links.html %}
