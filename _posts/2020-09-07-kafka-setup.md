---
layout: post
title: "Kafka 개발환경 설정"
subtitle:   "Kafka 설치 및 개발환경 정보"
date: 2020-09-07 20:00:00 -0400
categories: tip
tags: kafka setup
---


## Kafka 설치 및 개발 환경 정보
1. Windows 기본 설치
- Binary downloads에서 원하는 버전을 다운 : kafka_2.12-2.5.1.tgz
- [https://kafka.apache.org/downloads](https://kafka.apache.org/downloads){:target="_blank"}
- [https://www.apache.org/dyn/closer.cgi?path=/kafka/2.5.1/kafka_2.12-2.5.1.tgz](https://www.apache.org/dyn/closer.cgi?path=/kafka/2.5.1/kafka_2.12-2.5.1.tgz){:target="_blank"}
- 압축 해제 D:\DevOps\Kafka\kafka_2.12-2.5.1
- D:\DevOps\Kafka\kafka_2.12-2.5.1\bin\windows

2. Zookeeper 먼저 실행 (창 유지)
- cd 압축파일 푼 디렉토리\bin\windows
- .\zookeeper-server-start.bat ..\..\config\zookeeper.properties
 
3. Kafka 실행 (신규창 실행)
- cd 압축파일 푼 디렉토리\bin\windows
- .\kafka-server-start.bat ..\..\config\server.properties

4. topic 생성 :
- .\kafka-topics.bat --create --bootstrap-server localhost:9092 --replication-factor 1 --partitions 1 --topic ((원하는토픽명적기))
- .\kafka-topics.bat --create --bootstrap-server localhost:9092 --replication-factor 1 --partitions 1 --topic devtopic

5. 토픽 목록 확인 
- .\kafka-topics.bat --list --bootstrap-server localhost:9092

6. producer로 메시지를 보내고 consumer를 통해 받기
- 메시지 보내기 : .\kafka-console-producer.bat --broker-list localhost:9092 --topic devtopic
- 메시지 받기 : .\kafka-console-consumer.bat --bootstrap-server localhost:9092 --topic devtopic --from-beginning

## Kafka Docker 
- http://wurstmeister.github.io/kafka-docker/

```
1. kafka-docker repository
	$ git clone https://github.com/wurstmeister/kafka-docker
	$ cd kafka-docker
2. docker-compose.yml 파일 수정
- 내장 Zookeeper 사용
- docker-compose-single-broker.yml
 > KAFKA_ADVERTISED_HOST_NAME: 127.0.0.1
3. docker-compose 실행
- docker-compose up -d
	$ docker-compose -f docker-compose-single-broker.yml up -d
	$ docker-compose logs / docker logs
```

```
## Kafka-Docker Confluent Platform
1. Kafka-Docker
	curl --silent --output docker-compose.yml https://raw.githubusercontent.com/confluentinc/cp-all-in-one/6.1.0-post/cp-all-in-one/docker-compose.yml

2. docker-compose
	$ docker-compose up -d
	$ docker-compose ps

3. Confluent Platform
	http://localhost:9021
```

## Kafka Manager on Windows
- https://www.scala-lang.org/download/ -> scala, sbt 다운
- [참고] https://my.oschina.net/yogiwang/blog/2052253
- cmd > kafka manager 폴더 > sbt > (kafka-manager cli 진입) > compile > run

### 실행 화면
![img1](/assets/img/post/kafka/img01.JPG)

![img2](/assets/img/post/kafka/img02.JPG)

![img3](/assets/img/post/kafka/img03.JPG)

![img4](/assets/img/post/kafka/img04.JPG)

![kafka-1](/assets/img/post/kafka/kafka-1.JPG)

![kafka-2](/assets/img/post/kafka/kafka-2.JPG)

![kafka-3](/assets/img/post/kafka/kafka-3.JPG)

![kafka-4](/assets/img/post/kafka/kafka-4.JPG)


### 참고
[Apache Kafka Documentation](https://kafka.apache.org/documentation/){:target="_blank"}

[Apache Kafka Ecosystem](https://cwiki.apache.org/confluence/display/KAFKA/Ecosystem){:target="_blank"}

[Apache Kafka Monitoring](https://docs.confluent.io/platform/current/kafka/monitoring.html){:target="_blank"}

[Apache Kafka Offset Monitor](https://github.com/Morningstar/kafka-offset-monitor){:target="_blank"}

[Apache Kafka using Confluent Platform](https://docs.confluent.io/platform/current/quickstart/ce-docker-quickstart.html){:target="_blank"}
