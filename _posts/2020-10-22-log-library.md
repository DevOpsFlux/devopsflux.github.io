---
layout: post
title: ".NET 로그 라이브러리 비교"
subtitle:   ".NET 로그 라이브러리 성능 및 로그 유실률 비교"
date: 2020-10-22 20:00:00 -0400
categories: tip
tags: etc
---

## .NET 로그 라이브러리 검토
- 현재 주문/예매 접근 트래픽 발생 로그의 경우 EOS 대상 및 대량 트래픽 발생 성능 이슈로 향후 프로세스 변경 개선 필요
- 대량 트래픽 고려한 신규 접근 로그 라이브러리 검토 필요. 일부 연동 파일로그 확인 시 누락건 발생으로 검토 진행
- 로깅 라이브러리 성능 테스트 benchmarks 관점에서 추가적으로 로그의 유실 방지 안정성 고려 테스트 검토 진행
- Nlog vs log4net vs Serilog

## 로그 라이브러리 관심도 및 활성 지수
- Serilog vs NLog 비교 검토
- Code Quality Rankings - Lumnify : https://lumnify.com/grades/?rel=libhunt-cmp

![img01](/assets/img/post/loglib/img01.jpg)
![img02](/assets/img/post/loglib/img02.jpg)
![img03](/assets/img/post/loglib/img03.jpg)

## 로그 라이브러리 성능 밴치 마크 자료
- Logging Performance  
- Serilog 2.7.1  vs NLog 4.5.7 
- https://github.com/panchengtao/LoggingPerformance/issues/1 
- https://www.darylcumbo.net/serilog-vs-nlog-benchmarks/

![img04](/assets/img/post/loglib/img04.jpg)

## 로그 유형 정보 및 테스트 툴 정보
- nGrinder, Jmeter, StressThreadHttp Tool 활용
![img05](/assets/img/post/loglib/img05.jpg)

## 로그 유형 및 CASE 테스트
![img06](/assets/img/post/loglib/img06.jpg)
![img07](/assets/img/post/loglib/img07.jpg)

## 티켓 접근 로그 라이브러리 선정
- 로그 유형별 테스트 결과 로그 유실율이 낮은 NLog 라이브러리를 최종 선정

## NLog  
- .NET 표준 및 .NET 플랫폼을 위한 유연한 로깅 플랫폼 
- 사용이 쉽고, 설정은 설정 파일과 소스 코드를 통한 2가지 방법 제공 
- 옵션 지정으로 비동기 로깅 등 지원 
- 구조화 된 다양한 로깅 지원 
- 제공된 다양한 싱크 확장성, 여러 대상 플랫폼과 연결이 유용. (데이터베이스, 파일, 콘솔 등) 
- 최신 .NET 플랫폼간에 이식 가능 - 테스트 결과 안정된 성능 및 로그 유실 안정성 우수

## Serilog
- Serilog의 구성은 NLog 및 log4net 처럼 XML 구성이 필요 없어 유연한 인터페이스를 사용하므로 매우 간결하게 사용 가능
- 최신 .NET 플랫폼간에 이식 가능
- 제공된 다양한 싱크 확장성 : Serilog의 구조화 된 다양한 로깅 지원 
  Console / File / Seq / ElasticSearch 등에 로그인하도록 쉽게 구성 가능
- API는 더 현대적이며 설정하기가 쉽고 유지 관리가 잘되며 기본적으로 구조적 로깅을 수행
- 구조화 된 로깅은 로깅 할 데이터가 구조화 된 형식으로 작성되도록하여 이벤트 데이터를 쉽게 쿼리 할 수있게합니다. 형식은 XML, JSON 또는 데이터 구문 분석을 쉽게하는 기타 구조화 된 형식이 될 수 있습니다. 구조화 된 로깅은 로그 분석을 위해 로그 파일을 처리하는데도 도움이됩니다.
- 구조화 된 형식을 사용하여 로그를 저장하는 경우 명명 된 속성을 전달 된 인수와 연결합니다 (즉, 정규식 등을 사용하지 않고 검색 / 필터링 지원)
- 구조화 된 로깅과 "구조화 된 쿼리"를 사용할 때 검색 결과의 관련성이 훨씬 높아집니다.
- 로그 파일의 구성 및 관리이며, 문자열 형식을 다른 형식으로 형식화하는 방법이 아니라 다른 방법은 성능입니다. 
- Apache 재단 후원을 받고 있으며, 지속적으로 개선 진행이 되고 있습니다.
```
  > log.디버그("사용자 ID는 {@userId}", userId입니다);
  > _logger.Information("Access Control: User {User} granted access to module {Module}", user, module);
  > "Access Control: User {User} granted access to module {Module}"
		{
			"User": "daryl",
			"Module": "User Management"
		}
```

## 로그 테스트 버젼 정보
```
Serilog -Version 2.9
NLog -Version 4.6.8

Install-Package NLog -Version 4.6.8
Install-Package Newtonsoft.Json -Version 12.0.3

Install-Package Serilog -Version 2.9.0
Install-Package Serilog -Version 2.8.0
Install-Package Serilog.Sinks.File -Version 4.1.0
```

[ 참고 자료 ]
---
## 로그라이브러리 밴치 마크
- nlog-vs-log4net-vs-serilog/
  https://stackify.com/nlog-vs-log4net-vs-serilog/
  https://www.slant.co/topics/61/versus/~nlog_vs_log4net_vs_serilog
- serilog-vs-nlog-benchmarks/
  https://www.darylcumbo.net/structured-logging/	
  https://www.darylcumbo.net/serilog-vs-nlog-benchmarks/
- LoggingPerformance 
  > Serilog < NLog < NLog Async
  https://github.com/pcTOR/LoggingPerformance/issues/1
  https://www.darylcumbo.net/serilog-vs-nlog-benchmarks/

## serilog vs nlog
- 관심도 및 활성 지수
https://dotnet.libhunt.com/compare-serilog-vs-nlog
- 장/단점
https://www.slant.co/topics/61/versus/~nlog_vs_log4net_vs_serilog
- 구조적 로깅과 기본 로깅의 장점
https://qastack.kr/software/312197/benefits-of-structured-logging-vs-basic-logging

---
- NLog 
https://nlog-project.org/
https://www.slideshare.net/jacking/n-log
http://deep-depth.blogspot.com/2014/01/net-low-latency-logging-part-2-nlog.html
옵션 튜닝 : https://github.com/nlog/NLog/wiki/File-target
- Network-target
https://github.com/NLog/NLog/wiki/Network-target
https://nlog-project.org/2019/03/20/nlog-4-6-is-live.html
- Configuration.Variables 설정
https://jacking75.github.io/csharp_nlog_dynamic_file_path/
https://github.com/NLog/NLog/wiki/Var-Layout-Renderer

---
## serilog
https://github.com/serilog/serilog/wiki
https://gitter.im/serilog/serilog
https://github.com/serilog/serilog-sinks-async/
https://www.csharpcodi.com/csharp-examples/Serilog.ILogger.Write(Serilog.Events.LogEvent)/
https://dzone.com/articles/serilog-tutorial-for-net-logging-16-best-practices
- loglevel
https://github.com/serilog/serilog/wiki/Configuration-Basics
- Serilog Tutorial
https://blog.datalust.co/serilog-tutorial/