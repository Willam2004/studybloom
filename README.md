studybloom
==========
布隆过滤器是1970由布隆提出的。它实际上是一个很长的二进制向量和一系列随机映射函数。
布隆过滤器可以用于检索一个元素是否在一个集合中。它的优点是空间效率和查询时间都远远超过一般的算法，
缺点是有一定的误识别率和删除困难。

引用链接：[布隆过滤器][1]
[1]:http://zh.wikipedia.org/wiki/%E5%B8%83%E9%9A%86%E8%BF%87%E6%BB%A4%E5%99%A8

这个工程的目的是我个人学习布隆过滤器的一些代码和笔记的积累。想通过各个语言实现布隆过滤器的方式来进行学习。
会有以下语言设计：

- Java
- C++

算法原理
============
根据吴军博士的 *《数学之美》* 描述，假定我们存储一亿个电子邮件地址，我们先建立一个二进制的数组，然后将这个二进制的数组中的值都置为0，对于每一个email地址，
我们用8个不同的随机数产生器（F1，F2....，F8）产生八个信息指纹（f1,f2,....,f8）.再用一个随机数产生器G把这八个信息指纹映射到1到十六亿的
八个自然数g1,g2,...,g8,现在我们把这八个位置二进制全部设置为1，当我们对这一亿个 email 地址都进行这样的处理后。一
个针对这些 email 地址的布隆过滤器就建成了。
