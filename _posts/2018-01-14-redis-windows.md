---
layout: post
title: "Redis 개발환경 설정"
subtitle:   "Windows Redis 개발 환경 설정"
date: 2018-01-14 20:00:00 -0400
categories: tip
tags: redis setup
---

# Redis 설치 및 개발 환경 정보
1. Windows Redis 설치
- [https://github.com/dmajkic/redis/downloads](https://github.com/dmajkic/redis/downloads){:target="_blank"}
- [https://msopentech.com/opentech-projects/redis/ ](https://msopentech.com/opentech-projects/redis/ ){:target="_blank"}
- Windows 버전 Redis는 MS Open Tech 그룹의 GitHub 저장소
- [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis){:target="_blank"}
- Redis-x64-3.2.100.msi

2. Redis 설정 및 실행
- redis-server.exe
- redis-cli.exe
- redis-cli -h host -p port -p password
- Redis 기본 포트 : 6379
- * 설정파일지정 실행 : redis-server redis.windows.conf

3. Redis Windows Service 등록/실행
```
 redis-server --service-install redis.windows.conf --loglevel notice
 redis-server --service-start
 redis-server --service-stop
 redis-server --service-uninstall
 서비스 이름 및 포트 지정
 redis-server --service-install -service-name MyRedisServer
 redis-server --service-install -service-name MyRedisServer -port 99001
 redis-server --service-start -service-name MyRedisServer
 redis-server --service-uninstall
 서비스 실행
 net stop redis
 net start redis
```

***
# Docker Redis 설정
1. bagic
```
docker pull redis
docker images
docker run -it --name myredis -d -p 6379:6379 redis
docker ps -al
[redis-cli 접속, exit]  
docker run -it --link myredis:redis --rm redis redis-cli -h redis -p 6379    
myredis:6379> set test1 val1
myredis:6379> get test1
myredis:6379> set test2 val2
myredis:6379> keys *
```

2. --link 
```
docker run -it -v ${PWD}:/data --name myredis -d -p 6379:6379 redis 
docker ps -al
[redis-cli 접속, exit]  
docker run -it --link myredis:redis --rm redis redis-cli -h redis -p 6379    
[redis-server 접속, exit]  
docker exec -it myredis /bin/bash
```

3. --network
```
docker network ls
docker network create redis-net
docker network ls
docker run -it --name myredis -p 6379:6379 --network redis-net -v ${PWD}:/data -d redis redis-server --appendonly yes
docker ps -al
[redis-server 접속, exit]  
docker exec -it myredis /bin/bash
[redis-cli 접속, exit]  
docker run -it --network redis-net --rm redis redis-cli -h myredis -p 6379
```
***

## Redis 명령어
- [http://redis.io/commands](http://redis.io/commands){:target="_blank"}

## Redis GUI Tool Redis-Desktop-Manager
- [https://redisdesktop.com/](https://redisdesktop.com/){:target="_blank"}

## Redis with C# .NET  
- ServiceStack.Redis
  [https://www.nuget.org/packages/ServiceStack.Redis/](https://www.nuget.org/packages/ServiceStack.Redis/){:target="_blank"}
- StackExchange.Redis.Extensions
  [https://www.nuget.org/packages/StackExchange.Redis.Extensions.LegacyConfiguration/](https://www.nuget.org/packages/StackExchange.Redis.Extensions.LegacyConfiguration/){:target="_blank"}
  
- Microsoft.Extensions.Caching.Redis
  [https://www.nuget.org/packages/Microsoft.Extensions.Caching.Redis](https://www.nuget.org/packages/Microsoft.Extensions.Caching.Redis){:target="_blank"}


![img1](/assets/img/post/redis/img1.jpg)
![img2](/assets/img/post/redis/img2.jpg)
![img3](/assets/img/post/redis/img3.jpg)
![img4](/assets/img/post/redis/img4.jpg)