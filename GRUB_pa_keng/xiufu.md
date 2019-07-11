[zhuyetu]:https://github.com/ZT-XU/myblog/raw/master/GRUB_pa_keng/light.jpg
[cs]:https://github.com/ZT-XU/myblog/raw/master/GRUB_pa_keng/%E5%BE%AE%E4%BF%A1%E5%9B%BE%E7%89%872.jpg
[qk]:https://github.com/ZT-XU/myblog/raw/master/GRUB_pa_keng/%E5%BE%AE%E4%BF%A1%E5%9B%BE%E7%89%871.jpg

![p][zhuyetu]

# 记录：解决双系统 Windows 10 更新后进入grub rescue 模式

## 前言


在今天更新windows 10 1903 的时候在重启的时候发现电脑找不到boot直接进入到了grub rescue模式，老实说，我已经不是第一次遇到这种情况了，所以再解决这个问题之后记录一下，以防下次再遇到同样的情况。

## 解决

首先，遇到这种情况其实只要在开机时按F12（不同品牌的电脑可能不同）进入boot选项菜单然后进入系统即可，但是每次开机都要按F12未免太过麻烦，所以解决方法如下：

我先进入到windows 10完成更新，在设置中**关闭windows 10 快速启动**，然后重新启动。不出意外进入到了grub rescue模式，然后用`ls`命令输出gpt分区，我忘记我当初manjaro安装在哪个分区了，所以只能一个一个去试，输入`ls (hd0,gptx)\boot\grub`,如下图:

![cs][cs]

如果有输出路径信息，说明对应的`(hd0,gptx)`就是grub启动的分区。我这里是(hd0,gpt8)。
之后依次输入`set root=(hd0,gpt8)`, `set prefix=(hd0,gpt8)/boot/grub`，`insmod normal`, `normal`。

![qk][qk]

输入之后我就可以看到之前的grub启动菜单了，进入我的Linux系统，打开终端，再输入`sudo update-grub`, `sudo grub-install /dev/sda`, 最后重启系统，就可以看到grub启动菜单了，问题解决！！！
