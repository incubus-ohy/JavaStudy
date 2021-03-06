# Java集合容器面试题目录

   * [一.集合容器概述](#一集合容器概述)
      * [1.什么是集合](#1什么是集合)
      * [2.集合的特点](#2集合的特点)
      * [3.集合和数组的区别](#3集合和数组的区别)
      * [4.使用集合框架的好处](#4使用集合框架的好处)
      * [5.常用的集合类有哪些？](#5常用的集合类有哪些)
      * [6.List，Set，Map三者的区别？List、Set、Map 是否继承自 Collection 接口？List、Map、Set 三个接口存取元素时，各有什么特点？](#6listsetmap三者的区别listsetmap-是否继承自-collection-接口listmapset-三个接口存取元素时各有什么特点)
      * [7.集合框架底层数据结构](#7集合框架底层数据结构)
      * [8.哪些集合类是线程安全的？](#8哪些集合类是线程安全的)
      * [9.Java集合的快速失败机制 “fail-fast”？](#9java集合的快速失败机制-fail-fast)
      * [10.怎么确保一个集合不能被修改？](#10怎么确保一个集合不能被修改)
   * [二.Collection接口](#二collection接口)
      * [1.List接口](#1list接口)
         * [(1). 迭代器 Iterator 是什么？](#1-迭代器-iterator-是什么)
         * [(2). Iterator 怎么使用？有什么特点？](#2-iterator-怎么使用有什么特点)
         * [(3). 如何边遍历边移除 Collection 中的元素？](#3-如何边遍历边移除-collection-中的元素)
         * [(4). Iterator 和 ListIterator 有什么区别？](#4-iterator-和-listiterator-有什么区别)
         * [(5). 遍历一个 List 有哪些不同的方式？每种方法的实现原理是什么？Java 中 List 遍历的最佳实践是什么？](#5-遍历一个-list-有哪些不同的方式每种方法的实现原理是什么java-中-list-遍历的最佳实践是什么)
         * [(6). 说一下 ArrayList 的优缺点](#6-说一下-arraylist-的优缺点)
         * [(7). 如何实现数组和 List 之间的转换？](#7-如何实现数组和-list-之间的转换)
         * [(8). ArrayList 和 LinkedList 的区别是什么？](#8-arraylist-和-linkedlist-的区别是什么)
         * [(9). ArrayList 和 Vector 的区别是什么？](#9-arraylist-和-vector-的区别是什么)
         * [(10). 插入数据时，ArrayList、LinkedList、Vector谁速度较快？阐述 ArrayList、Vector、LinkedList 的存储性能和特性？](#10-插入数据时arraylistlinkedlistvector谁速度较快阐述-arraylistvectorlinkedlist-的存储性能和特性)
         * [(11). 多线程场景下如何使用 ArrayList？](#11-多线程场景下如何使用-arraylist)
         * [(12). 为什么 ArrayList 的 elementData 加上 transient 修饰？](#12-为什么-arraylist-的-elementdata-加上-transient-修饰)
         * [(13). List 和 Set 的区别](#13-list-和-set-的区别)
      * [2.Set接口](#2set接口)
         * [(1). 说一下 HashSet 的实现原理？](#1-说一下-hashset-的实现原理)
         * [(2). HashSet如何检查重复？HashSet是如何保证数据不可重复的？](#2-hashset如何检查重复hashset是如何保证数据不可重复的)
         * [(3). HashSet与HashMap的区别](#3-hashset与hashmap的区别)
      * [3.Queue](#3queue)
         * [(1). BlockingQueue是什么？](#1-blockingqueue是什么)
         * [(2). 在 Queue 中 poll()和 remove()有什么区别？](#2-在-queue-中-poll和-remove有什么区别)
   * [三.Map接口](#三map接口)
      * [1.说一下 HashMap 的实现原理？](#1说一下-hashmap-的实现原理)
      * [2.HashMap在JDK1.7和JDK1.8中有哪些不同？HashMap的底层实现](#2hashmap在jdk17和jdk18中有哪些不同hashmap的底层实现)
         * [(1). JDK1.8之前](#1-jdk18之前)
         * [(2). JDK1.8之后](#2-jdk18之后)
         * [(3). JDK1.7 VS JDK1.8 比较](#3-jdk17-vs-jdk18-比较)
      * [3.HashMap的put方法的具体流程？](#3hashmap的put方法的具体流程)
      * [4.HashMap的扩容操作是怎么实现的？](#4hashmap的扩容操作是怎么实现的)
      * [5.HashMap是怎么解决哈希冲突的？](#5hashmap是怎么解决哈希冲突的)
         * [(1). 什么是哈希？](#1-什么是哈希)
         * [(2). 什么是哈希冲突？](#2-什么是哈希冲突)
         * [(3). HashMap的数据结构](#3-hashmap的数据结构)
         * [(4). hash()函数](#4-hash函数)
         * [(5). JDK1.8新增红黑树](#5-jdk18新增红黑树)
         * [(6). 总结](#6-总结)
      * [6.能否使用任何类作为 Map 的 key？](#6能否使用任何类作为-map-的-key)
      * [7.为什么HashMap中String、Integer这样的包装类适合作为K？](#7为什么hashmap中stringinteger这样的包装类适合作为k)
      * [8.如果使用Object作为HashMap的Key，应该怎么办呢？](#8如果使用object作为hashmap的key应该怎么办呢)
      * [9.HashMap为什么不直接使用hashCode()处理后的哈希值直接作为table的下标？](#9hashmap为什么不直接使用hashcode处理后的哈希值直接作为table的下标)
      * [10.HashMap 的长度为什么是2的幂次方](#10hashmap-的长度为什么是2的幂次方)
      * [11.HashMap 与 HashTable 有什么区别？](#11hashmap-与-hashtable-有什么区别)
      * [12.如何决定使用 HashMap 还是 TreeMap？](#12如何决定使用-hashmap-还是-treemap)
      * [13.HashMap 和 ConcurrentHashMap 的区别](#13hashmap-和-concurrenthashmap-的区别)
      * [14.ConcurrentHashMap 和 Hashtable 的区别？](#14concurrenthashmap-和-hashtable-的区别)
      * [15.ConcurrentHashMap 底层具体实现知道吗？实现原理是什么？](#15concurrenthashmap-底层具体实现知道吗实现原理是什么)
   * [四.辅助工具类](#四辅助工具类)
      * [1.Array 和 ArrayList 有何区别？](#1array-和-arraylist-有何区别)
      * [2.如何实现 Array 和 List 之间的转换？](#2如何实现-array-和-list-之间的转换)
      * [3.comparable 和 comparator的区别？](#3comparable-和-comparator的区别)
      * [4.Collection 和 Collections 有什么区别？](#4collection-和-collections-有什么区别)
      * [5.TreeMap 和 TreeSet 在排序时如何比较元素？Collections 工具类中的 sort()方法如何比较元素？](#5treemap-和-treeset-在排序时如何比较元素collections-工具类中的-sort方法如何比较元素)

***

# 说明

>- **本文所涉及的所有面试题皆收自一线互联网大厂**
>- **GitHub用户如果访问过慢的话，可以移步至【资源分享群】下载本地文件**
>- **资源分享群链接：[点击加入群聊](https://jq.qq.com/?_wv=1027&k=5Op2CWT)**
>- **视频资料请关注微信公众号"Java架构筑基"免费获取**

***

# 一.集合容器概述

## 1.什么是集合

**集合框架**：用于存储数据的容器。

集合框架是为表示和操作集合而规定的一种统一的标准的体系结构。

任何集合框架都包含三大块内容：对外的接口、接口的实现和对集合运算的算法。

**接口**：表示集合的抽象数据类型。接口允许我们操作集合时不必关注具体实现，从而达到“多态”。在面向对象编程语言中，接口通常用来形成规范。

**实现**：集合接口的具体实现，是重用性很高的数据结构。

**算法**：在一个实现了某个集合框架中的接口的对象身上完成某种有用的计算的方法，例如查找、排序等。这些算法通常是多态的，因为相同的方法可以在同一个接口被多个类实现时有不同的表现。事实上，算法是可复用的函数。

它减少了程序设计的辛劳。

集合框架通过提供有用的数据结构和算法使你能集中注意力于你的程序的重要部分上，而不是为了让程序能正常运转而将注意力于低层设计上。

通过这些在无关API之间的简易的互用性，使你免除了为改编对象或转换代码以便联合这些API而去写大量的代码。 它提高了程序速度和质量。

## 2.集合的特点

集合的特点主要有如下两点：

* 对象封装数据，对象多了也需要存储。集合用于存储对象。
* 对象的个数确定可以使用数组，对象的个数不确定的可以用集合。因为集合是可变长度的。

## 3.集合和数组的区别

* 数组是固定长度的；集合可变长度的。
* 数组可以存储基本数据类型，也可以存储引用数据类型；集合只能存储引用数据类型。
* 数组存储的元素必须是同一个数据类型；集合存储的对象可以是不同数据类型。

**数据结构**：就是容器中存储数据的方式。

对于集合容器，有很多种。因为每一个容器的自身特点不同，其实原理在于每个容器的内部数据结构不同。

集合容器在不断向上抽取过程中，出现了集合体系。

## 4.使用集合框架的好处

* 容量自增长；
* 提供了高性能的数据结构和算法，使编码更轻松，提高了程序速度和质量；
* 允许不同 API 之间的互操作，API之间可以来回传递集合；
* 可以方便地扩展或改写集合，提高代码复用性和可操作性。
* 通过使用JDK自带的集合类，可以降低代码维护和学习新API成本。

## 5.常用的集合类有哪些？

* Map接口和Collection接口是所有集合框架的父接口：
* Collection接口的子接口包括：Set接口和List接口
* Map接口的实现类主要有：HashMap、TreeMap、Hashtable、ConcurrentHashMap以及Properties等
* Set接口的实现类主要有：HashSet、TreeSet、LinkedHashSet等
* List接口的实现类主要有：ArrayList、LinkedList、Stack以及Vector等

## 6.List，Set，Map三者的区别？List、Set、Map 是否继承自 Collection 接口？List、Map、Set 三个接口存取元素时，各有什么特点？

![图片](https://uploader.shimo.im/f/0lsDLasWrbw0e0N9.png!thumbnail)

Java 容器分为 Collection 和 Map 两大类，Collection集合的子接口有Set、List、Queue三种子接口。我们比较常用的是Set、List，Map接口不是collection的子接口。

Collection集合主要有List和Set两大接口

* List：一个有序（元素存入集合的顺序和取出的顺序一致）容器，元素可以重复，可以插入多个null元素，元素都有索引。常用的实现类有 ArrayList、LinkedList 和 Vector。
* Set：一个无序（存入和取出顺序有可能不一致）容器，不可以存储重复元素，只允许存入一个null元素，必须保证元素唯一性。Set 接口常用实现类是 HashSet、LinkedHashSet 以及 TreeSet。

Map是一个键值对集合，存储键、值和之间的映射。 Key无序，唯一；value 不要求有序，允许重复。Map
