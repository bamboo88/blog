---
title: python
keywords: sample
summary: "Python Scope"
sidebar: python_sidebar
permalink: python_scope.html
folder: python
---


* Variable scope 变量的作用域就是变量的命名空间
* 变量在赋值时就决定了哪些范围的对象可以访问这个变量,这个范围就是命名空间
* if/elif/else、try/except/finally、for/while语句并不会产生新的作用域(python没有块级作用域)
* def、class、lambda等语句会产生作用域

#### 变量查找遵循LEGB法则:
* Local(本地作用域)
* Enclosing(函数内部与内嵌函数之间)
* Global(全局作用域)
* Build-in(内置作用域)

1. 块级作用域(python没有)
```
if 2 == 2:
    name = "hello word"
print name

for a in xrange(5):
    h = a
print h
```

输出内容：

hello word
9

解释：在Java/C#中,执行上面的代码会提示name,age没有定义,但在Python中可以执行成功,这是因为在Python中是没有块级作用域的,代码块里的变量,外部可以调用,所以可运行成功;

2. 局部作用域和全局作用域
```
a = 10 # 全局作用域
def fun():
    a = 5 # 局部作用域
    return a
def fun1():
    global a # 如果需要对全局变量a的值进行修改(重新创建变量),需要使用global进行声明
    a = a + 5
    return a

print a
print fun()
print fun1()
```

3. 闭包closure(如果在一个内部函数里,对在外部函数内(但不是在全局作用域)的变量进行引用,那么内部函数就被认为是闭包(closure))
```
name = "key"
def f1():
    name = "helo"
    def f2():
        name = "word"
        print(name)
    f2()
f1()

def f3():
    print(name)
 
def f4():
    name = "eric"
    f3()
 
f3()
```

{% include links.html %}
