<h1 align="center">Yoga14sACH2021_Hackintosh</h1>

  <p align="center">
    <a href="https://github.com/mortal0110/Yoga14sACH2021_Hackintosh/graphs/contributors" style="text-decoration: none;">
      <img alt="GitHub Contributors" src="https://img.shields.io/github/contributors/mortal0110/Yoga14sACH2021_Hackintosh" />
    </a>
    <a href="https://github.com/mortal0110/Yoga14sACH2021_Hackintosh/issues" style="text-decoration: none;">
      <img alt="Issues" src="https://img.shields.io/github/issues/mortal0110/Yoga14sACH2021_Hackintosh?color=0088ff" />
    </a>
    <a href="https://github.com/mortal0110/Yoga14sACH2021_Hackintosh/pulls">
      <img alt="GitHub pull requests" src="https://img.shields.io/github/issues-pr/mortal0110/Yoga14sACH2021_Hackintosh?color=0088ff" />
    </a>
  </p>


Step-by-Step Guide on How to Install macOS on Yoga 14s ACH2021（手把手教你如何在yoga14s ACH2021上安装黑苹果）

> README文件仅为汇总，详细内容请在wiki中查看或者点击标题跳转对应wiki。

# [电脑配置](https://github.com/TychoSuen/Yoga14sACH2021_Hackintosh/wiki/电脑配置)

|   规格   | 详细信息                                               |
| :------: | ------------------------------------------------------ |
| 电脑配置 | Yoga14sACH2021                                         |
| 操作系统 | Windows10 20H2 + MacOS Ventura                         |
|  处理器  | AMD Radeon Graphics 八核 7nm                           |
|   内存   | 16GB（三星 DDR4 3200MHz 8GB $\times$ 2）               |
|   主板   | 联想 LNYNB161216（AMD PCI 标准主机 CPU 桥）            |
|  主硬盘  | 西数 WDC PC SN730 SDBPNTY-512G-1101（512G / 固态硬盘） |
|   显卡   | AMD Radeon Graphic （2 GB / 联想）                     |
|  显示器  | 联想 LEN8A90（14英寸）                                 |
|   声卡   | 瑞旻 High Definition Audio                             |
|   网卡   | Intel Wi-Fi 6 AX200 1600MHz #2                         |
| 官方BIOS | GZCN37WW                                               |

# [完善度](https://github.com/TychoSuen/Yoga14sACH2021_Hackintosh/wiki/完善度及兼容性#完善度)

测试环境 MacOS Ventura

| 功能           | 是否可用                          | MacOS    | 是否可用 |
| -------------- | --------------------------------- | -------- | -------- |
| 电源           | ✅                                 | iCloud   | ✅        |
| 蓝牙           | ✅                                 | 接力     | ✅        |
| 显示器亮度调节 | ✅                                 | 隔空投送 | ❌        |
| 刷新率         | ✅(90Hz)                           | 台前调度 | ✅        |
| 无限网卡       | ✅                                 | 屏幕镜像 | ❌        |
| 触摸板         | ✅                                 |          |          |
| USB接口        | ✅                                 |          |          |
| 外放           | ✅                                 |          |          |
| 摄像头         | ✅                                 |          |          |
| 麦克风         | ✅                                 |          |          |
| 睡眠           | ✅(关盖睡眠需要时间以及唤醒很迅速) |          |          |

> ✅仅表示在正常使用环境下经过测试可以正常使用

# [Geekbench 6比较](https://github.com/TychoSuen/Yoga14sACH2021_Hackintosh/wiki/完善度及兼容性#geekbench-6比较)

| 系统          | 项目 | 分数                                                         |
| ------------- | ---- | ------------------------------------------------------------ |
| Win 10        | CPU  | [Single-Core: 1930 Multi-Core: 7096](https://browser.geekbench.com/v6/cpu/10328820) |
| MacOS Ventura | CPU  | [SIngle-Core: 1542 Multi-Core: 7029](https://browser.geekbench.com/v6/cpu/10329321) |
| Win 10        | GPU  | [16674](https://browser.geekbench.com/v6/compute/3611974)    |
| macOS Ventura | GPU  | [13093](https://browser.geekbench.com/v6/compute/3611837)    |



# [DiskMark比较](https://github.com/TychoSuen/Yoga14sACH2021_Hackintosh/wiki/完善度及兼容性#diskmark比较)

| 系统 | Win 10                                                       | MacOS Ventura                                                |
| ---- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| 分数 | <img src="./assets/AS%20SSD%20Benchmark%20win10.png" alt="AS SSD Benchmark win10" style="zoom:30%;" /> | <img src="./assets/image-20250205222601149.png" alt="image-20250205222601149" style="zoom:35%;" /> |
| 工具 | AS SSD Benckmark                                             | AmorphousDiskMark                                            |

# [镜像制作以及安装工作](https://github.com/TychoSuen/Yoga14sACH2021_Hackintosh/wiki/黑苹果教程)

该项内容建议在网络中搜索进行学习，此项目中该部分并不完善。

<p style = 'color: red; font-weight: bold;'>请注意：数据无价, 谨慎操作！ </p>

> - [EFI各文件介绍1](https://yuexiang.fun/1231.html)
> - [EFI各文件介绍2](https://blog.xjn819.com/post/opencore-guide.html)

# [收尾工作/美化](https://github.com/TychoSuen/Yoga14sACH2021_Hackintosh/wiki/黑苹果教程#完善以及美化工作)

## [黑成白苹果](https://github.com/TychoSuen/Yoga14sACH2021_Hackintosh/wiki/完善以及美化工作#黑成白苹果)

我们通过使用bootcamp达成不通过使用oc界面在win与mac之间进行切换。

> 安装bootcamp可能会导致电脑上的exFAT分区被隐藏，并且可能无法修改，请注意提前备份。

## Windows、Mac文件互传

这是本项目中最为简单的部分，打开`DiskGenuis`，释放出一部分空间并将此空间格式化为`exFAT`格式、添加驱动器号。

> exFAT格式下的文件Windows和Mac都可读可写，如果有U盘经常在双系统下使用建议也格式化为exFAT格式。

## [使用部分联想管家功能](https://github.com/TychoSuen/Yoga14sACH2021_Hackintosh/wiki/完善以及美化工作#使用部分联想管家功能)

### 生效功能

|        功能        |                    是否生效                     |
| :----------------: | :---------------------------------------------: |
| Fn功能键开启与关闭 |       ✅( 键盘上第一行的功能键几乎能工作 )       |
|  键盘灯启动与关闭  | ✅(`Fn+Space`可以进行切换，Pane中不可以进行切换) |
|    性能模式切换    |        ✅(`Fn+Q`不行，Pane中可以进行切换)        |
|     CapsLk 锁      |      ✅(单击用于切换键盘，长按可以锁定大写)      |
|     刷新率切换     |          ❌(Fn+R不行，在MacOS默认90Hz)           |

### 副作用

- ~~可能会导致`系统设置-键盘-键盘快捷键-修饰键`不能进行自定义~~
- ~~在Windows下切换性能模式可能会导致重启到Mac时Pane不能切换性能模式~~

## Apple ID设置中机型图标不显示

方法1：退出Apple ID重启电脑再登陆Apple ID

方法2：重新[更改三码](https://github.com/TychoSuen/Yoga14sACH2021_Hackintosh/wiki/完善以及美化工作#更改三码)即可



 # 参考文档

- https://blog.xjn819.com/post/opencore-guide.html

- https://yuexiang.fun/1231.html

- https://github.com/daliansky/XiaoXinPro-13-hackintosh/issues/139#issue-970836873

- https://heipg.cn/tutorial/basic-install-hackintosh-walkthrough.html

- https://zhuanlan.zhihu.com/p/578312673

- https://hpglw.com/95d74e2e.html

# 鸣谢

[@黑成白苹果](https://m.tb.cn/h.TLeFr0V?tk=3Teieg6xuXt)

# 建议及声明

由于测试环境有限，部分功能在我的电脑下可以实现不代表适用于所有电脑；如有问题可以提交issues，不保证能够解决。

<p style = 'color: red; font-weight: bold;'>本项目仅用于学术研究与技术交流，任何因使用本项目代码或相关内容引发的法律责任或其他后果，作者不承担任何责任。
</p>
