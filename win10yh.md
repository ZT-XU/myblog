
[win10before]:https://raw.githubusercontent.com/ZT-XU/myblog/master/win10yh/Windows-10-S.jpg
[win10meihua]:https://raw.githubusercontent.com/ZT-XU/myblog/master/win10yh/win%E7%BE%8E%E5%8C%96.png
[wallpaper]:https://github.com/ZT-XU/myblog/raw/master/win10yh/wallpaper.png
[gjl]:https://raw.githubusercontent.com/ZT-XU/myblog/master/win10yh/%E5%B7%A5%E5%85%B7%E6%A0%8F.png
[rwl1]:https://github.com/ZT-XU/myblog/raw/master/win10yh/%E4%BB%BB%E5%8A%A1%E6%A0%8F1.png
[rwl2]:https://github.com/ZT-XU/myblog/raw/master/win10yh/%E4%BB%BB%E5%8A%A1%E6%A0%8F2.png
[rwl3]:https://github.com/ZT-XU/myblog/raw/master/win10yh/%E4%BB%BB%E5%8A%A1%E6%A0%8F3.png
[rwl4]:https://github.com/ZT-XU/myblog/raw/master/win10yh/%E4%BB%BB%E5%8A%A1%E6%A0%8F4.png
[rwll]:https://github.com/ZT-XU/myblog/raw/master/win10yh/rwll.png
[kscd]:https://github.com/ZT-XU/myblog/raw/master/win10yh/kscd.png
[zyglq]:https://github.com/ZT-XU/myblog/raw/master/win10yh/zyglq.png
[wddn]:https://github.com/ZT-XU/myblog/raw/master/win10yh/wddn.png

# Winodws10 美化与调优

## 写在文前

最近重装了自己的win10系统，对自己的系统进行了美化调优，目前基本用得还是很舒服的，所以这篇博客决定来做一些分享，分享一些使用Windows的心得（将来可能也会写一些Linux系统的文章）。  
我个人是不喜欢折腾+具有“软件洁癖”的类型，所以这次分享的操作大体上都会比较简单，不会涉及到复杂的注册表操作，安装的软件能少装就不装，我也会在文章最后推荐一些我个人觉得很好用的Windows（绿色）软件。  
> 我将从刚刚重装完成的电脑开始，介绍一些基础的操作让它更加好用，虽说如此，这些操作你都可以在自己的电脑上进行。

## 美化

重装好Windows10后，系统的默认界面是这样的：  
![win10before][win10before]  
美化之后：  
![win10meihua][win10meihua]  

### 一、桌面

对电脑桌面颜值影响最大的就是壁纸了，好看的壁纸能让我们在使用电脑时心情舒畅。好看的壁纸可以在网上搜索找到，但如果你和我一样喜欢动态壁纸的话，推荐**wallpaper engine**：  
![wallpaper][wallpaper]  
一个只专注于动态壁纸的软件，简单易用，steam上售价18RMB，一顿饭钱，就可以用到各种炫酷的动态壁纸，相信我，你会爱上这个软件的。

### 二、任务栏

我比较喜欢Mac os的dock外观，所以接下来，就是对任务栏进行美化了。首先，右键单击任务栏空白处，将红框部分全部取消勾选：

![rwll][rwll]

在桌面新建一个空文件夹，然后右键单击任务栏空白处，并选择「新建工具栏」，在弹出的窗口中选择你刚才新建的那个文件夹。

![gjl][gjl]

![rwl][rwl1]

随后，右键任务栏取消勾选`任务栏锁定`向左一直拖动新建文件夹，直到应用程序图标**被挤压到右边**，并将应用程序栏（就是程序图标前那个）拖拽到你喜欢的位置：

![rwl2][rwl2]

![rwl3][rwl3]

然后取消勾选新建工具栏的`显示文本`及`显示标题`属性，再次`锁定任务栏`，删除新建文件夹:

![rwl4][rwl4]

然后在桌面上选择你最常用得5到6个软件固定到任务栏，再右键单击桌面空白处，在`查看`中取消勾选`显示桌面图标`，一个仿dock的任务栏就完成了。桌面美化大功告成！

![win10meihua][win10meihua]
> 任务栏透明化: 在微软商店中，搜索安装Translucent TB并启动，设置开机启动：右键程序图标，勾选"Open at boot", 然后在前5个菜单项中选择clear即可。

## 调优

### 一、开始菜单

隐藏桌面后，我选择使用任务栏 + 开始菜单来代替桌面的快捷方式，任务栏放5到6个最常用的软件，其他的软件快捷方式就放在开始菜单那里。

![kscd][kscd]

> 我发现很多小伙伴并不知道开始菜单右边那些区域是可以用来整理快捷方式的，像office，回收站，我的电脑，控制面板这些放在这里简直不要太方便好吗。

### 二、优化小娜

Win10的小娜其实可以用来作为Linux下`Albert`那样的工作，只不过，需要进行一些优化（禁止搜索网页从而提高速度），优化教程可以参考：  
[小娜优化](https://jingyan.baidu.com/article/48206aead0fd57216ad6b328.html)  
之后，就可以使用`win + s`键搜索启动应用了。

### 三、文件资源管理器

固定在程序栏的文件资源管理器一直是很蛋疼的存在，点击打开之后是快速访问，但基本没有我想要看到的东西，所以把它打开的位置定位为我的电脑，方法如下图：

![zyglq][zyglq]

这样，点击资源管理器之后，就相当于我的电脑了，在我的电脑上面的菜单栏上，基本涵盖了右键点我的电脑的菜单项，卸载软件的选项也在这里哦！

![wddn][wddn]

## Windows好用的软件

文章最后，推荐几个我认为在Windows上非常好用得软件。

### Snipaste

给力的截图软件，在微软商店即可安装。

### Vscode

宇宙第一编辑器，下载地址：<https://code.visualstudio.com/download>

### EveryThing

超强的文件搜索软件，搜索速度非常快，完爆Windows自带的，力荐！
下载地址：<https://www.voidtools.com/zh-cn/downloads/>

### 火绒安全

完爆360、腾讯管家，超级良心的电脑杀毒软件，还带有广告窗口拦截等功能，力荐! 下载地址：<https://www.huorong.cn/>

### Uninstall Tool

可以卸载系统检测不到的一些软件，下载地址：<https://www.crystalidea.com/uninstall-tool/download>

### Anydesktop

自带传输协议的电脑远程访问工具，支持Mac os、Windows、Linux三大平台，超强！下载地址：<https://anydesk.com/download>
