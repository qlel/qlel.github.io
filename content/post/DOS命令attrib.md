+++
title = "DOS命令attrib"
date = "2021-01-31T17:20:38+08:00"
tags = ["dos"]
showLicense = false
+++
显示、设置或删除分配给文件或目录的属性。 
如果在没有参数的情况下使用，则`attrib`将显示当前目录中所有文件的属性。
<!--more-->

## 参数
参数|描述
--|--
`{+\|-}r`|设置（+）或清除（-）只读文件属性。
`{+\|-}a`|设置（+）或清除（-）存档文件属性。 此属性集用于标记自上次备份以来发生更改的文件。请注意， xcopy命令使用存档属性。
`{+\|-}s`|设置（+）或清除（-）系统文件属性。 如果文件使用此属性集，则必须清除该属性，然后才能更改文件的任何其他属性。
`{+\|-}h`|设置（+）或清除（-）隐藏文件属性。 如果文件使用此属性集，则必须清除该属性，然后才能更改文件的任何其他属性。
`{+\|-}i`|设置（+）或清除（-） "非内容索引文件" 属性。
`[<drive>:][<path>][<filename>]`|指定要显示或更改属性的目录、文件或文件组的位置和名称。您可以使用 `？` 和 `*` filename参数中的通配符，以显示或更改一组文件的属性。
`/s`|将attrib和任何命令行选项应用于当前目录及其所有子目录中的匹配文件。
`/d`|将attrib和任何命令行选项应用于目录。
`/l`|将attrib和任何命令行选项应用于符号链接，而不是符号链接的目标。
`/?`|在命令提示符下显示帮助。

---
## 示例
若要显示位于当前目录中名为 News86 的文件的属性，请键入：
```powershell
attrib news86
```
若要将只读属性分配给名为 test.txt 的文件，请键入：
```powershell
attrib +r report.txt
```
若要从位于驱动器 b：中的磁盘上的公共目录及其子目录中删除只读属性，请键入：
```powershell
attrib -r b:\public\*.* /s
```
若要为驱动器 a 上的所有文件设置 Archive 属性，然后清除扩展名为 .bak 的文件的 Archive 属性，请键入：
```powershell
attrib +a a:*.* & attrib -a a:*.bak
```
---
[参考链接](https://docs.microsoft.com/zh-cn/windows-server/administration/windows-commands/attrib)
