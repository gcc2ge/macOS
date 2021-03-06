# macOS 系统的安装

## 安装之前

重装之前，使用时光机器(Time Machine)，将所有硬盘资料备份到移动硬盘上。这个也可以方便地作为系统快照，恢复之前某个时刻的机器的状态。数据无价，Time Machine是Mac最有价值的功能之一，一次设置，终生受益。不管是更换机器，重新安装系统，丢失机器，还是硬件损坏，Time Machine都是你最后的保障。

覆盖安装和全新安装（即抹盘安装），默认是覆盖安装。你可以在安装界面使用磁盘工具将系统盘抹掉，这样安装以后就是一个完全干净的系统，但是你的数据和程序也将完全清除。你也可以选择覆盖安装，安装之前无需将系统盘抹掉，这样不会丢失程序和数据，但是可能引起冲突、不一致等问题。

安装时，请将语言选为English，不要使用中文界面。碰到问题的时候，使用英文关键词，在互联网查找、搜索，可以比中文关键字获得更加准确和丰富的信息。

## 网络安装 or 本地安装

Mac OS X支持网络安装和本地安装。网络安装，就是直接使用command+R，进入恢复模式，然后从互联网下载操作系统进行安装，整个过程自动、方便。安装的时候，注意只能使用wifi网络，并且仅支持WPA/WPA2加密方式，不支持WEP加密方式。

本地安装，就是预先下载安装镜像，制作安装盘，直接从本地安装盘安装。这样时间进度可控，出现问题的风险小。以后进行重新安装和恢复的时候，再也不用重新从网络长时间等待下载，整个安装过程一般在半个小时内完成。

苹果缺省的安装方式是网络安装，但是我们推荐使用本地安装方式。因为网络安装的方式在美国可能很适合，安装速度很快，但是中国大陆需要从境外服务器下载。Yosemite（10.10）安装镜像有5.2G大，即使你的网速有100Mbps或者更高，你也经常会发现网络安装的过程是一个痛苦的体验，往往看着安装进度条蜗牛一般前进，提示还有上百小时才能下载完毕。

## DNS

8.8.8.8

114.114.114.114

## 制作安装盘

### 分区

准备一个U盘或移动硬盘（大于等于6G），建议使用USB 3或者雷电高速接口。最好使用移动硬盘作为介质，速度比U盘快，同时可以将移动硬盘作为时光机器和恢复磁盘助手(Recovery Disk Assistant)。

首先在磁盘工具内的"Options"里，选择GUID，否则无法启动，然后在"Partision Layout"将移动硬盘分成三个分区：

* 分区名字Yosemite，大小8G，格式是Mac OS Extended(Journaled)，本地磁盘安装介质的制作，方便以后安装系统
* 分区名字recovery，大小2G，格式是Mac OS Extended(Journaled)，恢复助手，用于对系统进行恢复
* 分区名字data，剩余的磁盘空间，格式是Mac OS Extended(Journaled)，数据备份和时光机器的介质

### 制作安装盘

你可以从Mac App Store下载安装镜像

    https://itunes.apple.com/us/app/os-x-yosemite/id915041082?mt=12

从App Store完成下载后，OS X Yosemite安装程序会自动启动，不要点击继续，停在安装界面第一页。插入刚才分区好的移动硬盘或者U盘，在命令行输入下面的命令，制作安装盘

    sudo /Applications/Install\ OS\ X\ Yosemite.app/Contents/Resources/createinstallmedia --volume /Volumes/Yosemite --applicationpath /Applications/Install\ OS\ X\ Yosemite.app --nointeraction


等待创建完成，你就拥有了一个安装启动盘，以后都可以用来安装恢复系统。

### 制作恢复盘

苹果提供OS X Recovery Disk Assistant工具，这个工具将在本地磁盘制作一个恢复分区。下载地址：

    http://support.apple.com/kb/dl1433
    
## 安装OS X

安装盘制作完毕后，重启并按Option键，选择安装盘安装。安装或者恢复之前，一般使用时光机器进行备份，然后用磁盘工具删掉之前的机器磁盘上的内容。
(安装一般需要30分钟左右)

## 安装以后

* 更改安全设置

允许从所有来源安装应用程序，在Security and Privacy里设置"Allow apps downloaded from" 选项为"Anywhere"

* 更改触摸板默认设置

在"Trackpad"里打开"Tap to click"设置
