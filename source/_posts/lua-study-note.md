---
title: Lua学习笔记
toc: false
date: 2017-01-03 22:23:05
categories: IT
tags: lua
---



开始学习Lua啦。
学会了就可以去搭建openApi平台 n(*≧▽≦*)n


<!--more-->
- Lua快，LuaJIT更快
- 用源码的方式安装LuaJIT 2.1版本，虽然是beta版本，但是比正式版本的2.0的效率高
- 安装好Lua后运行`ln -sf luajit-2.1.0-beta1 /usr/local/bin/luajit`才能在命令行使用luajit命令
- type()方法显示变量类型
- nil表示空类型
- boolean:0和false为假，其他为真
- 除单引号、双引号外可以用长括号的方式定义字符串,[[0级,[=[1级,[==[2级
- 字符串会内化（intern）,值相同的字符串存储在相同的地址中，比较两个字符串值是否相同即比较他们的地址是否一致
- 函数也是一种数据类型，有名函数的定义本质上是匿名函数对变量的赋值
- ^指数
- ~=不等于
- a and b a为nil返回a,否则返回b
- a or b a为nil返回b,否则返回a
- 不要在循环中进行大量的字符串的拼接，会生成很多新的字符串，用table和table.contact代替，或使用table.new
- ..用来进行字符串的拼接
- elseif和else if不同，else if表示在else中嵌套了if
- while语句有break，没有continue；没有do-while，有repeat
- repeat-until直到条件为真时结束
- for var=begin,finish(,step) do step可省略,默认为1，不想设置上限时，可以让finish=math.huge
- for i,v in ipairs(array) do 通过迭代器ipairs遍历数组中的值
- 其他迭代器包括：io.lines迭代文件中的每行;pairs迭代table元素；string.gmatch迭代字符串
- ipairs()可以被JIT编译，pairs()只能被解释执行。在性能敏感的场景，避免对表遍历
- return只能写在语句块的最后，一旦执行了return语句，该语句之后的所有语句都不会再执行
- 全局变量会污染全局变量空间，有性能损耗，尽量使用局部变量和局部函数：local
