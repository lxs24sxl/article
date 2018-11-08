# 如何在linux环境下安装node

### 1.首先我们需要一个上传文件包工具: lrzsz
· 简易ftp
```
[root@VM_0_7_centos ~]# yum install lrzsz
# 下载好按y开始安转，等待即可
```

### 2.去官网下载node文件关于linux系统的包 
[下载地址:https://npm.taobao.org/mirrors/node/v10.13.0](https://npm.taobao.org/mirrors/node/v10.13.0/)
下载之后的文件名为:  node-v10.13.0-linux-x64.tar.gz  (注意gz)

### 3.解压node安装包
```
[root@VM_0_7_centos ~]# cd /home/node
[root@VM_0_7_centos node]# rz
# tip: 此时会弹出一个对话框，导入文件
[root@VM_0_7_centos node]# tar -zxvf node-v6.2.0-linux-x64.tar.gz
# tip: 分别是四个参数
# x : 从 tar 包中把文件提取出来
# z : 表示 tar 包是被 gzip 压缩过的，所以解压时需要用 gunzip 解压
# v : 显示详细信息
# f xxx.[tar.gz] 指定被处理的文件是 xxx.[tar.gz]
```


### 4.安装nano,配置环境变量(默认已有)
```
[root@VM_0_7_centos ~]# yum install nano
[root@VM_0_7_centos ~]# nano ~/.bashrc
# tip: 再最后加入：
# export PATH=/home/node/node-v6.2.0-linux-x64/bin:$PATH
# nano 的操作步骤如下:
# ctrl+o -> ctrl-x -> y -> enter
# 每次修改.bashrc后，使用source ~/.bashrc 是修改立即生效
[root@VM_0_7_centos ~]# source ~/.bashrc
```

### 5.检查是否配置成功
```
[root@VM_0_7_centos ~]# npm -v
6.4.1
[root@VM_0_7_centos ~]# node -v
v10.13.0
```