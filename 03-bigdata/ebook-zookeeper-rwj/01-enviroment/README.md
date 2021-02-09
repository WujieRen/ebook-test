# Zookeeper分布式安装

## Prerequisites

## Installation

点击[下载](http://archive.apache.org/dist/zookeeper/)相应版本，本文档采用3.5.7。这里以三台节点为例。三台节点主机名分别为n1、n2、n3。

## Configure Zookeeper

解压下载的Zookeeper压缩文件至指定目录。

修改zoo.cfg文件，注意修改文件名称。该文件中主要修改两个地方：

1. 指定本地存储数据的目录，如：dataDir=/opt/cluster/zookeeper/data/zkData

2. 指定zk节点服务器端的实例，有几个写几个。注意server.后面的序号不能重复：

   ```shell
   server.1=n1:2888:3888
   server.2=n2:2888:3888
   server.3=n3:2888:3888
   ```

在目录/opt/cluster/zookeeper/data/zkData下vim myid文件，写1，保存退出。myid文件的内容要和"server.x"中的x保持一致，不同节点删过的myid文件对应其中一个序号即可。

将Zookeeper分发到其他节点上。

在其他节点上，将分发过来的Zookeeper配置文件中的myid的内容分别改为对应的序号。这里分别为2和3。

## Operate the Zookeeper Cluster

启动/关闭Zokkeeper server：

```shell
zkServer.sh start/stop
```

查看Zookeeper server状态：

```shell
zkServer.sh status
```

启动关闭Zookeeper client：

```shell
zkCli.sh start/stop
```

在所有节点上启动Zookeeper server后用命令jps可以看到对应进程的名字：~~~

启动Zokeeper client后用命令jps可以看到对应进程的名字：~~~







