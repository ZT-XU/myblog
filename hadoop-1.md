<!-- 链接 -->

# Hadoop学习笔记（1）

## 使用docker搭建分布式环境  

> 今天开始，准备学习大数据分析，参考的教材是O‘REILLY的[《Hadoop数据分析》](https://book.douban.com/subject/30180515/),算是一本比较新的书吧！我自己也属于刚入门，写笔记除了分享，更重要的是可以提高学习的效果！！  

>这里我使用的是docker而不是书上推荐的在vmware上安装虚拟机，至于为什么抛弃vm而选择docker，当然是docker更加轻量级更加好用，docker可以说是当今虚拟化技术的潮流，当然想更具体的优点可以去查阅相关资料，这里就不再累述。

下面先说明一下我的环境配置：

- **系统：Manjaro Linux**
- **Docker version：18.09.2-ce**
- **安装docker（Arch 真爽啊）：**  
  `sudo pacman -S docker`
- **更换docker源（使用ustc源）：**
  `sudo gedit /etc/docker/daemon.json`  
  然后把下面的内容加入，即可：

```json
{
  "registry-mirrors": ["https://docker.mirrors.ustc.edu.cn"]
}
```
- **把自己加入`docker`用户组，这样就运行docker时就不用加`sudo`了**：

```sh
echo "hello"
sudo groupadd docker
sudo usermod -aG docker $USER
```

然后重启即可。

### 搭建分布式环境

>书中搭建的环境是伪分布式的，也就是单机，但是为了将来更深入地学习云计算和大数据，我在这里搭建的是全分布式的环境，搭建方法非常简单，得益于一个大佬在docker hub上发布了已经配置好的开发环境，使我们不用被繁琐的配置步骤所困扰，很快地学习Hadoop的核心部分。

首先，我们先到docker hub上拉去相关的镜像，你也可以自己一步步拉，从操作系统到Hadoop再到jdk一个个地拉，然后自己配置，如果闲麻烦（like me），直接拉大佬已经配置好的镜像就行了，方法很简单，运行命令：  
`sudo docker pull kiwenlau/hadoop:1.0`

然后克隆大佬的配置库：
`git clone https://github.com/kiwenlau/hadoop-cluster-docker`

>这是我用来测试环境，我们的目的是学习，所以我后面会再自己写hadoop的配置熟悉一下。

创建Hadoop网络：

`sudo docker network create --driver=bridge hadoop`

这个很重要，使用桥接网络我们才可以模拟分布式集群。

下面先热一下身：
启动docker容器：
`cd hadoop-cluster-docker`
`sudo ./start-container.sh`

>通过结果你也可以知道，这个环境包含了1个`master`，2个`slaver`，对于我们学习完全够用了。

这是我们会进如`master`的根目录下，运行自带的WordCount程序热身一下先吧：  
`./start-hadoop.sh`  
`./run-wordcount.sh`

以上就是这篇笔记的内容，后续会继续深入学习，待更。。。

## 写在最后

今天开始会开始学习Hadoop数据分析，在搭好环境之后对docker更加喜爱了，如果将来有机会，也会写一些docker的文章。目前先啃好这本书，上面的内容基本与书上无关，所以后面就是Hadoop实践部分了。开学了，希望可以保持一月一更，甚至一月多更。

## 参考

- <https://kiwenlau.com/2016/06/12/160612-hadoop-cluster-docker-update/>
- <https://docs.docker.com/get-started/>
