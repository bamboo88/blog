---
title: Multi THread
keywords: sample
summary: "Multi Thread"
sidebar: advanced_features_sidebar
permalink: multi_process.html
folder: AdvancedFeatures
---

```
#-*-coding:utf-8-*-
from multiprocessing import Process
import os

# 子进程要执行的代码
def run_proc(name):
    print('Run child process {} {} ...'.format(name,os.getpid()))

if __name__=='__main__':
    print 'Parent process {}.'.format(os.getpgid())
    p = Process(target=run_proc, args=('test',))
    print('Child process will start.')
    p.start()
    p.join()
    print('Child process end.')
```
执行结果:
```
Parent process 6512.
Child process will start.
Run child process test (14288)...
Child process end.
```

{% include links.html %}
