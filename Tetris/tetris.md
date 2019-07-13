# 项目实战：简易俄罗斯方块

![bg](https://github.com/ZT-XU/myblog/raw/master/Tetris/bg.png)

## 前言

学了java，一直想找一个项目实战，俄罗斯方块就是一个不错的实战项目，它原理实现比较简单。话虽如此，我一开始还是毫无头绪，直到去油管上看一个俄罗斯方块的视频和在GitHub上看他实现的源码，才有了思路。我基于他的程序做了一些加工，做出了下面的半成品。俄罗斯方块还是比较适合新手练习的，我将在下面分享一些我在做这个项目的一些技巧和体会，欢迎讨论！

![](https://github.com/ZT-XU/myblog/raw/master/Tetris/playing2.png)

![](https://github.com/ZT-XU/myblog/raw/master/Tetris/GAMEOVER.png)

## 准备

我使用的不是swing而是比较新的javafx，但事实上，javafx我也只是学我需要用到的地方，所以如果你用过swing，上手javafx制作一个俄罗斯方块还是比较快的，毕竟我们只需要javafx很少的比较常用的API。

## 设计思路

俄罗斯方块有如下七种形状：

![](https://github.com/ZT-XU/myblog/raw/master/Tetris/7.jpg)

它们的名称为：O, J, L, Z, S, T, I（把字母和图形对比一下你就知道为什么这么叫了）。其次，每个方块最多有4种变换形态。下面是我在一篇博客看到的所以变换：

![](https://github.com/ZT-XU/myblog/raw/master/Tetris/turn.png)

首先，是设计类来表示这七种形状，这里我一开始是想用七个类继承一个基类来实现，后来发现不如一个类写一起比较简单，具体思路是设计出一个形状类，它具有name等属性，而当程序在new的时候，name会随机选择七个name中的一个，然后后续的方法和操作则以这个name为依据。形状类初始化和翻转方法会因为其name的不同而不同。部分代码如下：

![](https://github.com/ZT-XU/myblog/raw/master/Tetris/code1.png)

![](https://github.com/ZT-XU/myblog/raw/master/Tetris/code2.png)

之后，我们生成一个二维数组作为零一矩阵来表示形状当前的位置，形状移动时，除了检查不要越过边界之外，还需要检查移动是否会碰到其它形状，这就是我们这个二维数组的作用了，应该很容易理解。

形状的移动方法有三种：右移，左移，和下移。前面两个实现起来比较简单，最后一个因为需要考虑到比较多的因素而比较复杂。在这里，我需要对下一个形状进行预测，这就意味着我必须在当前控制的形状无法移动是，交换控制权给下一个形状。所以实际上每个时刻最上方有两个形状生成，只不过其中一个是静止并且不可见的。当切换控制权之后，就必须检查是否需消行了，部分代码如下：

![](https://github.com/ZT-XU/myblog/raw/master/Tetris/code3.png)

后面就是我觉得比较难的消行操作了，如果处理不好会出现很多奇怪的bug，我实现现总体思路如下：
先检查整个二维数组，找到可以消的“行”，然后将所有需要消除的行记录并消除，消除之后，将没有消除的方块下移对应的距离，最后再更新二维数组。

## 总结

以上，就是总体的设计和实现思路了，剩下的界面其它元素设计和其它细节设计都比较简单，就不再累述，最后分享一下我看的油管视频的链接以供参考，以及我的项目源码。

## 链接

### 我参考的视频：

<https://www.youtube.com/watch?v=boAJUSN8fOU&t=1284s>

### 我的项目源码：

<https://github.com/ZT-XU/Tetris>