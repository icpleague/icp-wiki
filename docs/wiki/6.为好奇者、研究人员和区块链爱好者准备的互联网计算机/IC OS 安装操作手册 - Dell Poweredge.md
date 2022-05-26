# IC OS 安装操作手册 - Dell Poweredge

本手册涵盖了安装 Internet 计算机操作系统（以下称为 IC-OS）所需的所有步骤。物理机预计将根据各自的手册进行上架和堆叠。如果您在安装过程中遇到任何问题，我们恳请您将带有错误消息的电子邮件发送至： support@internetcomputer.org

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

### 视窗

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

## UEFI - 进入系统设置

重新启动或打开服务器电源。注意左上角带有启动选项的蓝屏。列出选项后，按几次 F2。如果您的选项被系统识别，它应该突出显示进入系统设置程序。

## UEFI - 系统 BIOS

在系统设置程序中，选择系统 BIOS 并按 Enter。在系统 BIOS 中，选择处理器设置并按 Enter。将每个套接字的 NUMA 节点设置为 0 ；将最小 SEV 非 ES ASID 设置为 253 ；选择返回以返回系统 BIOS。

## UEFI - 引导设置

选择引导设置并按回车键。将引导模式设置为 UEFI ；选择返回以返回系统 BIOS。

## UEFI - 集成设备

选择集成设备并按 Enter。将 Pcie Preferred IO Bus 设置为 Enabled ；将 Enhanced Preferred IO 设置为 Enabled ；SR-IOV 全局启用到启用；选择返回以返回系统 BIOS。

## UEFI - 其他设置

选择其他设置，然后按 Enter。将 F1/F2 错误提示设置为已禁用；选择返回以返回系统 BIOS。选择完成并按 Enter。选择 Yes 保存更改并按 Enter。选择确定并按 Enter。确认退出并按回车。系统现在将重新启动。

## 引导管理器 - 进入引导管理器

注意左上角带有启动选项的蓝屏。列出选项后，按几次 F11。如果您的选项被系统识别，它应该突出显示进入引导管理器。在 Boot Manager 中，选择 One-shot UEFI Boot Menu，然后按 Enter。在启动菜单中，选择您的 USB 设备，然后按 Enter。

## IC-OS - 安装程序引导

USB 安装程序正在启动，请稍候。此过程最多可能需要 3 分钟。IC-OS 安装开始。请密切关注进展。这部分最多可能需要 8 分钟。如果您遇到任何问题，请将带有错误消息的电子邮件发送至：support@internetcomputer.org。 一旦您被要求插入 HSM，请移除键盘并插入 HSM USB 设备。如果安装成功完成，它将启动重新启动。**此时请不要拔出 U 盘或 HSM USB 设备**。

## IC-OS - 首次启动

IC-OS 的首次启动仍需要 HSM USB 设备。请等到进一步的指示。此步骤最多可能需要 2 分钟。看到此消息后，您可以拔下 HSM USB 设备、USB 记忆棒和 VGA/视频。您的机器已成功加入 Internet 计算机。	