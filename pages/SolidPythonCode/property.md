---
title: SolidPythonCode
keywords: sample
summary: "SolidCode"
sidebar: solid_code
permalink: solid_property.html
folder: SolidPythonCode
---

### python����װ����-property

### ʵս��������

һ. �����ҹ�˾�ṩ�˶������BMI��ֵ�Ľӿڷ��񣬴������£�
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
    "A��B��˾��������"
    bmi = BMI(60,1.7)
    bmi.comput_bmi()
    #bmi = BMI()
    #bmi.height = 1.7
    #bmi.weight = 60
    #bmi.comput_bmi()
    print bmi.__dict__</code></pre>
ִ�н����
<pre><code>standard stature
{'weight': 60, 'height': 1.7}
bmi.weight�����ڲ��ͱ����bmi.__dict__['weight'];
bmi.height�����ڲ��ͱ����bmi.__dict__['height'];</code></pre>

��. ����A��B��˾ĳЩ�ͻ�ϲ������������ߺ����ز��������ҹ�˾ҵ���������У�����A��B��˾Ҫ�����ߺ����ز��������޶���
�ƻ��Ľ���ʩ��
1. ��height��weight�������ó�˽������
2. ����height��weight��getter��setter�ķ������ж��û����������
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
    #Python��ʵ������û��˽�б����ġ���һЩ�򵥵ı���ѭ�Ĺ淶��Python������Ӧ���κ����ơ�
    #bmi._height = 10 Ҳ�ǿ��Ը�ֵ�ɹ���
    bmi.set_height(1.7)
    bmi.set_weight(200)
    bmi.comput_bmi()
    print bmi.__dict__</code></pre>
ִ�н����
<pre><code>strong stature
{'_height': 1.7, '_weight': 200}</code></pre>
�׶˷�����
1. �ͻ�֮ǰʹ�õĴ������ڱ����޸ģ�
    # obj.height �޸�Ϊ obj.get_height()
    # obj.height �޸�Ϊ obj.set_height(value)
�������ع��͸��²������ݣ���ʹ���ߴ����ܴ���鷳��

{% include links.html %}