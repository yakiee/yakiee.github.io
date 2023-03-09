---
title: 在 MacOS 和 Ubuntu20.04 下的集群搭建之一
date: 2022-03-25 21:05:43
tags: NFS OS
---

## 系统环境
- 宿主机: MacOS (从节点)
- 虚拟机: Parallels Desktop (主节点：Ubuntu20.04)

## 配置两台主机的网络连接

### 虚拟机的网络设置
网络源为默认的 Shared Network (共享网络)
![PD network config](/source/_posts/在-MacOS-和-Ubuntu20-04-下的集群搭建/networkConfig.png)

### 查看主机的IP地址

```bash
$ ifconfig  #查看主机的
```

可能会看到有多个网络接口，选择在同一网段下的那个地址。用 ping 命令进行网络联通测试。