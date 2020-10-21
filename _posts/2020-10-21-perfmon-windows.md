---
layout: post
title: "Windows Server 성능 모니터링 - Perfmon"
subtitle:   "Windows Server 성능 모니터링 활용"
date: 2020-10-21 20:00:00 -0400
categories: tip
tags: tools
---

# 성능모니터 설정 : Performance Counter
- 실행창(Windows Key + R) > perfmon.msc
- 제어판 > 관리 도구 > 성능 모니터
- 서버관리자 > 도구 > 성능모니터
```
1. 성능모니터 로그 수집 설정
 - 성능모니터 > 데이터 수집기 집합 > 사용자 정의 > 새로만들기 > 데이터 수집기 집합 추가

2. 성능모니터 카운터 추가 
 - Web Service > Anonymous Users/sec (동시 접속자수) [배율:1.0]    
 - Active Server Page > Requests/Sec (초당 처리된 요청 수)
 - Active Server Page > Requests Queued (처리 대기중 요청 수)
 - Active Server Page > Requests Rejected (HTTP 503 상태 코드를 반환하는 요청 수)
 - Active Server Page > Requests Executing (처리 중인 요청 수)
 - Active Server Page > Requests Executtion Time (요청 처리 시간)
 - Active Server Page > Requests Disconnected (통신 오류로 인해 연결이 끊어진 요청 수)

 - Active Server Pages\Request Wait Time : 가장 최근의 요청이 큐에서 기다리는 밀리세컨드 수
 - Active Server Pages\Requests Queued : 처리되기 위해 기다리는 요청 수
 - Active Server Pages\Requests Rejected : 실행되지 않는 전체 요청 수. 요청이 실행되지 얂는 이유는 처리할 리소스가 없기 때문이다.
 - Active Server Pages\Requests/sec : 초당 실행된 요청 수
```

---
# ※ 주요 모니터링 항목
```
 - Current Connections : 현재 연결 수 (Client와 연결된 TCP Connection의 개수)
 - Users/sec : 동시 접속자 수(현재 처리 중인 익명 사용자의 요청 수/초)
 - Requests/Sec : 초당 처리된 요청 수
- Active Server Page > Requests Disconnected
 - 통신 오류로 인해 연결이 끊어진 요청 수입니다.

- Active Server Page > Requests Executing
 - 현재 처리 중인 요청 수입니다.

- Active Server Page > Requests/Sec
 - 초당 처리된 요청 수입니다. 이 값은 애플리케이션 현재 처리량을 나타냅니다.

- Active Server Page > Requests Queued 
 - 처리를 위해 대기 중인 ASP 스크립트의 수
 - 대기열에서 서비스를 기다리는 요청 수를 모니터링
 - 스트레스 상황에서 지연된 요청 수가 상당히 증가할 경우 프로세서 사용률은 비교적 낮게 남아있고
   이것은 스크립트가 처리할 수 있는 것보다 많은 호출을 수신하는 COM 개체를 호출하고 있다는 표시
 - 동시 사용자 수가 500 이상인 상황에서 이 값이 5 이상의 값을 나타내면 웹 서버의 처리 능력을 초과한 것입니다.

- Active Server Page > Requests Rejected
 - 서버 리소스 부족으로 인해 처리되지 않은 총 요청 수입니다. 이 카운터는 서버가 사용 중임을 나타내는 HTTP 503 상태 코드를 반환하는 요청 수를 나타냅니다.
```

## 성능모니터 모니터링
![img01](/assets/img/post/perfmon/img01.jpg)
![img02](/assets/img/post/perfmon/img02.jpg)
![img03](/assets/img/post/perfmon/img03.jpg)

## 성능모니터 로그 
![img05](/assets/img/post/perfmon/img05.jpg)

## Performance Counter 및 nGrinder 성능 모니터
![img07](/assets/img/post/perfmon/img07.jpg)
![img08](/assets/img/post/perfmon/img08.jpg)

## EMS Solution - POLESTAR 모니터링
![img06](/assets/img/post/perfmon/img06.jpg)

[ 참고 자료 ]
- https://docs.microsoft.com/ko-kr/sql/reporting-services/report-server/performance-counters-reportserver-service-performance-objects?view=sql-server-2016
- https://docs.microsoft.com/ko-kr/windows-server/administration/windows-commands/perfmon
- https://studyforus.tistory.com/161
- https://www.nextstep.co.kr/121
- 성능모니터 데이터 로그 수집 : https://kkarijoo.tistory.com/106
- Current Connections Web Service / Current Connections : https://nsinc.tistory.com/44
- https://techcommunity.microsoft.com/t5/ask-the-performance-team/windows-performance-monitor-overview/ba-p/375481

