---
tags:
  - os
  - kernel
---


>커널이 자신을 보호하기 위한 인터페이스이다.  
>시스템 관련 서비스를 모아 함수 형태로 제공하며 사용자나 응용 프로그램으로부터 컴퓨터의 자원을 보호하기 위해 자원에 직접 접근하는 것을 차단한다.


### 특권명령(Privileged Instructions)
- CPU가 Kernel모드일 때만 CPU에서 실행될 수 있는 기계어 명령(ex. IO)
- mode bit이 0이면 사용자모드, 1이면 커널모드로 작동