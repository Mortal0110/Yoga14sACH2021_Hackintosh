# Yoga14sACH2021_Hackintosh

Step-by-Step Guide on How to Install macOS on Yoga 14s ACH2021（手把手教你如何在yoga14s ACH2021上安装黑苹果）

# 电脑配置

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
| 官方BIOS |                                                        |

# 完善度

测试环境 MacOS Ventura

| 功能           | 是否完善                          |
| -------------- | --------------------------------- |
| 电源           | ✅                                 |
| 蓝牙           | ✅                                 |
| 显示器亮度调节 | ✅                                 |
| 无限网卡       | ✅                                 |
| 触摸板         | ✅                                 |
| USB接口        | ✅                                 |
| 外放           | ✅                                 |
| 麦克风         | ✅                                 |
| 睡眠           | ✅(关盖睡眠需要时间以及唤醒很迅速) |

> ✅仅表示在正常使用环境下经过测试可以正常使用

# 镜像制作以及安装工作

该项内容可以在网络中搜索进行学习（后续考虑补充）

## 镜像下载以及U盘制作

转载自老吴黑苹果 [网盘链接(内有MacOSVentura镜像以及U盘制作教程)](https://www.alipan.com/s/Ln643E4FQPu)

## EFI配置说明

- [EFI各文件介绍1](https://yuexiang.fun/1231.html)
- [EFI各文件介绍2](https://blog.xjn819.com/post/opencore-guide.html)

# 收尾工作

## 黑成白苹果

### 目标

我们通过使用bootcamp达成不通过使用oc界面在win与mac之间进行切换。

### 安装

Bootcamp可以在google直接搜索下载，注意不同的系统对应不同的版本；下载完成后将文件放在任意你想放的位置，双击`setup.exe`进行安装；安装完成后运行。

### 切换

Win切换Mac：在任务栏右下角找到图标，右击`切换到MacOS`即可。
Mac切换Win：低版本mac可以在左上角找到`系统偏好设置--启动磁盘`，高版本mac在`设置-通用-启动磁盘`，在进入启动磁盘后选择Win所在盘点击`重新启动`即可（需要输入密码）。

### 关闭OC引导

在Win或者Mac中打开`config.plist`文件（打开方式可参照问题2），在`Misc`中取消勾选`Show Picker`，然后在`UEFI--UEFI驱动`中取消勾选`OpenCanopy.efi`，保存即可。

> bootcamp安装过程中常见问题：
> 1、运行`setup.exe`提示“版本不适用”：进入`driver--apple--bootcamp.msi`运行即可（如果提示仍然要从`setup.exe`进行安装请参照2）
> 2、运行`setup.exe`提示“版本不适用”：在Win端用OCAT打开`efi--oc--config.conf`或者在Mac端用opencare打开相同文件，找到左侧`PI`、勾选`spoofvendor`、然后找到`UpdateSMBIOSMode`、选择 `creat`、然后找到`Kernel`、点击`选项`、然后把`CustomSMBIOSGuid `去掉勾选、保存、然后重新安装bootcamp，此时如果运行`setup.exe`提示缺少winpedrive之类的文件夹，在bootcamp同级文件夹下创建空文件夹即可。
>
> 注意：Bootcamp的最高适配系统为Win10

## 使用部分联想管家功能

### [使用方式](https://github.com/daliansky/XiaoXinPro-13-hackintosh/issues/139#issue-970836873)

- 下载 [ECEnabler.kext](https://github.com/1Revenger1/ECEnabler/releases)
  - 得到 `ECEnabler.kext` 放入 `OC/Kexts` 并在 `config.plist` 中引入。
- 下载 `YogaSMC-App-Release.dmg`
  - 双击选择安装， 然后再双击安装 `YogaSMCPane.prefPane` 控制面板，安装后在 `系统偏好设置` 最后一行找到。
- 下载 [YogaSMC-Release.zip](https://github.com/zhen-zen/YogaSMC/releases)
  - 解压 得到 `YogaSMC.kext` 放入 `OC/Kexts` 并在 `config.plist` 中引入。
- 在 上面的 `YogaSMC-Release.zip` 中
  - 解压后同时会得到 `SSDTSample/*.dsl` ,
  - 使用 [MaciASL.app](https://github.com/acidanthera/MaciASL/releases) 分别打开 `SSDT-ECRW.dsl`、`SSDT-RCSM.dsl` ，
  - 不做任何修改，在 `文件`，选择 `另存为`，`文件格式`选择为：`ACPI xxx`,
  - 分别得到 `SSDT-ECRW.aml`、`SSDT-RCSM.aml` ，
  - 注意后缀是`.aml`，
  - 将它们放入 `OC/ACPI` 并在 `config.plist` 中引入。
- 重启生效。

### 生效功能

|        功能        |                    是否生效                     |
| :----------------: | :---------------------------------------------: |
| Fn功能键开启与关闭 |       ✅( 键盘上第一行的功能键几乎能工作 )       |
|  键盘灯启动与关闭  | ✅(`Fn+Space`可以进行切换，Pane中不可以进行切换) |
|    性能模式切换    |      ~~✅(`Fn+Q`不行，Pane中可以进行切换)~~      |
|     CapsLk 锁      |          ❎(Mac中CapsLk用于切换中英文)           |

### 副作用

- ~~可能会导致`系统设置-键盘-键盘快捷键-修饰键`不能进行自定义~~
- 

 # 参考文档

- https://blog.xjn819.com/post/opencore-guide.html

- https://yuexiang.fun/1231.html

- https://github.com/daliansky/XiaoXinPro-13-hackintosh/issues/139#issue-970836873

# 建议及声明

由于测试环境有限，部分功能在我的电脑下可以实现不代表适用于所有电脑；如有问题可以提交issues，不保证能够解决。
