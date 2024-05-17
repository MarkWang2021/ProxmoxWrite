# ProxmoxWrite

1、关闭死机的虚拟机

ps -ef| grep "/usr/bin/kvm -id 102"

kill 进程

查看虚拟机vmID,输入命令：

qm list

如果我需要关闭编号为100的虚拟机，首先删除vmID的lock锁文件,输入命令：

rm /var/lock/qemu-server/lock-100.conf

进行关闭，输入命令

qm stop 100


