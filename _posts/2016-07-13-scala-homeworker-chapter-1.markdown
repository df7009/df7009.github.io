---
layout: post
title:  "快学scala_cahpter_1习题"
category: scala
categories: jekyll update
---


#### 1. 在Scala REPL中键入3，然后按Tab键。 有哪些方法可以被应用？

#### 2. 在Scala REPL中计算3的平方根，然后再对该值求平方。现在，这个结果与3相差多少？（提示: res 变量是你的朋友）

    {% highlight scala %}
    scala> scala.math.sqrt(3)
    res0: Double = 1.7320508075688772
    scala> res0*res0
    res2: Double = 2.9999999999999996
    {% endhighlight %}

#### 3. res 变量是val 还是var？
    
    {% highlight scala %}
    scala> res0 = 1.7
    <console>:12: error: reassignment to val // res is val type
           res0 = 1.7
    {% endhighlight %}
    
#### 4. Scala允许你用数字去乘字符串-去REPL中试一下“crazy”*3。这个操作做什么？ 在Scaladoc中如何找到这个操作？

    ![1-1]({{ site.url }}/images/quick-scala/quick-scala-1-1.png)
    

