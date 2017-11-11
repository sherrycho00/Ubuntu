## u盘变为可读
- 问题描述

u盘在Windows下可以正常读取，在Ubuntu下只能读取u盘中的内容，不能创建文件或复制文件进去

- 解决方法

在Windows的命令行窗口中输入chkdsk G: /f /r 
G:表示U盘,/f是指修复测盘上的错误，/r是指查找损坏的扇区并恢复可读信息

[参考文档](http://blog.csdn.net/Lina_ACM/article/details/60768815)
