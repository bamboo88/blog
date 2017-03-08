---
title: classMethod
keywords: sample
summary: "Python Class Method"
sidebar: python_sidebar
permalink: python_class_method.html
folder: python
---

### python类中普通方法、静态方法、类方法的区别
#### 类是一组具有相同属性和相同操作的对象的集合。
##### common method
    描述一个类的行为
##### @staticmethod
    @staticmethod means: when this method is called, we don't pass an instance of the class to it (as we normally do with methods). This means you can put a function inside a class but you can't access the instance of that class (this is useful when your method does not use the instance).
    staticmethod 并不是因为不想创建实例才声明的，而是声明该方法不会更改实例本身的数据。基本上和一个全局函数差不多。

##### @classmethod
    @classmethod means: when this method is called, we pass the class as the first argument instead of the instance of that class (as we normally do with methods). This means you can use the class and its properties inside that method rather than a particular instance.
    classmethod 并不是因为不想创建实例才声明的，而是为了实现对类本身的操作（传入cls之后就可以对自身的属性和方法进行操作）。比如对传入参数的检查，过滤，修改。

#### 如何调用它们
1. 一般方法使用类生成的对象调用
2. 静态方法用类或者类的实例直接调用
3. 类方法用类或者类的实例直接调用(类当参数传入方法) 

#### 示例演示
##### 实例代码：
<pre><code>#-*-coding:utf-8-*-
"""
Data:2017-3-8
Author:zhuzi
"""
class Bamboo:
    def __init__(self):
        print "Initial construction method"

    @staticmethod
    def callStaticmethod():
        # 静态方法可以不用传入参数
        print "this is staticmethod"

    @classmethod
    def callClassmethod(cls):
        # 类方法的第一个参数必须类对象本身
        print "This is classmethod"

    def callCommonmethod(self):
        # 普通方法的第一个参数必须是self,表示实例对象本身
        print "This is common method"

if __name__ == '__main__':
    print "使用类对象调用"
    Bamboo.callStaticmethod()
    Bamboo.callClassmethod()

    print "使用实例对象调用"
    boo = Bamboo()
    boo.callStaticmethod()
    boo.callClassmethod()
    boo.callCommonmethod()
</code></pre>

#### 运行结果：
<pre><code>使用类对象调用
this is staticmethod
This is classmethod
使用实例对象调用
Initial construction method
this is staticmethod
This is classmethod
This is common method</code></pre>
