---
title: 在 MacOS 与 Ubuntu 20.04 之间搭建集群之二
date: 2022-05-25 03:54:26
tags:
---
### 在 MacOS 与 Ubuntu 20.04 之间搭建集群

#### 成功进行:

1. ##### ssh 连接

   ![Screenshot 2022-05-25 at 3.18.52 AM](/Users/vw/Library/Application Support/typora-user-images/Screenshot 2022-05-25 at 3.18.52 AM.png)

   ![Screenshot 2022-05-25 at 3.37.19 AM](/Users/vw/Library/Application Support/typora-user-images/Screenshot 2022-05-25 at 3.37.19 AM.png)

   ![Screenshot 2022-05-25 at 3.37.42 AM](/Users/vw/Library/Application Support/typora-user-images/Screenshot 2022-05-25 at 3.37.42 AM.png)

2. ##### mount 挂载共享文件夹

   > **sudo mount -a  -o nolocks,resvport,locallocks,rw -t nfs yakiee:/home/vw/mirror /Users/vw/mirror/**

   ![Screenshot 2022-05-25 at 3.38.23 AM](/Users/vw/Library/Application Support/typora-user-images/Screenshot 2022-05-25 at 3.38.23 AM.png)

3. ##### mpich 的安装

​	Ubuntu: **apt**

![Screenshot 2022-05-25 at 3.48.28 AM](/Users/vw/Library/Application Support/typora-user-images/Screenshot 2022-05-25 at 3.48.28 AM.png)

​	MacOS: 下载 **Homebrew** （ macOS 的包管理器 ）

​	https://formulae.brew.sh/formula/mpich

> ​	**brew install mpich**

![Screenshot 2022-05-25 at 3.47.18 AM](/Users/vw/Library/Application Support/typora-user-images/Screenshot 2022-05-25 at 3.47.18 AM.png)

​	<u>但是装载目录非 /usr/bin内</u>

#### 问题：

1. 无法让用主机与宿主机并行运行 .out 文件

报错：

![Screenshot 2022-05-25 at 3.35.11 AM](/Users/vw/Library/Application Support/typora-user-images/Screenshot 2022-05-25 at 3.35.11 AM.png)

有可能的解决方式：更改 mpich 的安装路径

参考回答：https://stackoverflow.com/questions/13387356/mpiexec-hydra-how-to-run-mpi-process-on-machines-where-locations-of-hydra-pmi