# 关闭防火墙

```shell
# 查看防火墙是否在运行
systemctl status firewalld
# 关闭防火墙
systemctl stop firewalld
systemctl disable firewalld
# 重启电脑后，检验是否关闭成功
systemctl status firewalld
```

![](../../images/15/04/01.jpg)