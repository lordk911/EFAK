[![Build Status](https://app.travis-ci.com/smartloli/EFAK.svg?branch=master)](https://app.travis-ci.com/smartloli/EFAK)
![](https://img.shields.io/badge/language-java-orange.svg)
[![codebeat badge](https://codebeat.co/badges/4c141093-e55d-464d-87ce-7431cde81398)](https://codebeat.co/projects/github-com-smartloli-efak-master)
[![Hex.pm](https://img.shields.io/hexpm/l/plug.svg)](https://github.com/smartloli/EFAK/blob/master/LICENSE)

[![Stargazers over time](https://starchart.cc/smartloli/kafka-eagle.svg)](https://starchart.cc/smartloli/kafka-eagle)

# EFAK (Eagle For Apache Kafka, previously known as Kafka Eagle)

This is an monitor system and monitor your kafka clusters, and visual consumer thread,offsets,owners etc.

When you install [EFAK](https://www.kafka-eagle.org/), you can see the current consumer group,for each group the topics that they are consuming and the offsets, lag, logsize position of the group in each topic. This is useful to understand how fast you are consuming from a message queue and how quick the message queue is increase. This will help you debuging kafka producers and consumers or just to have an idea of what is going on in your system.

The system shows the trend of consumer and producer trends on the same day, so you can see what happened that day.

Supported on kafka version: ``` 0.8.2.x ```,``` 0.9.x ```,``` 0.10.x ```,``` 0.11.x ```,``` 1.x ```,``` 2.x ``` .

Supported platform: ```Mac OS X```,```Linux```,```Windows```.

Supported JDK: ```JDK8+```

Here are a few `EFAK` system screenshots:
![efak_tv](https://www.kafka-eagle.org/images/docs/bscreen@2x.png)

# Get started
* [Get EFAK](http://download.kafka-eagle.org/)
* [Installation guides](https://www.kafka-eagle.org/articles/docs/documentation.html)

Unsure if EFAK is for you? Watch EFAK video in action on [www.kafka-eagle.org](https://www.kafka-eagle.org)!

# Alert Support
`EFAK` supports currently popular IM alarm systems, such as:
* DingDing
* WeChat
* Webhook
* Email
* ...

# List of Consumer Groups & Active Group Graph
![Consumer & Active Graph](http://www.kafka-eagle.org/images/docs/consumer@2x.png)

# List of Topics Detail
![Topics](http://www.kafka-eagle.org/images/docs/list@2x.png)

# Consumer & Producer Rate Chart
![Rate Chart](http://www.kafka-eagle.org/images/docs/consumer_rate_graph@2x.png)

# Start EFAK
![KE Script](http://www.kafka-eagle.org/images/docs/startup@2x.png)

# Kafka Offset Types

Kafka is designed to be flexible on how the offsets are managed. Consumer can choose arbitrary storage and format to persist kafka offsets. `EFAK` currently support following popular storage format:
  * Zookeeper. Old version of Kafka (0.8.2 before) default storage in Zookeeper.
  * Kafka. New version of Kafka (0.10.0 in the future) default recommend storage in Kafka Topic(__consumer_offsets).
  
`EFAK` supports multiple offset storage paths. If you store them in Zookeeper and Kafka, you can configure them like this.
```
# Set kafka cluster alias
efak.zk.cluster.alias=cluster1,cluster2

# Set kafka cluster zookeeper address
cluster1.zk.list=xdn1:2181,xdn2:2181,xdn3:2181
cluster2.zk.list=tdn1:2181,tdn2:2181,tdn3:2181

# Set kafka cluster offset storage path
cluster1.efak.offset.storage=kafka
cluster2.efak.offset.storage=zookeeper
```

# Kafka SQL

Use the SQL statement to query the topic message log, and visualize the results, you can read [Kafka SQL](http://www.kafka-eagle.org/articles/docs/quickstart/ksql.html) to view the syntax.
For example, if you kafka has a topic with three partitions, the ksql query statement is as follows.
```
select * from ke_p3_r2 where `partition` in (0,1,2) limit 10
```

![ksql](http://www.kafka-eagle.org/images/docs/kafka_ksql_v2@2x.png)
![ksql_result](http://www.kafka-eagle.org/images/docs/kafka_ksql_result_v2@2x.png)

# Quickstart

Please read [EFAK Install](http://www.kafka-eagle.org/articles/docs/installation/linux-macos.html) for setting up and running `EFAK`.

# Deploy

The project is a maven project that uses the Maven command to pack the deployment as follows:
```bash
./build.sh
```
# More Information

Please see the [EFAK Manual](http://www.kafka-eagle.org/articles/docs/documentation.html) for for more information including:
  * System environment settings and installation instructions.
  * Information about how to use script command.
  * Visual kafka consumer group,topic,offset metadata information etc.
  * Metadata collection and log change information.
 
# Contributing

The `EFAK` is released under the Apache License and we welcome any contributions within this license. Any pull request is welcome and will be reviewed and merged as quickly as possible.

Since this is an open source tool, please comply with the relevant laws and regulations, the use of civilization.

# Project Name and Management

`EFAK` was renamed from its previous name due to [this issue](https://github.com/smartloli/kafka-eagle/issues/525). `EFAK` is designed to be used with Apache Kafka and is offered to support the needs of the Kafka community. The project is open source by [Smartloli](https://www.kafka-eagle.org/articles/about/me.html) and maintained and managed in Github.

# Contributors

Thanks to the following members for maintaining the project. If this project help you reduce time to develop, you can give us a star. 

|Alias |Github |Email |
|:-- |:-- |:-- |
|smartloli|[smartloli](https://github.com/smartloli)|smartloli.org@gmail.com|
|hexiang|[hexian55](https://github.com/hexian55)|hexiang55@gmail.com|
|cocodroid|[cocodroid](https://github.com/cocodroid)|sujunguang@gmail.com|
|alisa|[alisa](https://github.com/zoumm)|alisazou1211@gmail.com|
|iamwzt|[iamwzt](https://github.com/iamwzt)|981911861@qq.com|
|JacobAP|[JacobAP](https://github.com/JacobAP)|jacobap@163.com|