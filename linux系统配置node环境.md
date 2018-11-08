# 如何在linux环境下安装node

### 1.首先我们利用yum安装一个传输文件的工具: lrzsz（推荐） 
`lrzsz`是一款linux下命令行界面上支持上传和下载的第三方工具，能够起到很方便的作用。(简易ftp)
`sz: 将选定的文件发送(send)到本地机器;`
`rz：运行该命令会弹出一个文件选择窗口, 从本地选择文件上传到服务器(receive).`
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
```
tip: 此时会弹出一个对话框，导入文件
```
[root@VM_0_7_centos node]# tar -zxvf node-v6.2.0-linux-x64.tar.gz
```
tip: 分别是四个参数
`x : 从 tar 包中把文件提取出来`
`z : 表示 tar 包是被 gzip 压缩过的，所以解压时需要用 gunzip 解压`
`v : 显示详细信息`
`f : xxx.[tar.gz] 指定被处理的文件是 xxx.[tar.gz]`


### 4.安装nano,配置环境变量(默认已有)
* nano:一个体积小巧而功能强大的文本编辑器。
```
[root@VM_0_7_centos ~]# yum install nano
[root@VM_0_7_centos ~]# nano ~/.bashrc
```
在打开的.bashrc文件最后将配置加进去（非软连接）
`export PATH=/home/node/node-v6.2.0-linux-x64/bin:$PATH`
nano 的保存操作步骤如下
`ctrl+o -> ctrl-x -> y -> enter`
每次修改.bashrc后，使用source ~/.bashrc 是修改立即生效
```
[root@VM_0_7_centos ~]# source ~/.bashrc
```


### 5.检查是否配置成功
弹出版本号则配置成功
```
[root@VM_0_7_centos ~]# npm -v
6.4.1
[root@VM_0_7_centos ~]# node -v
v10.13.0
```