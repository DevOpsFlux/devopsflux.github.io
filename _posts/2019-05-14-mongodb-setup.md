---
layout: post
title: "MongoDB 개발환경 설정"
subtitle:   "Windows MongoDB 개발 환경 설정"
date: 2018-05-14 20:00:00 -0400
categories: tip
tags: redis setup
---

# MongoDB 설치 및 개발 환경 정보
1. Windows 설치
- [http://www.mongodb.org/downloads](http://www.mongodb.org/downloads){:target="_blank"}
- [http://docs.mongodb.org/manual/tutorial/install-mongodb-on-windows/](http://docs.mongodb.org/manual/tutorial/install-mongodb-on-windows/){:target="_blank"}

2. MongoDB 설정 및 실행
- MongoDB 실행(mongod.exe)
- mongod.exe는 MongoDB 서버 실행파일이고, mongo.exe는 MongoDB를 조작할수 있는 MongoDB Shell 프로그램
- 설정파일 : D:\mongodb\mongod.cfg
- mkdir D:\mongodb\data
- D:\mongodb\bin\mongod.exe --dbpath D:\mongodb\data  (Ctrl + C 도는 Ctrl + D 로 중단)

3. MongoDB Windows Service 등록/실행
```
 MongoDB 서비스 등록
	실행 > services.msc
	D:\mongodb\bin\mongod.exe -f D:\mongodb\bin\mongod.cfg -install
서비스 제거
	D:\mongodb\bin\mongod.exe -f D:\mongodb\mongod.cfg -remove

	MongoDB 서버 Port 27017

	MongoDB 웹 관리 툴
	http://127.0.0.1:28017/
```

## MongoDB Docs
- [https://docs.mongodb.com](https://docs.mongodb.com){:target="_blank"}
- [http://docs.mongodb.org/manual/tutorial/install-mongodb-on-windows/](http://docs.mongodb.org/manual/tutorial/install-mongodb-on-windows/){:target="_blank"}

## MongoDB Cloud
- [https://www.mongodb.com/cloud](https://www.mongodb.com/cloud){:target="_blank"}

## MongoDB GUI Compass
- [https://www.mongodb.com/download-center/compass](https://www.mongodb.com/download-center/compass){:target="_blank"}

## MongoDB GUI Robomongo
- [https://robomongo.org/](https://robomongo.org/){:target="_blank"}

## MongoDB with C# .NET  
- MongoDB.Bson
  [https://www.nuget.org/packages/MongoDB.Bson/](https://www.nuget.org/packages/MongoDB.Bson/){:target="_blank"}
- MongoDB.Driver
  [https://www.nuget.org/packages/MongoDB.Driver/](https://www.nuget.org/packages/MongoDB.Driver/){:target="_blank"}
  
![img1](/assets/img/post/mongodb/setup/img11.jpg)
![img2](/assets/img/post/mongodb/setup/img22.jpg)
![img3](/assets/img/post/mongodb/setup/img33.jpg)