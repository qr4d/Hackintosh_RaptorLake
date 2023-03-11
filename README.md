# Hackintosh_RaptorLake
适用于13代(Raptorlake)黑苹果引导文件

OpenCore 0.9.0，机型可选MacPro或iMac

# 支持的主板

华硕z690p d4
铭瑄h610 itx
(搭配黑苹果网卡)

## 正常驱动
* 声卡
* USB接口
* 音量调节
* 有线网卡
* 无线网卡
* 睡眠唤醒
* 隔空投送
* 接力

## 无法驱动
* 随航无法使用


# BIOS设置
铭瑄BIOS从1.4版本开始支持RaptorLake，但官方[BIOS](http://www.maxsun.com.cn/2022/0512/5728.html)v1.4g默认开启了cfglock，使用cfglock.efi/grub/ru.efi等方法均不能解锁cfglock，不得已基于1.4版本魔改了一份BIOS，默认解锁cfglock。
据说OpenCore可以通过开启Quirks选项AppleCpuPmCfgLock跳过，但我没试过


# 制作启动盘
* 用rufus.exe格式化U盘，选择 非可引导 FAT32(U盘)或Large FAT32(外置硬盘)
* 下载[OpenCore](https://github.com/acidanthera/OpenCorePkg)，用其中macrecovery工具（需要python环境）下载macos，放入U盘
* 将EFI文件装入U盘
* 下载[OCAT](https://github.com/ic005k/OCAuxiliaryTools/releases)，读取EFI\OC目录下的config.plist，检查更新并生成新的三码信息
* BIOS里选择从U盘启动，按指示安装即可

NVRAM的boot-args添加-v可以看到报错信息，或者在[开机时按Command-V](https://support.apple.com/zh-cn/HT201255)

