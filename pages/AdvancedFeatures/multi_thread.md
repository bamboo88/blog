---
title: Multi THread
keywords: sample
summary: "Multi Thread"
sidebar: advanced_features_sidebar
permalink: multi_thread.html
folder: AdvancedFeatures
---

Python 实现多线程的方式：
1. 函数
2. 用类来包装对象

python版本: 2.7

函数实现方式:

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
    #启动线程之后,须确保主线程等待所有子线程返回结果后再退出,如果主线程比子线程早结束,无论其子线程是否是后台线程,都将会中断,抛出异常:Unhandled exception in thread started by sys.excepthook is missing lost sys.stderr 
    while 1:
       pass
  ```




{% include links.html %}
