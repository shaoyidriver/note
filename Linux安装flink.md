# Linux安装flink

1. 下载flink文件，上传到Linux上

链接: https://pan.baidu.com/s/1V2fVs2qu887dC1i0imhDPg 

提取码: prmd 

2. 解压flink文件并启动

```
[root@localhost install]# tar xzf flink-1.8.0-bin-scala_2.11.tgz
[root@localhost install]# cd flink-1.8.0/
[root@localhost flink-1.8.0]# ./bin/start-cluster.sh

# 关闭防火墙（centos7）
[root@localhost flink-1.8.0]# systemctl stop firewalld
```

3. 访问http://192.168.137.128:8081/

页面展示，则安装成功。