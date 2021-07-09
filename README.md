## Hadoop Learing

[Hadoop Base](https://hadoop.apache.org/docs/stable/hadoop-project-dist/hadoop-common/SingleCluster.html#Standalone_Operation)

### 服务器信息
用户信息： hadoop/123456

目录：/home/hadoop

端口开放：
```bash 
firewall-cmd --zone=public --add-port=8088/tcp --permanent
```

### Standalone hadoop设置：

Data nodes - http://10.0.15.172:9870/

ResourceManager - http://localhost:8088/


### 一些常用操作 ### 
```bash
bin/hdfs dfs -put test.word /user/hadoop/iw
bin/hdfs dfs -mkdir /user/hadoop/iw
bin/hdfs dfs -mkdir /user/hadoop/ow
bin/hdfs dfs -put test.word /user/hadoop/iw

bin/hadoop jar hadoop-demo-1.0-SNAPSHOT.jar  /user/hadoop/iw  /user/hadoop/kc word

bin/hdfs dfs -cat /user/hadoop/kc/*
```


```bash
#统计单词green的出现次数并输出到/user/hadoop/green目录
bin/hadoop jar hadoop-demo-1.0-SNAPSHOT.jar  /user/hadoop/iw  /user/hadoop/green green #参数为 输入目录 输出目录 和需要查找的单词
#查看结果
bin/hdfs dfs -cat /user/hadoop/green/*
```
