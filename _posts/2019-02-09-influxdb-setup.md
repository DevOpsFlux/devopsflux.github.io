---
layout: post
title: "influxDB 개발환경 설정"
subtitle:   "influxDB 설치 설정"
date: 2019-02-09 20:00:00 -0400
categories: tip
tags: influxdb setup
---


# influxDB 설치 및 개발 환경 정보
1. Windows 설치
- unzip influxdb-1.7.7_windows_amd64.zip
- https://dl.influxdata.com/influxdb/releases/influxdb-1.7.7_windows_amd64.zip
- [https://portal.influxdata.com/downloads/](https://portal.influxdata.com/downloads/){:target="_blank"}
- 설정 정보 : influxdb.conf 파일 수정

2. InfluxDB 실행
- influxd -config influxed.conf
- D:\ELK_Stack\influxdb\influxdb-1.7.7-1\influxd.exe
- D:\ELK_Stack\influxdb\influxdb-1.7.7-1\influxed.conf

3. InfluxDB 설정
- D:\ELK_Stack\influxdb\influxdb-1.7.7-1\influx.exe
- InfluxDB 사용자 인증설정 : influxdb.conf 파일 auth-enable = true 설정 InfluxDB 재시작

## InfluxDB 생성
```
0.  1) influxd.exe 서버 실행
	2) influx.exe 접속 실행

1. DB생성  : CREATE DATABASE <database name>
	CREATE DATABASE testdb 
2. DB 사용 : use <database name>
	use testdb

3. DB Insert :
	insert monitoring,cpu=i5,core=5 memory=600,disk=50000

4. DB Select : 
	SELECT * FROM <measurement name> 
	select * from monitoring
```

## Tutorial
- influxDB line protocol tutorial
  [https://docs.influxdata.com/influxdb/v1.7/write_protocols/line_protocol_tutorial/](https://docs.influxdata.com/influxdb/v1.7/write_protocols/line_protocol_tutorial/){:target="_blank"}

- InfluxDB plugin for Grafana
  [https://grafana.com/grafana/plugins/influxdb](https://grafana.com/grafana/plugins/influxdb){:target="_blank"}


### 설치 및 설정 화면

![img1](/assets/img/post/influxdb/img01.PNG)

![img2](/assets/img/post/influxdb/img02.PNG)

![img3](/assets/img/post/influxdb/img03.PNG)

![img4](/assets/img/post/influxdb/img04.PNG)

