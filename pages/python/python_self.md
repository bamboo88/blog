---
title: python之self
keywords: sample
summary: "Python Self"
sidebar: python_sidebar
permalink: python_self.html
folder: python
---

### python中self理解
#### self 是指向类实例对象而非类本身
示例代码
<pre><code>class SelfTest:
    def printself(self):
        print self
        print self.__class__

bamboo = SelfTest()
bamboo.printself()</code></pre>
运行结果：
<pre><code>&lt;__main__.SelfTest instance at 0x00000000022DB308 &gt; 代表类实例对象
__main__.SelfTest 代表类本身
</code></pre>

#### self 不是Python中的关键字，可以任何名字代替，约定俗称用self
示例代码
<pre><code>class SelfTest:
    def printself(hello):
        print hello
        print hello.__class__

bamboo = SelfTest()
在Python的解释器内部,当我们调用bamboo.printself()时,实际上Python解释成SelfTest.printself(bamboo),也就是说把self替换成类的实例。下面两行运行的结果相同
bamboo.printself()
SelfTest.printself(bamboo)</code></pre>
运行结果：
<pre><code>&lt;__main__.SelfTest instance at 0x00000000022DB308 &gt; 代表类实例对象
__main__.SelfTest 代表类本身
&lt;__main__.SelfTest instance at 0x00000000026EB308 &gt;
__main__.SelfTest</code><pre>
