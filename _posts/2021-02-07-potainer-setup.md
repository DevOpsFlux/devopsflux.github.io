---
layout: post
title: "Portainer Docker 관리 환경 설정"
subtitle:   "Portainer Docker 관리 환경 정보"
date: 2021-02-07 20:00:00 -0400
categories: tip
tags: Portainer setup
---

## Portainer 환경 설정 정보

1. Portainer 설치
- Docker Web UI Container Management

```
- Volume 생성 및 설정
docker volume create portainer_data
docker volume ls 
docker volume ls | grep "portainer"
- Docker Data 폴더 마운트
	## docker run -d -p 9000:9000 -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data --restart=always portainer/portainer
docker run -itd --name myportainer -p 9000:9000 -v /tmp/dev/portainer_data:/data portainer/portainer
docker run -itd --name myportainer -p 9000:9000 -v /var/run/docker.sock:/var/run/docker.sock -v /tmp/dev/portainer_data:/data portainer/portainer
- 접속 실행
 > http://localhost:9000
 > admin/dev7********!
```

### 실행 화면
![1.Portainer-docker](/assets/img/post/potainer/img01.PNG)

![2.Portainer-데시보드](/assets/img/post/potainer/img02.PNG)

![3.Portainer관리](/assets/img/post/potainer/img03.PNG)

![4.Portainer-Container관리](/assets/img/post/potainer/img04.PNG)


### 참고
[portainer.io](https://www.portainer.io/){:target="_blank"}

[Portainer Documentation](https://documentation.portainer.io/){:target="_blank"}

[Portainer Docker](https://hub.docker.com/r/portainer/portainer){:target="_blank"}


