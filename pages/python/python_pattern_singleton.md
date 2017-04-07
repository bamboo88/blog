---
title: singleton
keywords: sample
summary: "Python Singleton"
sidebar: python_sidebar
permalink: python_pattern_singleton.html
folder: python
---

### 单例模式
## 应用场景

1. Windows的Task Manager（任务管理器）就是典型的单例模式
2.  Windows的Recycle Bin（回收站）一直维护着一个实例
3.  网站的计数器
4.  应用程序日志应用，共享的日志文件一直处于打开状态，因此只用一个实例去操作，否侧内容不好追加。
5.  Django配置文件由单例模式完成共享资源的读取
6.  数据库连接池的设计一般也是采用单例模式。使用数据库连接池主要是节省打开或关闭数据库连接所引起的效率损耗，使用单例模式来维护，就可以大大降低这种损耗。
7.  多线程的线程池的设计一般也是采用单例模式，这是由于线程池要方便对池中的线程进行控制。
8.  操作系统的文件系统是大的单例模式实现，一个操作系统只能有一个文件系统。
9.  Django 的HttpRequest 和 HttpResponse 也是单例模式？？？

## 应用场景总结

1. 资源共享的情况下，公共的配置文件、日志记录等
2. 控制资源的情况下，方便资源之间的通信，线程池、连接池、文件系统等

## Python 创建单例模式的4中方法

1.使用模块（最简单）
python的模块是天然的单例模式，模块在第一次导入时，会生成.pyc文件，当第二次导入时会直接加载.pyc文件，而不会再次执行模块代码。
<pre><code>class SingletonTest(object):
    def doNothing(self):
        print "Singleton test"

singletontest = SingletonTest()</code></pre>
调用：
<pre><code>from mysingleton import singletontest

singletontest.doNothing()
</code></pre>
2.使用__new__方法创建
__new__()在__init__()之前被调用，用于创建实例对象
<pre><code>class SingletonTest(object):
    __instance = None
    def __new__(cls, *args, **kwargs):
        if not cls.__instance:
            cls.__instance = super(SingletonTest,cls).__new__(cls, *args, **kwargs)
        return cls.__instance

class MyTest(SingletonTest):
    print "singleton show"

if __name__ == '__main__':
    a = MyTest()
    b = MyTest()
    c = MyTest()
    print a == b == c</code></pre>
调用：类只会创建一次，注意从SingletonTest派生子类的时候，不要重载__new__
<pre><code>
singleton show
True</code></pre>
3.使用装饰器实现单例模式
<pre><code>def singletonTest(cls, *args, **kw):
    instances = {}
    def _singleton():
        if cls not in instances:
            instances[cls] = cls(*args, **kw)
        return instances[cls]
    return _singleton

@singletonTest
class MyTest(object):
    a = 1
    def __init__(self, x=0):
        self.x = x

if __name__ == '__main__':
    a = MyTest()
    b = MyTest()
    c = MyTest()
    print a == b == c
    print id(a),id(b),id(c)</code></pre>
调用：类只会创建一次，注意从SingletonTest派生子类的时候，不要重载\__new__
<pre><code>
True
42044440 42044440 42044440
</code></pre>
4.使用元类创建单例模式
    ...... 

## Python 日志记录单例示例

<pre><code>#coding=utf-8
import logging
LOGPATH = "test.log"

class SingleLogger(object):
    __instance = None
    def __new__(cls, *args, **kwargs):
        if SingleLogger.__instance is None:
            SingleLogger.__instance = object.__new__(cls, *args, **kwargs)
            SingleLogger.__instance.__logger = logging.getLogger("loggertest")
            SingleLogger.__instance.__logger.setLevel(logging.DEBUG)
            formatter = logging.Formatter('%(asctime)4s %(levelname)-4s %(message)s','%Y-%m-%d %H:%M:%S')
            file_handler = logging.FileHandler(LOGPATH)
            stream_handler = logging.StreamHandler()
            file_handler.setFormatter(formatter)
            SingleLogger.__instance.__logger.addHandler(file_handler)
            SingleLogger.__instance.__logger.addHandler(stream_handler)
        return SingleLogger.__instance

    def info(self, message):
        SingleLogger.__instance.__logger.info(message)

    def error(self, message):
        SingleLogger.__instance.__logger.error(message)

    def debug(self, message):
        SingleLogger.__instance.__logger.debug(message)

if __name__ == '__main__':
    logger = SingleLogger()
    logger.info("test")
    logger.error("test")
    logger.debug("test")
</code></pre>

## 日志记录信息如下：

* 2017-03-08 18:55:10 INFO test
* 2017-03-08 18:55:10 ERROR test
* 2017-03-08 18:55:10 DEBUG test

5. 共享属性(创建实例时把所有实例的__dict__指向同一个字典,这样它们具有相同的属性和方法)
<pre><code>class Borg(object):
    _state = {}
    def __new__(cls, *args, **kw):
        ob = super(Borg, cls).__new__(cls, *args, **kw)
        ob.__dict__ = cls._state
        return ob
 
class MyClass2(Borg):
    do something</code></pre>
    
