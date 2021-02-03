# Linux安装JDK

1. 下载JDK安装文件（以jdk1.8为例）

链接: https://pan.baidu.com/s/1WiMDqIf73iKZCOd8YpVQdg 

提取码: 7mfk

2. 卸载Linux默认自带的openjdk

```tex
# 查看当前系统Java版本
[root@localhost install]# java -version
openjdk version "1.8.0_242"
OpenJDK Runtime Environment (build 1.8.0_242-b08)
OpenJDK 64-Bit Server VM (build 25.242-b08, mixed mode)
```

显示当前jdk版本为openjdk，若提示没有安装jdk，标准2可跳过。

查看系统现有jdk文件：

```
[root@localhost install]# rpm -qa |grep jdk
java-1.8.0-openjdk-headless-1.8.0.242.b08-1.el7.x86_64
java-1.8.0-openjdk-1.8.0.242.b08-1.el7.x86_64
```

删除类似以上两种形式的文件：

```
[root@localhost install]# rpm -e --nodeps java-1.8.0-openjdk-headless-1.8.0.242.b08-1.el7.x86_64
[root@localhost install]# rpm -e --nodeps java-1.8.0-openjdk-1.8.0.242.b08-1.el7.x86_64
```

3. 通过rpm方式安装jdk

```
[root@localhost install]# rpm -ivh jdk-8u211-linux-x64.rpm

# 安装完成后查看Java版本，如下则说明安装成功
[root@localhost install]# java -version
java version "1.8.0_211"
Java(TM) SE Runtime Environment (build 1.8.0_211-b12)
Java HotSpot(TM) 64-Bit Server VM (build 25.211-b12, mixed mode)
```

