---
title: Inheritance
keywords: sample
summary: "inheritance"
sidebar: advanced_features_sidebar
permalink: inheritance.html
folder: AdvancedFeatures
---

#### 单个类继承参数的变化演示

```
class parent(object):
    x=1 
    
class child1(parent):
    pass
    
class child2(parent):
    pass
    
print parent.x,child1.x,child2.x (1,1,1)

child1.x = 2
print parent.x,child1.x,child2.x (1,2,1)

parent.x = 3
print parent.x,child1.x,child2.x (3,2,3)

```

#### 理解MRO(Method Resolution Order)方法解析顺序和多继承


1. 在古典类中,MRO 搜索采用简单的自左至右额深度优先方法,即按照多继承申明的顺序形成继承树的结构,
   自顶向下采用深度优先的搜索顺序,当找到所需要的属性和方法的时候就停止搜索。
   
2. 新式类采用的是C3 MRO 搜索方法


#### 应该尽量避免多重继承

{% include links.html %}
