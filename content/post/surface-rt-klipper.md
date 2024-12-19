+++
title = "九十元大屏触控klipper pad 安装教程——使用二手sureface rt"
date = 2024-07-18T10:56:30+08:00
author = "DikiFive"
keywords = ["", ""]
cover = ""
summary = ""
draft = false
+++

# Surface RT 安装 Klipper、Moonraker、Fluidd 和 KlipperScreen 指南

本教程将引导您通过一系列步骤，将您的 Surface RT 设备转变为 Klipper 控制平板，安装包括 Klipper、Moonraker、Fluidd 和 KlipperScreen 在内的软件。

## 1. 原作信息
以下资源提供了安装所需的信息和文件：
- 视频教程：[How to Make a Klipper Tablet for $20 in Five MINUTES!_youtube](https://youtu.be/hv79HNvNFqE?si=HOvAYXr6eaFtHLSw)
- GitHub 网址：[Klipper-for-3d-printer-on-Microsoft-Surface-RT-GitHub](https://github.com/theck32/Klipper-for-3d-printer-on-Microsoft-Surface-RT.git)
- 越狱教程：[All-in-on jailbreak package for Tegra based Windows RT tablets](https://windows-rt-devices.gitbook.io/windows/tools/tegra-jailbreak-usb)
- 本人搬运国内B站视频：[90元klipper大屏上位机（surface rt）](https://www.bilibili.com/video/BV133bkeqEvs/?share_source=copy_web&vd_source=b8f6d2bd85f4f67ed49ae1916ceb8b49)

## 2. Surface RT 越狱

首先，您需要对 Surface RT 设备进行越狱。

1. **越狱文件下载**：[Tegra_Jailbreak_USB](https://pan.quark.cn/s/ba434b125b12)，提取码：FrPJ
2. **准备 U 盘**：将 U 盘格式化为 FAT32 格式，并将下载的越狱文件解压到 U 盘根目录下。
3. **启动设备**：将 U 盘插入 Surface RT 设备，并从 U 盘启动设备。若 Surface RT 仅有一个 USB 口，可能需要拓展坞。
4. **安装金钥匙**：使用箭头键选择“安装金钥匙”并按 Enter。
5. **接受并安装**：使用箭头键突出显示“接受并安装”，然后按 Enter。安装完成后设备会重启。

### 安装 Yahallo
- 在重启后，再次从 U 盘启动，并选择“Install Yahallo”然后按 Enter。

## 3. 下载 KlipperRT.img
- 从[这里](https://pan.quark.cn/s/a3524551db60)下载 KlipperRT.img 镜像文件，提取码：q62S。

## 4. 写入镜像文件
- 使用 Etcher 或等效工具将 KlipperRT.img 镜像写入 USB 驱动器。本人使用[balenaEtcher-1.19.21.Setup](https://pan.quark.cn/s/567f1143790c)提取码：58xP

## 5. 启动 Surface RT
- 通过同时按住音量减小键和电源键，从 USB 驱动器启动 Surface RT。

## 6. 等待安装完成
- 安装过程可能需要 30-40 分钟。完成后，设备会自动关闭。

## 7. 移除 USB 驱动器并启动设备
- 移除 USB 驱动器，并正常启动 Surface RT。

## 8. 访问终端
- 当 KlipperScreen 启动后，使用 `Ctrl+Alt+F3` 进入终端。
- - 默认账户pi 密码为raspberry
- root账户尚未设置，设置密码后可以使用
- 输入指令sudo passwd root设置下密码再用su root后输入自己设置的密码就行了

## 9. 查找 MCU 链接
- 在终端中运行 `ls /dev/serial/by-id/` 来查找 MCU 链接，此信息将用于 `printer.cfg` 文件中的 `[mcu]` 部分。

## 10. 配置 Wi-Fi
- 在终端中运行 `sudo raspi-config`，选择系统选项（1），然后配置 Wi-Fi。

## 11. 扩展文件系统
- 在 `raspi-config` 菜单中，返回第一页选择 6，然后选择 A1 扩展文件系统。

## 12. 重启设备
- 完成所有配置后，重启设备。

## 13. 配置 `printer.cfg`
- 在 Fluidd 中配置 `printer.cfg` 文件。

---

**注意**：以上步骤是针对微软 Surface RT 设备的特定操作，请确保在操作前备份重要数据。