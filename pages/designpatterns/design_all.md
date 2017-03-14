---
title: Design Patterns
keywords: sample
summary: "Design Patterns"
sidebar: python_design
permalink: design_pattern.html
folder: designpattern
---


### 设计模式分为三类
* 创建型模式(5种):工厂方法模式、抽象工厂模式、单例模式、建造者模式、原型模式。
* 结构型模式(7种):适配器模式、装饰器模式、代理模式、外观模式、桥接模式、组合模式、享元模式。
* 行为型模式(11种):策略模式、模板方法模式、观察者模式、迭代子模式、责任链模式、命令模式、备忘录模式、状态模式、访问者模式、中介者模式、解释器模式。
### 设计模式原则
1. 开闭原则(Open Close Principle)
  开闭原则是指对扩展开放，对修改关闭。在程序拓展的时候，不能去修改原有的代码，实现一个热插拔的效果
2. 里氏代换原则(Liskov Substitution Principle)
* 子类的能力必须大于等于父类，即父类可以使用的方法，子类都可以使用。
* 子类返回值的能力是比父类小
* 任何子类方法可以声明抛出父类方法声明异常的子类。而不能声明抛出父类没有声明的异常。
3. 依赖倒转原则(Dependence Inversion Principle)
面向接口编程，依赖于抽象而不依赖于具体。
4. 接口隔离原则(Interface Segregation Principle)
降低依赖，降低耦合。
5. 迪米特法则(最少知道原则)(Demeter Principle)
一个实体应当尽量少的与其他实体之间发生相互作用，使得系统功能模块相对独立。
6. 合成复用原则(Composite Reuse Principle)
尽量使用合成/聚合的方式，而不是使用继承。
