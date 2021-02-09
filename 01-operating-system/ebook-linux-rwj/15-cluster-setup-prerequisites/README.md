# 集群安装先决环境

这里以三台机器组成一个集群为例。集群节点安排如下：

| HOST NAME |   IP ADDRESS   | OPRATING SYSTEM |
| :-------: | :------------: | :-------------: |
|    n1     | 192.168.154.11 |    CentOS 7     |
|    n2     | 192.168.154.12 |    CentOS 7     |
|    n3     | 192.168.154.13 |    CentOS 7     |

参考：[Vmware安装CetOS系统](../02-installation/README.md)，先安装好3台机器。主机名和ip地址见上表。如果要修改请参考：

- [配置主机名](./01-config-hostname/README.md) 。
- [配置网络信息](./02-config-network/README.md) 。

其他配置参考如下：

> **[info] 注意**
>
> 没特殊说明的，就是三台机器都需要配置的。
>
> 另外，不同系统和版本可能略有差异。

1. [修改hosts文件，配置映射信息](./03-config-hosts/README.md)；
2. [关闭防火墙](./04-config-firewall/README.md)；
3. [禁用SELinux](./05-config-selinux/README.md)；
4. [修改umask值为0022](./06-config-umask/README.md)；
5. [配置NTP时间同步](./07-config-time-sync/README.md)；
6. [配置免密SSH](./08-config-ssh/README.md)；
7. [安装JDK](./09-config-jdk/README.md)；

以上所有配置完成后重启，保险起见，最好分别验证是否生效。

如果验证全部正确以后，就可以去搭建hadoop、HBase、Spark等集群了。

