<!-- 链接 -->
[m_meihua_tou]:https://github.com/ZT-XU/myblog/raw/master/Manjaro_yh/meihua.png
[peizi]:https://github.com/ZT-XU/myblog/raw/master/Manjaro_yh/peizi.png
[kjj]:https://github.com/ZT-XU/myblog/raw/master/Manjaro_yh/kjj.png

# Manjaro 美化与调优

> 之前说过要写一篇Linux的优化文章，今天正好有空，赶紧开工。我曾经是Ubuntu的忠实粉丝，但是如今我已经叛逃到Manjaro了。

> 为什么是Manjaro？  
> 首先，Manjaro是基于Arch Linux的！！！所以基本Arch上的操作（强大的Arch wiki）都可以应用到Manjaro上.  
> 其次，Manjaro基于Arch开发，将Arch安装过程中很多复杂的操作（特别是驱动）都先帮你弄好了，所以安装不会像Arch那么复杂，反而和Ubuntu安装过程一样简单。  
> 最后，用了Manjaro我们也可以和大佬们一样高呼“Arch 大法好了”，软件丰富，安装简单，基本一条命令就搞定，不需要像Ubuntu一样（可能）需要安装依赖！  

和之前一样，我会从刚装完Manjaro的电脑开始，本文分为三部分，第一部分说一下刚装好Manjaro之后的一些配置和必要的软件安装，第二部分讲一下Manjaro的美化操作（太丑了，强迫症受不了啊），第三部分讲一些优化操作还有软件安装。

> 注： Manjaro根据不同的桌面环境有不同的版本，我的是Gnome版本。

## 安装Manjaro之后要做的几件事

### 一、更换源

Manjaro换源很简单  
`sudo pacman-mirrors -i -c China -m rank`
`sudo pacman -Syy`  
这个会显示最快的几个源，选最快的那个就行，我选的是中科大的源。
>这样其实就可以了，但是我安装某些软件的时候比如chrome（yay可以解决，但是太慢了），pacman是找不到的，所以推荐修改配置文件，并安装GPG key，这样就可以用pacman安装一些常用的软件了，具体原因我也不清楚，还希望有大佬可以解答一下。

修改`/etc/pacman.conf`,在最后一行添加：

```bash
[archlinuxcn]
SigLevel = Optional TrustedOnly
Server = https://mirrors.ustc.edu.cn/archlinuxcn/$arch
```

然后，命令行运行：  
`sudo pacman -S archlinuxcn-keyring`  
`sduo pacman -Syy`  

### 二、卸载Manjaro自带的一些没用的软件

Manjaro自带了一些我们不需要的软件，留着他们一点都不优雅。  

#### **steam**  

不知道Linux的steam能来干嘛？卖萌吗？软件包管理器搜索steam，将`steam-gnome`卸载。  

#### **office**  

Manjaro自带了两个office，都没有WPS好用，果断卸载。软件包管理器搜索office，将`Libre-office`和`ms-office-online`卸载。  
其他的比如还有发邮件的（忘记什么名字了），uget，qtorrent 对我没用，我也都卸载了，你可以自己在软件包管理器里看哪些没用卸载，其实不管也行，我就是强迫症。。。
> ！！！：卸载的时候要谨慎，带Gnome的还有qt的千万不要卸载，依赖关系太多的也不要卸载，不要问我怎么知道的。。。  

卸载之后就可以更新一下软件了  
`sudo pacman -Syyu`  

## 三、常用软件

### yay

以后可以用yay来代替pacman安装软件

`sudo pacman -S yay base-devel`

### 搜狗输入法

```bash
sudo pacman -S fcitx-im #全部安装
sudo pacman -S fcitx-configtool
sudo pacman -S fcitx-sogoupinyin
```

配置fcitx并重启使其生效

### 谷歌浏览器

`sudo pacman -S google-chrome`  

### vim

`sudo pacman -S vim`

### git

`sudo pacman -S git`

### vscode

`sudo pacman -S visual-studio-code-bin`

### VLC视频播放器

`sudo pacman -S vlc`

### Albert 软件启动神器

`sudo pacman -S albert`
> 设置中设置快捷键，开机启动，extension中勾选application和files。

### 网易云音乐

`yay -S netease-cloud-music`

### wps

`yay -S wps-office`  
`yay -S ttf-wps-fonts`

### 四、美化

Manjaro默认太丑了，不能忍。。。

#### 主题

我选择arh主题，这个主题很漂亮，搭配copernico这个透明的shell-theme，美化效果见下图：  

![美化][m_meihua_tou]  

安装：  
`yay -S gtk-theme-arc-git`  
`yay -S gnome-shell-theme-copernico-git`  
然后在tweak中选择这两个主题，再去网上找一张好看的壁纸，最后在dash to dock中配置一下（选择在下方并设置透明），就大功告成啦！！！

#### Gnome 插件

> 需要在谷歌浏览器中安装Gnome shell extension插件

Manjaro自带不少Gnome拆件，有些好用有些没用，这里给大家看看我的Gnome拆件列表，大家可以做个参考（一些自带的没有出现就表明我弃用它了）：  

- **Activities configurator**  
可以优化顶栏，去掉一些没用的提示，我的配置如下：  
![配置][peizi]

- **Coverflow Alt-Tab**  
  alt-tab 切换效果美化
- **GnomeStatsPro**  
  系统监视器
- **simple net speed**  
  显示实时网速
- **Status Area Horizontal Spacing**  
  使顶栏更加紧凑
- **Window is ready**  
  去掉Window is ready 这个的无用提示
- **(K)StatusNotifierItem/AppIndicator Support** （系统自带）  
  可以在顶栏显示后台程序图标tu
- **Pamac Updates Indicator** （系统自带）  
  提醒软件更新状态
- **User Themes** (系统自带)
  让用户可以使用shell主题
- **dash to dock** (系统自带)

### 五、调优

#### 设置`alt + ctrl + T` 启动终端

打开`设置`，在`设备`中选择`keyboard`，拉到最下，添加快捷键，如下图：

![快捷键][kjj]

#### 大号文本

在`设置` -> `通用辅助功能` 中开启`大号文本`

#### 优化vim

因为已经有vscode了，可以用code命令代替vim（需要sudo的还是要用vim才行），所以vim对我来说就是一个普通的文本编辑器了，写代码也基本在vscode上进行（现在vscode实在太好用了）。虽然如此，默认vim用起来还是很蛋疼的，需要进行一些优化，我的vim配置基本都是一些简单的美化插件，只作为一个普通的文本编辑器的话足够了，如果你和我一样只是想用vim做一些简单的编辑，可以参考我的vim配置：
<https://github.com/ZT-XU/666>
> 差不多就这些了，后面有想到其他的点再更新！！！

