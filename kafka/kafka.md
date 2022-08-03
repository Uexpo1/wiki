# Kafaka

> 1）查看当前服务器中的所有 topic
```java
bin/kafka-topics.sh --zookeeper  hadoop102:2181 --list
```
> 2）创建 topic
```java
bin/kafka-topics.sh --zookeeper hadoop102:2181 --create --replication-factor 3 --partitions 1 --topic first
```
> 3）删除 topic
```java
bin/kafka-topics.sh --zookeeper  hadoop102:2181 --delete --topic first
```
> 4）发送消息
```java
bin/kafka-console-producer.sh --broker-list hadoop102:9092 --topic first
```
> 5）消费消息
```java
[hadoop@hadoop102 kafka]$ bin/kafka-console-consumer.sh --zookeeper hadoop102:2181 --topic first

[hadoop@hadoop102 kafka]$ bin/kafka-console-consumer.sh --bootstrap-server hadoop102:9092 --topic first

[hadoop@hadoop102 kafka]$ bin/kafka-console-consumer.sh --bootstrap-server hadoop102:9092 --from-beginning --topic first

```
> 6）查看某个 Topic 的详情
```java
bin/kafka-topics.sh --zookeeper hadoop102:2181 --describe --topic first
```
> 7）修改分区数
```java
bin/kafka-topics.sh --zookeeper hadoop102:2181 --alter --topic first --partitions 6
```
> 8) 命令解释
```
选项说明：
–topic 定义 topic 名
–replication-factor 定义副本数
–partitions 定义分区数
```