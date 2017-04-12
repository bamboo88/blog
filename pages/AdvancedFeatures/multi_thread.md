---
title: Multi THread
keywords: sample
summary: "Multi Thread"
sidebar: advanced_features_sidebar
permalink: multi_thread.html
folder: AdvancedFeatures
---

Python 实现线程的方式：
1. 使用thread.start_new_thread()方法实现
2. 继承threading.Thread类实现

python版本: 2.7

使用thread.start_new_thread()方法实现:

 ```
import thread
import time

def print_time(threadName,delay):
    count = 0
    while count < 5:
        time.sleep(delay)
        count += 1
        print "{} {} ---- ".format(threadName,time.strftime("%H:%M:%S",time.localtime()))


try:
   thread.start_new_thread(print_time,("Thread-1",1))
   thread.start_new_thread(print_time,("Thread-2",1))
except:
   print "Error: unable to start thread"
#启动线程之后,须确保主线程等待所有子线程返回结果后再退出,如果主线程比子线程早结束,无论其子线程是否是后台线程,都将会中断,抛出异常:Unhandled exception in thread started by sys.excepthook is missing lost sys.stderr,所以下面加了死循环执行程序
while 1:
   pass
  ```
执行结果：
```
Thread-1 13:57:50 ---- Thread-2 13:57:50 ---- 
Thread-1 13:57:51 ---- Thread-2 13:57:51 ---- 
Thread-2 13:57:52 ---- Thread-1 13:57:52 ---- 
Thread-1 13:57:53 ---- Thread-2 13:57:53 ---- 
Thread-2 13:57:54 ---- Thread-1 13:57:54 ---- 
  ```
线程的结束一般依靠线程函数的自然结束;也可以在线程函数中调用thread.exit(),他抛出SystemExit exception,达到退出线程的目的.
  
继承threading.Thread类实现(重写__init__方法和run方法):

```
import threading
import time
exitFlag = 0
class myThread (threading.Thread):   #继承父类threading.Thread
    def __init__(self, threadName, delay):
        threading.Thread.__init__(self)
        self.threadName = threadName
        self.delay = delay
    def run(self):                   #把要执行的代码写到run函数里面 线程在创建后会直接运行run函数
        print "Starting " + self.threadName
        print_time(self.threadName, self.delay, 5)
        print "Exiting " + self.threadName

def print_time(threadName, delay, counter):
    while counter:
        if exitFlag:
            threading.thread.exit()
        time.sleep(delay)
        print "{} {}".format(threadName,time.strftime("%H:%M:%S",time.localtime()))
        counter -= 1

# 创建新线程
thread1 = myThread("Thread-1", 1)
thread2 = myThread("Thread-2", 2)

# 开启线程
thread1.start()
thread2.start()

print "Exiting Main Thread"
```

执行结果：

```
Starting Thread-1
Starting Thread-2
Exiting Main Thread
Thread-1 14:32:53
Thread-2 14:32:54
Thread-1 14:32:54
Thread-1 14:32:55
Thread-2 14:32:56
Thread-1 14:32:56
Thread-1 14:32:57
Exiting Thread-1
Thread-2 14:32:58
Thread-2 14:33:00
Thread-2 14:33:02
Exiting Thread-2
```



{% include links.html %}
