---
title: markdown使用指南
date: 2021-02-22 12:00:06
tags:
---

[TOC]

# markdown简介
Markdown是一种可以使用普通文本编辑器编写的标记语言，通过简单的标记语法，它可以使普通文本内容具有一定的格式。其文本格式为.md

类似于html，只不过标签更简单，更易读易写，可以转化外html

md不是一种编程语言，也不会代替html，适用写文档，写博客的。

可以直接添加html标签来写，也可以用md标签来写，也可以不用标签

**优点：**

- 纯文本，兼容性强，所有的文本编辑器都支持
- 让用户专注于内容而不是排版
- md可以随意转换为html，pdf，md格式的
- 标记语法具有良好的可读性

# markdown编辑器
## 在线版

- [1. dillinger](http://dillinger.io/)
- [2. stackedit](https://stackedit.io/)
- [3. mahua](http://mahua.jser.me/)
- [4. 博客平台－简书](http://www.jianshu.com/)
- [5. 博客平台－博客园](http://www.cnblogs.com/)
- [6. 马克飞象](https://maxiang.io/)

## window客户端

- [1. MarkdownPad](http://markdownpad.com/)
- [2. MarkPad](http://code52.org/DownmarkerWPF/)
- [3. Smark](http://git.oschina.net/elerao/Smark)
- [4. Miu](https://github.com/egoist/Miu)

## mac客户端

- [1. mou](http://25.io/mou/)
- [2. Macdown](http://macdown.uranusjr.com/)
- [3. UIysses](https://ulyssesapp.com/)

## 浏览器插件

- [MaDe](https://chrome.google.com/webstore/detail/made/oknndfeeopgpibecfjljjfanledpbkog/related)

## 文本编辑器

- Sublime Text
- Atom
- WebStorm

## 参考文档

- [月光博客](http://www.williamlong.info/archives/4319.html)

# markdown语法
## 标题
在标题前面加\# 即可
语法：
```
# title		//是一级标题
## title	//是二级标题
### title	//三级标题
#### title	//四级
##### title	//五级
###### title//六级
```
结果：
![分级标题](https://github.com/ruchoc/markdownPhotos/raw/main/pictures/4.png)

## 段落
段落就是一段文字（此处即是一处段落）

## 列表
无序列表是通过\+、\-、\*来实现的
语法：

```
+ html
- css
* js
```
结果：
+ html
- css
* js

使用\+
语法：
```
+ html
+ css
+ js
```
结果：
+ html
+ css
+ js

有序列表是通过1.,2.来表示的
语法：
```
1. html
2. css
3. js
```
结果：
1. html
2. css
3. js

嵌套规则：上一级与下一级之间敲三个空格即可
语法：
```
1. html
   1. css
      1.js
```
结果：
1. html
   1. css
      1.js

## 链接

链接就是超链接
+ 不带title
语法：
```
[百度](http://www.baidu.com)
```
结果：
[百度](http://www.baidu.com)

+ 带title
语法：
```
[百度](http://www.baidu.com "Title")
[id]: http://www.baidu.com "Title"
(other text)
[百度][id]
```
结果：
[百度](http://www.baidu.com "Title")

+ 自动链接
语法：
```
<http://www.baidu.com/>
```
结果：
<http://www.baidu.com/>

+ 自动生成邮箱
语法：
```
<285182436@qq.com>
```
结果：
<285182436@qq.com>

## 图片
+ 插入本地图片
语法：
```
![alt](/user/desktop/doge.png)	//这里采用相对路径，也可使用绝对路径
```
结果：
显示一张本地的图片

+ 插入网络图片
语法：
```
![](http://mouapp.com/Mou_128.png)
![alt](http://mouapp.com/Mou_128.png 'optionalTitle')
![alt][id]
(OTHER_TEXT)
[id]: http://mouapp.com/Mou_128.png "Title"
//三种语法效果一样
```
结果：
![alt](http://mouapp.com/Mou_128.png 'optionalTitle')

+ 把图片存入markdown文件
用base64转码工具把图片转成一段字符串，然后把字符串填到基础格式中链接的那个位置
语法：
`![](data:image/png;base64,iVBORw0......)`
结果：
显示一张图片
这样做法经常会有字符串太长从而割裂整篇文章，非常影响阅读体验，所以可以结合上述第三种方法，把大段的字符串放到最后面
语法：
```
![][id]
//文末存储字符串语法：
[id]:data:image/png;base64,iVBORw0......
```
结果：
显示一张图片

*综合考量，只推荐第二种方法。第三种方法操作麻烦还容易造成卡顿*

## 引用
语法：
```
> 引用内容
```
结果：
> 引用内容

*多行引用*
语法：
```
    面朝大海，春暖花开

> 从明天起，做一个幸福的人   

> 喂马、劈柴，周游世界  

> 从明天起，关心粮食和蔬菜  

> 我有一所房子，面朝大海，春暖花开  

> 从明天起，和每一个亲人通信  

> 告诉他们我的幸福  

> 那幸福的闪电告诉我的  

> 我将告诉每一个人  

> 给每一条河每一座山取一个温暖的名字  

> 陌生人，我也为你祝福  

> 愿你有一个灿烂的前程  

> 愿你有情人终成眷属  

> 愿你在尘世获得幸福  

> 我只愿面朝大海，春暖花开  
```
结果：
    面朝大海，春暖花开

> 从明天起，做一个幸福的人   

> 喂马、劈柴，周游世界  

> 从明天起，关心粮食和蔬菜  

> 我有一所房子，面朝大海，春暖花开  

> 从明天起，和每一个亲人通信  

> 告诉他们我的幸福  

> 那幸福的闪电告诉我的  

> 我将告诉每一个人  

> 给每一条河每一座山取一个温暖的名字  

> 陌生人，我也为你祝福  

> 愿你有一个灿烂的前程  

> 愿你有情人终成眷属  

> 愿你在尘世获得幸福  

> 我只愿面朝大海，春暖花开  

## 粗体
语法：
```
**粗体字**
```
结果：
**粗体字**

## 斜体
语法：
```
*斜体字*
```
结果：
*斜体字*

## 粗体+斜体
语法：
```
***粗斜体字***
```
结果：
***粗斜体字***

## 删除线
语法：
```
~~删除线内容~~
```
结果：
~~删除线内容~~

## 高亮
语法：
```
==高亮内容==
```
结果：
==高亮内容==

## 代码引用
*单行代码引用*
语法：
```
`引用内容`
```
结果：
`引用内容`

*多行代码引用*
语法：
最上一行与最下一行都用三个\`，中间写引用内容
结果：
```代码使用语言
引用内容1
引用内容2
引用内容3
```

## 分割线
语法：
```
***
---
___
```
结果：
***
---
___

## 表格
语法：
```
|left      |middle    |right     |
|----------|:--------:|---------:|
|1         |2         |3         |
|4         |5         |6         |
|7         |8         |9         |
```
结果：
|left      |middle    |right     |
|----------|:--------:|---------:|
|1         |2         |3         |
|4         |5         |6         |
|7         |8         |9         |
*注意第二行的冒号分别代表着居中和右对齐，默认左对齐*

## 转义
markdown判定在以下字符前加反斜杠\\字符会以原样输出
```
\   反斜线
`   反引号
*   星号
_   底线
{}  花括号
[]  方括号
()  括弧
#   井字号
+   加号
-   减号
.   英文句点
!   惊叹号
```
举例：
`\\`
结果：
\\

## 流程图
语法：
> 三个反引号+flow
> st=>start: 开始
op=>operation: My Operation
cond=>condition: Yes or No?
e=>end
st->op->cond
cond(yes)->e
cond(no)->op
> 三个反引号

结果：
```flow
st=>start: 开始
op=>operation: My Operation
cond=>condition: Yes or No?
e=>end
st->op->cond
cond(yes)->e
cond(no)->op
```

***流程图中的条件语句指出箭头只能是yes或no***

## 锚点
在你想要放置目录的地方独留一行`[toc]`即可自动生成目录树

*在目录树之外跳转到某个标题*
语法：
```
[回到markdown简介](#markdown简介)
//无论是几级标题，都只需一个#
//在typora里跳转需要Ctrl+click
//而在web环境下则不需要Ctrl
```
结果：
[回到markdown简介](#markdown简介)

其它语法：
```
[id]: #markdown简介
[id][]
[回到markdown简介][id]
```
结果：
[id]: #markdown简介
[id][]
[回到markdown简介][id]

**注意**
MarkDown形式的锚点目标的定义其实就是标题的定义即：任何级别的标题可以直接作为锚点目标；
锚点的目标内容中不能有大写字母和空格，所以如果锚点目标的目标内容中有大写字母或空格，
则需要在定义锚点中的目标内容时，把大写字母改成小写字母，把空格改成-