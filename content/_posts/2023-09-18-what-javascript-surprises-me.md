---
layout: post
title: "What Javascript Surprises Me"
date: 2023-09-18
author: "Jamin Chen"
header-img: "img/post-bg-universe.jpg"
tags: ["Computer Languages"]
---

## 背景

我比较喜欢研究计算机语言理论。所有的计算机语言来自于历史上诸多计算机学者和工程人
员的努力。每种语言都有生而为之的特征。每年都有诸多计算机语言诞生，而追寻每种语言
背后的故事以及了解它们的与众不同的特点，很有意思。这是What X surprises me系列文
章之一，记录某种语言的设计特点在我的认知中带来某种惊讶或惊喜。有点钟书先生《管锥
编》异曲同工之意。这篇有关Javascirpt的语言特点，对比的背景是Java/CPP/Python等。

## 基础

*   灵活的变量声明范围：var声明范围为function or script scoped，let和const是block-scoped
*   声明提升：var可提升，默认为undefined; let和const不可提升，否则抛出referror

## 控制流

*   throw可以抛出任意类型

*   Boolean和literal true/false判定不同，if (Boolean) 为true

*   loop break: break label语法方便快速跳出更外层的loop；类似的continue label语法

*   for语法：for...in对object属性名进行遍历，或者对可便利变量如array values进行遍历；
    for...of对object所有可遍历属性的值进行遍历，针对不同属性调用不同的遍历器。

## 函数

*   func参数都是基于值传递，即更改参数值不影响外部传入参数；但是如果传入参数是obj或
    arr，修改obj属性或者arr value会同样修改外部对象属性。逻辑上并不矛盾，基于参数传
    递，可以理解为obj地址为参数值。

*   Closure功能比较强大并且随处可见。Closure生命周期能够超越定义它的外部函数，进入调
    用函数生命周期，成为真正意义的clousure。

*   arguments: func参数以array-like方式存储在arguments中，例如arguments\[0], length,
    callee (等价于func name)。

*   Arrow function (=>): 更短的函数声明，不绑定this，同时没有arguments, super,
    new.target等；在arrow function出现以前，所有函数须有绑定的this。

## 操作符

*   Comma为操作符之一，二元操作符，用于for loop condition

*   Array的\[]操作符，既是索引操作符根据index获取值，同时也是属性操作符根据值获取
    index。

## 对象与类

*   JS建立在一套简单灵活的Object概念之上

*   Object是引用类型reference type，因此两个不同object永不相等。

*   Object和Class是两个相似但不同的概念，不像其他语言中一个是另一个的实例化。

*   Object可以通过变量+初始化列表定义，变量名即为Object名称。

*   Object可以通过定义构造函数、并通过New创建。构造函数绑定this，arguments等内置
    \变量。在这个意义上，大部分函数都可以认为是object构造函数。Object可以通过

*   Object.create(ObjectName) 构造实例

*   Object可以定义函数类型的属性。

*   Object可以定义getter和setter，二者同样为属性，属性名为函数名

*   Function constructor定义的Object和Class在大多数情况下作用相同，如定义属性、
    \静态函数属性等，而Class可以定义private属性、methods，这是object所不具备的。

*   Class也可以通过声明class类型的变量定义，变量名即为Class名称。

*   Class构造函数通过constructor()定义，literally

*   Class private变量通过#varname定义

## 其他

*   Typed array是个奇怪的名称，更具体应该是typed buffer或者typeless array。和通常
    意义上的array并无相似之处，是一组特定长度的连续的内存空间。

*   任何类型都可以成为迭代器Iterator，只需要1）实现next() 方法；2）返回值包含value
    和done属性。注：这种有点类似python和go的duck typed接口声明，是一种很灵活的类
    型扩展机制。

*   JS支持一种简洁生成迭代器的函数，声明为function\*和yeild关键字。和Python yeild类
    似，但是没有后者简洁。

*   Iterables：特指支持for...of的遍历语法对象。一个对象如果想成为iterables，需要增
    加Symbol.iterator实现，其实现内容通常为function\* 定义的生成迭代器。
