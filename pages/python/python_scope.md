---
title: python
keywords: sample
summary: "Python Scope"
sidebar: python_sidebar
permalink: python_scope.html
folder: python
---


1. 块级作用域
<pre><code>if 2 == 2:
    name = "hello word"
print name

for a in xrange(5):
    h = a
print h</code></pre>
输出内容：
hello word
9
解释：在Java/C#中,执行上面的代码会提示name,age没有定义,但在Python中可以执行成功,
这是因为在Python中是没有块级作用域的,代码块里的变量,外部可以调用,所以可运行成功;

2. 局部变量和全局变量
<pre><code>
a = 10 # 全局变量
def fun():
    a = 5 # 局部变量
    return a
def fun1():
    global a # 如果需要对全局变量a的值进行更改，需要使用global进行声明
    a = a + 5
    return a

print a
print fun()
print fun1()</code></pre>


{% include links.html %}
