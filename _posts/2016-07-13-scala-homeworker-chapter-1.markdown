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

#### 5. 10 max 2的含义是什么？max方法定义在哪个类中？

    {% highlight scala %}
    /*
     * class Int
     * def max(that: Int): Int
     * Returns this if this > that or that otherwise.
    */
    scala> 10 max 2
    res1: Int = 10

    scala> 10 max 20
    res2: Int = 20
    
    scala> 10.max(20)
    res3: Int = 20

    scala> 10.max(2)
    res4: Int = 10
    
    {% endhighlight %}
    
#### 6. 用BigInt计算2的1024次方

    {% highlight scala %}
    scala> BigInt(2) pow 1024
    res10: scala.math.BigInt = 179769313486231590772930519078902473361797697894230657273430081157732675805500963132708477322407536021120113879871393357658789768814416622492847430639474124377767893424865485276302219601246094119453082952085005768838150682342462881473913110540827237163350510684586298239947245938479716304835356329624224137216
    
    scala> 2 pow 1024
    <console>:12: error: value pow is not a member of Int
       2 pow 1024
         ^
    /*
     *  如果不做特殊声明, 2 会默认认为是Int类型，Int类型不支持pow，所以报错
     */
    
    {% endhighlight %}
    
#### 7. 为了在使用probablePrime(100, Random)获取随机素数时不在probablePrime和Random之前使用任何限定符，你需要引入什么？

{% highlight scala %}
scala> import scala.util._
import scala.util._

scala> import scala.math.BigInt._
import scala.math.BigInt._

scala> probablePrime(100, Random)
res12: scala.math.BigInt = 983022931752053941466290644433
{% endhighlight %}

#### 8. 创建随机文件的方式之一是生成一个随机的BigInt，然后将它转成36进制，输出类似"qsnvbevtomcj38o06kul"这样的字符串。查阅Scaladoc,找到在Scala中实现该逻辑的方法。

{% highlight scala %}
scala> import scala.util._
import scala.util._

scala> import scala.math.BigInt._
import scala.math.BigInt._

scala> probablePrime(100, Random)
res12: scala.math.BigInt = 983022931752053941466290644433

scala> res12.toString(36)
res13: String = 2nb04a2ah7rvay82yymp
{% endhighlight %}

#### 8. 在Scala中如何获取字符串的首字符和尾字符

{% highlight scala %}
scala> "abcdef".head
res14: Char = a

scala> "abcdef".tail
res15: String = bcdef

scala> "abcdef".last
res16: Char = f
{% endhighlight %}

#### 9. take, drop, takeRight, dropRight这些字符串函数是做什么用的？和substring相比，它们的优点和缺点都有哪些？

{% highlight scala %}
scala> "12345678".drop(3)
res17: String = 45678

scala> "12345678".take(2)
res18: String = 12

scala> "12345678".takeRight(3)
res19: String = 678

scala> "12345678".dropRight(3)
res20: String = 12345
{% endhighlight  %}

个人认为drop take 更加能够反映用户真实的意图。 性能上，同样的处理意图（take(x)， substring(0, x)）我简单对比了一下，差别不大.

