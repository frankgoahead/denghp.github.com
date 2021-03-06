--- 
layout: post
title: vim 格式化代码,注释代码 快捷键
tags: 
- vim
- 格式化
- 注释代码
- 快捷键
categories:
- Code
UUID: 201212252232
---

　　使用Vim开发经常会遇到代码比较乱的格式，相信有经验的朋友都知道，只要是开发工具，或者编辑器都会有格式化的功能，哪怕是很简单的方式，今天就给大家介绍下在vim中如何使用格式化和注释代码的快捷键。


###格式化方法
####格式化全文
<pre id="bash">
gg=G
</pre>

####格式化选择模式
1、首先使用vim快捷键 v + 下上左右 选择某一区域<br>
2、同样使用 gg=G的方式来格式化,也可以直接使用 = 

####格式化当前光标下的N行
使用 N= 就行，这里的N表示数量

####自动缩进当前行
使用  ==

###注释代码方法
####选择模式注释
1、首先使用vim快捷键 Ctrl + v 选择某一区域<br>
2、再按大写的 I 进入行首插入模式输入注释符号如 "//" 或 "#",输入完毕之后，Vim会自动将你选中的所有行首都加上注释

####取消注释
Ctrl + v 进入块选择模式，选中你要删除的行首的注释符号，注意// 要选中两个，选好之后按d即可删除注释.

####替换命令,批量注释
:起始行号,结束行号s/^/注释符/g

###取消注释
:起始行号,结束行号s/^注释符//g

###示例
在10 - 20行添加 // 注释
<pre id="bash">
:10,50s#^#//#g
</pre>
在10 - 20行删除 // 注释
<pre id="bash">
:10,20s#^//##g
</pre>

在10 - 20行添加 # 注释
<pre id="bash">
:10,20s/^/#/g
</pre>
在10 - 20行删除 # 注释
<pre id="bash">
:10,20s/^/#/g
</pre>

###提示
例子中正则的分割符使用的是相反的符号，如果匹配// 那么使用 #作分隔符这样不需要对/作转义处理，节省输入次数
