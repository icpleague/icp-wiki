# IC OS 安装手册 - Supermicro

本手册涵盖了安装 Internet 计算机操作系统（以下称为 IC-OS）所需的所有步骤。

物理机预计将根据各自的手册进行上架和堆叠。

如果您在安装过程中遇到任何问题，我们恳请您将带有错误消息的电子邮件发送至： support@internetcomputer.org

非常感谢您为构建 Internet 计算机所做的努力。

## 下载安装映像

在此处下载 IC-OS ISO 映像：
[https ://download.dfinity.systems/blessed/ic/2fe8e5fa9b20451cbfe38d95e35fa9b3d5212a88/setup-os/setup-os.iso](https://download.dfinity.systems/blessed/ic/2fe8e5fa9b20451cbfe38d95e35fa9b3d5212a88/setup-os/setup-os.iso)

在此处下载相应的校验和：
[https ://download.dfinity.systems/blessed/ic/2fe8e5fa9b20451cbfe38d95e35fa9b3d5212a88/setup-os/SHA256SUMS](https://download.dfinity.systems/blessed/ic/2fe8e5fa9b20451cbfe38d95e35fa9b3d5212a88/setup-os/SHA256SUMS)

## 计算和检查校验和

### Mac OS X

打开终端并输入：

```
shasum -a 256 ~/Downloads/setup-os_<version>.iso
```

### Linux / Ubuntu

打开终端并输入：

```
sha256sum ~/Downloads/setup-os_<version>.iso
```

### Windows

打开 PowerShell 并键入：

```
Get-FileHash -Algorithm SHA256 .\Downloads\setup-os_<version>.iso
```

将计算出的校验和与 DFINITY 基金会提供的校验和进行比较。**只有在它们相同的情况下才能继续**，否则请联系 DFINITY 基金会。

## 创建可启动 U 盘

### Mac OS X

打开终端并输入：

```
diskutil list
```

- diskutil 命令仅显示所有可用驱动器。请确保 /dev/sda 是您的 U 盘，而不是任何其他驱动器。**警告：**如果您指定了错误的驱动器，您可能会丢失自己的数据。

```
dd if = ~/Downloads/setup-os_<version>.iso of = /dev/sda
```

### Linux / Ubuntu

打开终端并输入

```
blkid
```

blkid 命令只显示所有可用的驱动器。请确保 /dev/sda 是您的 U 盘，而不是任何其他驱动器。**警告：**如果您指定了错误的驱动器，您可能会丢失自己的数据。

```
dd if = ~/Downloads/setup-os_<version>.iso of = /dev/sda
```

### 视窗

从以下网址下载 Rufus Portable：[https](https://rufus.ie/en/) ://rufus.ie/en/ 启动 Rufus ；选择设备下的 U 盘；选择之前下载的 IC-OS 磁盘映像并按开始；选择 DD Image 模式并按 OK ；按 OK 确认操作

## 连接碰撞车

为了配置 UEFI 并启动 IC-OS 的安装，请将故障车连接到物理机。插入 VGA/视频、键盘和 IC-OS U 盘

## UEFI - 进入设置

重新启动或打开服务器电源。注意屏幕下方有 Supermicro 标志和启动选项。列出选项后，按几次 DEL（删除）。如果您的选项被系统识别，它应该说：进入设置...

## UEFI - 高级设置

更改为 Advanced 菜单 Select Boot Feature 并按 Enter Set Wait For "F1" If Error to Disabled ; 按 ESC（退出）返回上一级菜单 选择 ACPI 设置并按 Enter 将 PCI AER 支持设置为已启用；将每个套接字的 NUMA 节点设置为 NPS0 ；按 ESC (escape) 返回上一级菜单 选择 NB Configuration 并按 Enter 将 4-link xGMI 最大速度设置为 Auto ；按 ESC (escape) 返回上一级菜单 Select PCIe/PCI/PnP Configuration 并按 Enter Set SR-IOV Support to Enabled ；将 NVMe 固件源设置为 AMI Native Support ；将 M.2 (ACPI) 固件源设置为 AMI Native Support ；按 ESC（退出）返回上一个菜单

## UEFI - 引导设置

更改为 Boot 菜单 Set Boot Mode Select to UEFI Change to Save & Exit menu 选择 Save Changes and Reset 并按 Enter 选择 Yes 并按 Enter。系统现在将重新启动。

## 启动 USB 映像

注意屏幕下方有 Supermicro 标志和启动选项。列出选项后，按几次 F11。在 Boot Menu 中，选择 USB 设备并按 enter 请稍候，USB Installer 正在启动。此过程最多可能需要 3 分钟。IC-OS 安装开始。请密切关注进展。这部分最多可能需要 8 分钟。如果您遇到任何问题，请将带有错误消息的电子邮件发送至：support@internetcomputer.org 一旦您被要求插入 HSM，请移除键盘，而插入 HSM USB 设备。如果安装成功完成，它将启动重新启动。**此时请不要拔出 U 盘或 HSM USB**设备。

## 首次启动

IC-OS 的首次启动仍需要 HSM USB 设备。请等到进一步的指示。此步骤最多可能需要 2 分钟。看到此消息后，您可以拔下 HSM USB 设备、USB 记忆棒和 VGA/视频。您的机器已成功加入 Internet 计算机。

如果您的选项被系统识别，它应该显示 Invoking Boot Menu