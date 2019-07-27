---
layout: post
title: "Cloud-Native Day 2019 Seoul Review"
subtitle:   "Cloud-Native Day 2019 Seoul 참가 후기"
date: 2019-07-06 20:00:00 -0400
categories: review
tags: cloud-native review
---

## Cloud-Native Day 2019 Seoul 컨퍼런스 정보
- 일시 : 2019년 7월 4일(목) 09:30~17:30
- 장소 : EL Tower 그레이스 홀(6F) 
- 내용 : Cloud-Native Day 2019 Seoul
- 행사 : https://connect.pivotal.io/CND_Seoul_2019.html


## 주요 내용
- 클라우드 네이티브 전략과 로드맵 / 마이크로서비스의 디자인과 구현 전략
- Kubernetes, Itio, Envoy 등 오픈소스를 활용한 Any App, Every Cloud, One Platform 운영 전략
- 넷플릭스 케이스 스터디와 국내 실제 프로젝트로부터의 경험 공유
- 스페셜 핸즈온 세션: Spring Boot 기반의 마이크로서비스 아키텍처 구현하기

## 메인 컨퍼런스 내용

1. 클라우드 네이티브 IT를 위한 4가지 요소와 상관관계 - DevOps, CI/CD, Container, 그리고 MSA
- 4가지 요소인 : DevOps, CI/CD, Container, MSA 
- MSA 가 나머지 클라우드 네이티브 3 요소와 어떻게 상호작용하여 비즈니스에 도움이 되는지 조직 및 기술 측면으로 살펴 볼 수 있던 좋은 시간이었습니다.

2. MSA 전략 1: 마이크로서비스, 어떻게 디자인 할 것인가?
- DDD(Domain Driven Design) 방법론 : 현업 담당자와 협의 진행
- 모노리스 애플리케이션의 마이크로서비스 전환 방법론에 대한 모델링 과정에 대한 소개를 들을 수 있었습니다.
 1) 목표설정 (OKR)
 2) Event Storm
 3) Thin Slice 선택 - 데이터 기준 재 분리
 4) Boris - 아키텍처 표현
 5) Snap-E
 6) 테스트 완료 및 코드 생성
 7) 재사용 가능한 패턴 정리

3. MSA 전략 2: 마이크로서비스, 어떻게 구현할 것인가?
- MSA 컨테이너를 활용한 클라우드 네이티브 어플리케이션을 개발할 때 참고할 만한 레퍼런스 아키텍쳐와 개발 패턴 이야기를 들을 수 있었습니다.
- Netflix/OSS와 Spring Cloud이외에 다양한 패턴
- [https://www.slideshare.net/PivotalKorea/msa-1-154454835?from_m_app=android](https://www.slideshare.net/PivotalKorea/msa-1-154454835?from_m_app=android){:target="_blank"}

### 마이크로서비스 관련 패턴들
![img2](/assets/img/post/cloudnative/img2.jpg)

### MSA 관련 기술
![img3](/assets/img/post/cloudnative/img3.jpg)

### MSA 고려 사항
![img4](/assets/img/post/cloudnative/img4.jpg)


4. 클라우드 네이티브 플랫폼의 미래 - Kubernetes 기반의 PCF 로드맵
- Any App, Every Cloud, One Platform 전략
- Kubernetes, Istio, Envoy 등의 다양한 오픈소스를 어떻게 활용하고 플랫폼에 흡수하여 운영하는 방법
- [https://www.slideshare.net/PivotalKorea/kubernetes-pcf](https://www.slideshare.net/PivotalKorea/kubernetes-pcf){:target="_blank"}
![img5](/assets/img/post/cloudnative/img5.jpg)

5. 숨겨진 마이크로서비스: 초고속 응답과 고가용성을 위한 캐시 서비스 디자인
- MSA '팬아웃 효과' 문제 해결 과정
- 서비스 가용성 유지를 위해 캐시를 사용
- [https://www.slideshare.net/PivotalKorea/ss-154455324](https://www.slideshare.net/PivotalKorea/ss-154455324){:target="_blank"}
![img6](/assets/img/post/cloudnative/img6.jpg)
![img7](/assets/img/post/cloudnative/img7.jpg)
![img8](/assets/img/post/cloudnative/img8.jpg)