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
<code><pre>#-*-coding:utf-8-*-
import functools

def decorator_test(function):
    @functools.wraps(function)
    def wrapper(*args,**kwargs):
        args = [float(arg) for arg in args]
        return float(function(*args,**kwargs))
    return wrapper

@decorator_test
def test(a,b,c):
    return (a-b)/c

if __name__ == '__main__':
    t = test('23',12,'5')
    print t</code></pre>

{% include links.html %}
