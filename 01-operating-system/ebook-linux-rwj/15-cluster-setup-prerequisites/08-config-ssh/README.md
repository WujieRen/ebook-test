# 配置免密SSH

## 前提

三台主机要能互相ping通，即已经完成[配置hosts文件](../03-config-hosts/README.md)。

## 配置步骤

每个节点上分别执行以下命令。

```shell
# 以rsa算法生成密匙
ssh-keygen - rsa
# 发送公匙到指定的节点，包括本机自己也要执行。
# 有几台就要执行几次；
# 比如三台节点 n1、n2、n3，就要将hostname分别换成n1、n2、n3，每台节点上都要执行三次，分别发送到n1、n2、n3
ssh-copy-id <hostname>
```

如果报：ssh-copy-id not found，安装openssh-clients后再执行ssh-copy-id命令。

```shell
yum install openssh-clients -y
```

## 验证

配置完成后，验证是否能够免密登录。

```shell
ssh <hostname>
```

