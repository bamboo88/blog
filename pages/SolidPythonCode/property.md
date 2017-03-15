---
title: SolidPythonCode
keywords: sample
summary: "SolidCode"
sidebar: solid_code
permalink: solid_property.html
folder: SolidPythonCode
---

### python内置装饰器-property

### 实战场景演练

一. 现在我公司提供了对外求的BMI的值的接口服务，代码如下：
<pre><code>#-*-coding:utf-8-*-
import math
class BMI():
    def __init__(self,height = 0,weight = 0):
        self.height = height
        self.weight = weight
    def comput_bmi(self):
        bmi = self.weight / math.pow(self.height,2)
        if 18.5 <= bmi <= 24:
            print "standard stature"
        elif bmi < 18.5 :
            print "slim stature"
        else:
            print "strong stature"

if __name__ == '__main__':
    "A、B公司调用样例"
    bmi = BMI(60,1.7)
    bmi.comput_bmi()
    #bmi = BMI()
    #bmi.height = 1.7
    #bmi.weight = 60
    #bmi.comput_bmi()
    print bmi.__dict__</code></pre>
执行结果：
<pre><code>standard stature
{'weight': 60, 'height': 1.7}
bmi.weight在其内部就变成了bmi.__dict__['weight'];
bmi.height在其内部就变成了bmi.__dict__['height'];</code></pre>

二. 现在A、B公司某些客户喜欢恶意输入身高和体重参数，扰乱公司业务正常运行，现在A、B公司要求对身高和体重参数进行限定。
计划改进措施：
1. 将height和weight属性设置成私有属性
2. 新增height和weight的getter和setter的方法来判断用户输入的条件
<pre><code>#-*-coding:utf-8-*-
import math

class BMI():
    def __init__(self,height = 0,weight = 0):
        self.set_height(height)
        self.set_weight(weight)
    def comput_bmi(self):
        bmi = self.get_weight() / math.pow(self.get_height(),2)
        if 18.5 <= bmi <= 24:
            print "standard stature"
        elif bmi < 18.5 :
            print "slim stature"
        else:
            print "strong stature"

    def set_height(self,value):
        if value > 3.0 or value < 0:
            raise ValueError("The hight must greater than 0 and less than 3.0")
        self._height = value

    def set_weight(self,value):
        if value > 300 or value < 1:
            raise ValueError("The wight must greater than 1 and less than 300 kg")
        self._weight = value

    def get_height(self):
        return self._height

    def get_weight(self):
        return  self._weight
if __name__ == '__main__':
    # bmi = BMI(1.7,60)
    # bmi.comput_bmi()
    bmi = BMI(1.7,60)
    #Python中实际上是没有私有变量的。有一些简单的被遵循的规范。Python本身不会应用任何限制。
    #bmi._height = 10 也是可以赋值成功的
    bmi.set_height(1.7)
    bmi.set_weight(200)
    bmi.comput_bmi()
    print bmi.__dict__</code></pre>
执行结果：
<pre><code>strong stature
{'_height': 1.7, '_weight': 200}</code></pre>
弊端分析：
1. 客户之前使用的代码现在必须修改：
    # obj.height 修改为 obj.get_height()
    # obj.height 修改为 obj.set_height(value)
这样的重构和更新不向后兼容，给使用者带来很大的麻烦。

{% include links.html %}