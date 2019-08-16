---
layout: post
title: "Grafana 개발환경 설정"
subtitle:   "Grafana 설치 모니터링"
date: 2019-02-07 20:00:00 -0400
categories: tip
tags: grafana setup
---


# Grafana 설치 및 개발 환경 정보
1. Windows 설치
- grafana-6.2.5.windows-amd64.msi
- [https://grafana.com/grafana/download?platform=windows](https://grafana.com/grafana/download?platform=windows){:target="_blank"}
- [https://grafana.com/docs/installation/windows/](https://grafana.com/docs/installation/windows/){:target="_blank"}

- CMD 명령프롬프트를 실행 후 압축을 해제한 곳으로 이동 후 bin/폴더로 이동 후 grafana-server 명령어를 실행
- C:\Program Files\GrafanaLabs\grafana\bin\grafana-server.exe

2. Service 확인
 - Service Status
 CMD Shell
   > sc query Grafana
 PowerShell 
   > Get-Service Grafana | fl

![img2](/assets/img/post/grafana/img02.PNG)

3. grafana 사이트 접속
- http://localhost:3000
- Default port : 3000
- Default id/password : admin/admin
- 설정 정보 : C:\Program Files\GrafanaLabs\grafana\conf\defaults.ini
- Configuration : https://grafana.com/docs/v3.1/installation/configuration/

![img3](/assets/img/post/grafana/img03.PNG)


## Grafana Plugins   
- [https://grafana.com/plugins](https://grafana.com/plugins){:target="_blank"}
```
grafana-cli가 있는 폴더로 이동 후 파워쉘 실행
.\grafana-cli.exe plugins install michaeldmoore-annunciator-panel
grafana-cli plugins install michaeldmoore-annunciator-panel
```

## Windows IIS Server Grafana
- How to Use IIS with URL Rewrite as a Reverse Proxy for Grafana on Windows  
  [https://grafana.com/docs/tutorials/iis/](https://grafana.com/docs/tutorials/iis/){:target="_blank"}

- Download and install the URL Rewrite module for IIS : 
  [https://www.iis.net/downloads/microsoft/url-rewrite](https://www.iis.net/downloads/microsoft/url-rewrite){:target="_blank"}


### 실행 화면

![img4](/assets/img/post/grafana/img04.PNG)

![img7](/assets/img/post/grafana/img07.PNG)

![img5](/assets/img/post/grafana/img05.PNG)

![img6](/assets/img/post/grafana/img06.PNG)



