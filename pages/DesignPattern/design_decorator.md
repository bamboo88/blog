---
title: DesignPattern
keywords: sample
summary: "DesignPattern"
sidebar: python_design
permalink: design_decorator.html
folder: DesignPattern
---

### 装饰器是什么
装饰器是为已经存在的对象(函数、方法、类)添加额外的功能，提升代码的可读性。
装饰器是设计模式的一种，被用于有切面需求的场景(Java中面向切面编程)。

### 装饰器适用场景
* 插入日志
* 权限控制
* 性能测试?
* 事务处理?

### 装饰器模式定义
* 装饰器是单参数的函数
* 装饰器的参数是函数
* 装饰器返回的新的函数与经由参数传入的原函数名称相同

### 实战演练
<pre><code>#-*-coding:utf-8-*-
#functools.wraps会将经过装饰器修饰的函数的__name__属性修改为与原函数相同的名字，否则一些需要依赖函数签名的代码就会出粗
import functools

#装饰器传入参数仅仅是函数
def decorator_test(function):
    @functools.wraps(function)
    def wrapper(*args,**kwargs):
        args = [float(arg) for arg in args]
        return float(function(*args,**kwargs))
    return wrapper
 
#装饰器需要传入其它参数
def log(text):
    def decorator(func):
        @functools.wraps(func)
        def wrappers(*args,**kwargs):
            do something
            return func(*args,**kwargs)
        return wrappers
    return decorator  

@decorator_test
def test(a,b,c):
    return (a-b)/c

if __name__ == '__main__':
    t = test('23',12,'5')
    print t</code></pre>

{% include links.html %}
