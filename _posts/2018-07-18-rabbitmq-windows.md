---
layout: post
title: "RabbitMQ 개발환경 설정"
subtitle:   "Windows RabbitMQ 개발 환경 설정"
date: 2018-07-18 20:00:00 -0400
categories: tip
tags: rabbitmq setup
---

# RabbitMQ 설치 및 개발 환경 정보
1. RabbitMQ_언랭 설치(erlang download)_[step 1]

- RabbitMQ 설치 전 ERLang 설치 필요
https://www.rabbitmq.com/install-windows.html
esl-erlang_22.0_windows_amd64.exe

2. RabbitMQ 설치 Server
https://www.rabbitmq.com/install-windows.html
https://www.rabbitmq.com/documentation.html

3. Managgement Plugin 설치
https://yi-chi.tistory.com/74

 3-1 RabbitMQ Command Prompt (sbin dir) 를 실행
 3-2 rabbitmq-plugins enable rabbitmq_management 명령 설치

 3-3 rabbitmq-server -detached

실행 : http://localhost:15672  
	guest/guest


​```RabbitMQ

- Path 추가
C:\Windows\System32\cmd.exe /k cd C:\Program Files\RabbitMQ Server\rabbitmq_server-3.7.15\sbin
"C:\Program Files\RabbitMQ Server\rabbitmq_server-3.7.15\sbin"

rabbitmq-service.bat remove
rabbitmq-service.bat install

rabbitmq-plugins enable rabbitmq_management

rabbitmq-service.bat stop
rabbitmq-service.bat install
rabbitmq-service.bat start

rabbitmq-server -detached

sc query rabbitmq

Rabbitmq-service start
sc query rabbitmq
rabbitmqctl stop
rabbitmqctl status


http://localhost:15672/ 
로그인 정보 : guest/guest 

​```

## RabbitMQ.Client C#  
- https://www.nuget.org/packages/RabbitMQ.Client