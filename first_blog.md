# 如何使用 Markdown 书写博客
- ## Markdown 是什么？
Markdown是一种轻量级标记语言，你可以简单地理解为HTML的简化版，Markdown简单的语法使阅读和创作文档变得容易。因为语法特别简单而且容易排版，Markdown经常被用来书写个人博客。

Markdown简单易学，语法点很少，基本上一个小时就可以学完。下面将会具体介绍Markdown的基本语法，学会这些，你也可以自己写一篇排版优美的博客了！

---
## 目录
- [基础语法](#基础语法)
    - [标题](#标题)
    - [引述](#引述)
    - [字体格式](#字体格式)
    - [列表](#列表)
    - [链接](#链接)
    - [图片](#图片)
    - [代码块](#代码块)
    - [表格](#表格)
    - [目录索引](#目录索引)
- [扩展](#扩展)
    - [分隔线](#1.分隔线)
    - [删除线](#2.删除线)
    - [字符转义](#3.字符转义)
- [写在最后](#写在最后)
- [参考](#参考)
---

- ## 基础语法

与HTML一样，Markdown也有自己的文件格式，已md结尾，如：_test.md_

---

- ### 标题

Markdown标题语法非常简单，只要在文本前面加#号即可，如下：

```markdown
# 标题1
## 标题2
### 标题3
#### 标题4
##### 标题5
```

效果如下：
# 标题1
## 标题2
### 标题3
#### 标题4
##### 标题5

- ### 引述

---

在Markdown中使用引述，只需在引用文本前加“>”就行了：

```markdown
> 这是一个引述
>> 嵌套引述
```

效果：
> 这是一个引述
>> 嵌套引述

- ### 字体格式

---

Markdown中，使用_文本_的格式来斜体文本，使用__文本__的格式来加粗文本，具体如下(注: _都可以使用*来代替 , 就看你的个人喜好了):

```Markdown

_斜体_

**加粗**

___斜体加粗___

```

_斜体_

**加粗**

___斜体加粗___


- ### 列表

列表语法中,以下符合是等效的: __*__ , __-__ , __+__

看个人喜好咯.

代码:

```Markdown
- 一
- 二
- 三
    -- 二级列表
```

效果:
- 一
- 二
- 三
    - 二级列表

有序列表:

```Markdown
1. 一
2. 二
3. 三
4. 四
    - 可以搭配无序列表
    - 4.1
    - 4.2
```

效果:
1. 一
2. 二
3. 三
4. 四
    - 可以搭配无序列表
    - 4.1
    - 4.2

- ### 链接
Markdown链接有三种格式: 

1. 行内式：
格式为 \[link text](URL 'title text')。

代码：

```markdown
[百度一下,你就知道](http://www.baidu.com/)
```

效果：

[百度一下,你就知道](http://www.baidu.com/)

2. 参考式（推荐）：

> 参考式链接的写法相当于行内式拆分成两部分，并通过一个识别符来连接两部分。参考式能尽量保持文章结构的简单，也方便统一管理URL。

个人推荐使用参考式，这样我们可以把URL放在文件开头处，便于修改和管理，**参考式相对于行内式有一个明显的优点，就是可以在多个不同的位置引用同一个URL**。示例代码如下：

首先，定义链接(两个都是方括号)：
第二个方括号内为链接独有的识别符，可以是字母，数字，空白，**注意其不区分大小写**。

```markdown
[百度][link]
空白形式：
[百度][]
```

效果：

[百度][link]

空白形式：

[百度][]

定义链接内容：
其格式为：[识别符]: URL “title”。
示例代码如下：

```markdown
[link]: http://www.baidu.com/ "百度"
空白形式：
[百度]: http://www.baidu.com/ "百度"
```

[link]: http://www.baidu.com/ "百度"
[百度]: http://www.baidu.com/ "百度"
title 可写可不写， 我一般是先把链接定义在文件开头，然后再在文章内引用。

3. 直接式

这种形式适合来书写邮箱和引用链接，格式为\<URL>
代码：

```markdown
<www.baidu.com>

<www.example@email.com>
```

效果：

<www.baidu.com>

<www.example@email.com>

---

- ### 图片 
Markdown中引用图片格式如下：
> 插入图片的语法和插入超链接的语法基本一致，只是在最前面多一个!。也分为行内式和参考式两种。
格式为 \!\[img text](URL “title text”)。一样的，title text内容可写可不写。示例代码：

1. 行内式：

```markdown
![GitHub](https://avatars2.githubusercontent.com/u/3265208?v=3&s=100 "GitHub,Social Coding")
```
效果：

![GitHub](https://avatars2.githubusercontent.com/u/3265208?v=3&s=100 "GitHub,Social Coding")

2. 参考式（推荐）：

```markdown
![GitHub][github]

[github]: https://avatars2.githubusercontent.com/u/3265208?v=3&s=100 "GitHub,Social Coding"
```

效果：

![GitHub][github]

[github]: https://avatars2.githubusercontent.com/u/3265208?v=3&s=100 

---

- ### 代码块

Markdown中代码块格式如下：
示例：

\```python  
import os  
print("Hello")  
\```

三个\```要独占一行, \```后写上所写的语言名，就可以使用相应语言的语法高亮。
效果：

```python
import os
print("Hello")
```

- ### 表格
Markdown中搭建表格非常简单，语法如下：
> 使用 | 来分隔不同的单元格，使用 - 来分隔表头和其他行

示例代码：

```markdown
name | age
---- | ---
LearnShare | 12
Mike |  32
```

更加美观的写法：

```markdown
|    name    | age |
| ---------- | --- |
| LearnShare |  12 |
| Mike       |  32 |
```

效果：
|    name    | age |
| ---------- | --- |
| LearnShare |  12 |
| Mike       |  32 |

对齐：
在表头下方的分隔线标记中加入 :，即可标记下方单元格内容的对齐方式：  
:--- 代表左对齐  
:--: 代表居中对齐  
---: 代表右对齐  

代码：
```markdown
| left | center | right |
| :--- | :----: | ----: |
| aaaa | bbbbbb | ccccc |
| a    | b      | c     |
```
效果：
| left | center | right |
| :--- | :----: | ----: |
| aaaa | bbbbbb | ccccc |
| a    | b      | c     |

---

- ### 目录索引

对一篇长的文章来说，一个带位置定位的目录是很重要的，幸运的是，在Markdown中实现并不难，具体语法与链接相似：  
\[标题](#要引用的标题内容) **注：标题内容不区分大小写**
示例：

```markdown
## section
- [test](#test)
```
如上，就可以定位到test标题的位置了。  
效果：（点击一下试试看吧！！！）

### return
## section
- [test](#tes)


---

- ## 扩展

### 1.分隔线

Markdown中,可以在一行中使用三个或更多的 *、- 或 _ 来添加分隔线 要注意与文本之间要有空行:

```Markdown
---
```
效果:

---

### 2.删除线

Markdown使用~~来作为删除线，使用方法如下：
代码：

```markdown
这是 ~~要删除的文本~~
```

效果：  
这是 ~~要删除的文本~~

### 3.字符转义

> 反斜线（\）用于插入在 Markdown 语法中有特殊作用的字符。
例如：

```markdown
这是用来 *演示* 的 _文本_
这是用来 \*演示\* 的 \_文本\_
```

效果：  
这是用来 *演示* 的 _文本_  
这是用来 \*演示\* 的 \_文本\_

---
# 演示用
## test
返回：

- [return](#return)


---

## 写在最后

以上，就是Markdown的基本语法了，这些东西熟练掌握后，写几篇个人博客就完全是手到擒来了。

虽然简单，还是要写几篇博客来练习加深记忆，写博客的过程就是学习的过程，不管你写的是什么，哈哈，这是一位大佬跟我说的。这也是我的第一篇博客，接下来我也希望自己能坚持并养成写博客的这个习惯。

如果看完了，就赶紧去写你自己的一篇博客吧！

## 参考
- [Learning-Markdown](http://xianbai.me/learn-md/index.html)
- [Introduction To Markdown Using Visual Studio Code](https://www.youtube.com/watch?v=pTCROLZLhDM)