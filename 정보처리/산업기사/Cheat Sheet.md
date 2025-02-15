### 1. 정보시스템 기반 기술
- **응용 SW기초 기술 활용**
처리 능력 (Throughput) - 일정 시간 내에 시스템이 처리 하는 일의 양
사용 가능도 (Availability) - 시스템의 자원을 사용할 필요가 있을 때 즉시 사용 가능한 정도
신뢰도 (Reliability) - 시스템이 주어진 문제를 정확하게 해결하는 정도
반환 시간 (Turn Around Time) - 시스템에 작업을 의뢰한 시간부터 처리가 완료될 때까지 걸린 시간

시스템:
일괄 처리 (Batch Processing) - 1세대
실시간 처리 (Real-time Processing) - 2세대
다중 프로그래밍 (Multiprogramming) - 2세대
다중 처리 (Multiprocessing) - 2세대
시분할 (Time-sharing) - 2세대
다중 모드 (Multimode) - 3세대
분산 처리 (Distributed Processing) - 4세대
(above, talk about what's the goal, to increase or to decrease)

프로세스의 여러 가지 정의
- PCB를 가진 프로그램
- 실기억장치(주기억장치)에 저장된 프로그램
- 프로세서가 할당되는 실체
- 프로시저가 활동중인 것
- 비동기정 (async) 행위를 일으키는 주체
- 지정된 결과를 얻기 위한 일련의 계통적 동작 (series of systematic actions)
- 목적 또는 결과에 따라 발생되는 사건들의 과정

![[Pasted image 20250215150515.png]]
비선점 (non-preemptive) - FCFS(FIFO), SJF, HRN (Highest Response-ratio Next)
- HRN: 우선순위 계산식 = (대기 시간 + 서비스(실행) 시간) / 서비스(실행) 시간
선점 (pre-emptive) - RR, SRT, MQ, MFQ

반환 시간 (turnaround) = time of completion

세마포어 - P (down), V (up)

상호 배제 (mutual exclusion)
점유와 대기 (hold and wait)
비선점 (non-preemption)
환형 대기 (circular wait)

은행원 알고리즘 (Banker's Algorithm) used to avoid deadlocks

배치 (placement) 전략: 최초 (first fit), 최적 (best fit), 최악 (worst)

기상 기억장치 (virtual memory):
- 페이징 (paging) - 프로그램과 주기억장치의 영역을 (area) 동일한 크기로 나눈 후 나눠진 프로그램(페이지)을 동일하게 나눠진 주기억장치의 영역(페이지프레임)에 적재시켜 (load) 실행한다. page map table
- 세그먼테이션 (segmentation) - 프로그램을 가변적인 크기의 논리적인 단위로 나눈다. segment map table

워킹 셋 (working set) - 프로세스가 일정 시간 동안 자주 참조하는 페이지들의 집합
구역성 (locality) - 프로세스가 실행되는 동안 주기억장치를 참조할 때 일부 페이지만 집중적으로 참조하는 성질이 있다는 이론 (시간, 공간 구역성)

벨레이디의 모순 (Belady's Anomaly) - increasing the number of pages results in an increase in the number of page faults (for FIFO)

직접 파일 (Direct File) - 파일을 구성하는 레코드를 임의의 물리적 저장공간에 기록하는 것. uses hashing function
색인 순차 파일 (Indexed Sequential File) - 트랙 (Track), 실린더 (Cylinder), 마스터 (Master) 색인 영역 

파일 디스크립터 (FD) - 이름, 크기, 보조기억장치에서의 파일 위치, 파일 구조 ({색인} 순차, 직접), 보조기억장치의 유형, 엑세스 제어 정보, 파일 유형, 생선 잘짜와 시간, 최종 수정 날짜 및 시간, 엑세스한 횟수  

자원 보호:
접근 제어 행렬 (Access Control Matrix) - the table itself
접근 제어 리스트 (Access Control List) - the file
권한(자격) 리스트 (Capability List) - the user 
![[Pasted image 20250215162545.png]]

약결합 (loosely coupled) - 분산 처리 -> 독립된 OS + 메모리, 통신망을 통해 연결
강결합 (tighly coupled) - 다중 처리 -> 동일 OS, 메모리 공유 

스타형/성형 - point-to-point
망형 - 완전 연결형 - n(n-1)/2 링크

UNIX - 시분할 시스템 (Time Sharing System)을 위해 설계된 대화식 OS; 다중 사용자/작업 (multi-user/tasking); 트리 구조

커널 (Kernel) - UNIX 핵심 부분; 주기억장치에 적재된 후 상주하면서 실행; CPU Scheduling/기억장치/파일/입,출력 관리, 프로세스 통신, 데이터 전송
쉘 (Shell) - 사용자 명령어 인식; 시스템, 사용자 간의 인터페이스; DOS의 COMMAND.COM과 같은 기능; 명령어가 포함된 파일 형태로 존재; Bourne/C/Korn Shell

UNIIX I-nodes 블록: 부트 (부팅 시 필요한 코드 저장), 슈퍼 (전체 파일 시스템에 대한 정보), I-node (각 파일/디렉터리에 대한 모든 정보를 저장), 데이터 (디렉터리 엔트리와 실제 파일에 대한 데이터가 저장된 블록)

chmod - change mode
ps - process state

모뎀 - carries out 변조 (MOdulation, D -> A data) and 복조 (DEModulation, A -> D data) 
DSU (D data -> D signal)
CODEC (A data -> D signal)

데이터 단말기 (DTE - Data Terminal Equipment), 데이터 회선 종단장치 (Data Circuit-Termianting Equipment)
- 기계적 인터페이스 - RS-232C (w/ 25pin)
페킷형 터미널을 위한 DTE/DCE 접속 규격은 X25

주파수 분할 다중화기 (FDM) - 보호 대역 (guard band) -> 채널 간섭을 막기 위함
시분할 다중화기 (TDM) - 시간 폭 (time slot)
- 동기식 시분할 다중화기 (STDM, sync) - 균등한 (even) 시간 폭
- 비동기식 시분할 다중화기 (ATDM, async) - 필요한 장치에만 시간 폭 

광섬유 케이블 (Optic Fibre Cable) - 도청이 (wiretapping) difficult, 저손실성 (low loss), 무누화, 무유도 (non-inductive) thus resistant to electromagnetic noise, 감쇠율 (attenuation) low
- 코어 (core) - 빛은 전파되는 영역 (클래드보다 높은 굴절률 (refractive index)을 가진다)
- 클래드 (clad) - 코어의 빛을 반사시켜 외부로 빠져나가지 못하게 하고, 외부의 압력으로부터 보호한다
- 재킷 (jacket) - 습기, 마모, 파손, 등의 위험으로부터 내부를 보호한다
![[Pasted image 20250215170924.png]]

변조 속도: baud = 1/T
데이터 신호 속도 (bps) = 변조 속도 (baud) x 변조 시 상태 변화 수 (monobit, dibit, tribit, quadbit)
샤논 (Shannon)의 정의: $$C = W \times log_{2}{(1 + \frac{S}{N})[bps]}$$ C = 통신 용량 (Capacity, max achievable data rate), W = 대역폭, S = 신호 전력 (signal power), N = 잡음 전력 (noise power)
- 전송로의 통신 용량을 늘리기 위한 방법 (주파소 대역폭 up, 신호 세력 up, 잡음 세력 down)

진폭 편이 변저 (ASK): 2진수 0과 1을 서로 다른 진폭의 신호로 변조
주파수 편이 변조 (FSK): 2진수 0과 1을 서로 다른 주파수로 변조
위상 편이 변조 (PSK):  2진수 0과 1을 서로 다른 위상을 갖는 신호로 변조
직교 진폭 변조 (QAM): 반송파의 진폭과 위상을 상호 변환하여 신호를 얻는 변조 방식

- **애플리케이션 설계**
- **테스트 및 배포**
- **정보시스템 기반 기술 용어**
### 2. 프로그래밍 언어 활용
1. 프로그래밍 언어 활용
2. 프로그램 구현
### 3. 데이터베이스 활용
1. 데이터베이스의 이해
2. SQL 활용
3. 데이터베이스 프로그래밍

---
to cleanup:
[1과목]
계층:
네트워크 - 네트워크 연결 관리 및 데이터의 교환 및 중계 기능
물리 - 전송에 필요한 두 장치 간의 실제 접속과 절단 등 기계적, 전기적, 기능적, 절차적 특성을 정의함
데이터 링크 - 두 개의 인접한 개방 시스템들 간에 신뢰성 있고 효율적인 정보 전송을 할 수 있도록 함
전속 - 종단 시스템 (end-to-end) 간에 투명한 데이터 전송을 가능하게 함


[3과목]
관계대수는 질의에 대한 해를 생성하기 위해 수행해야 할 연산의 순서를 명시하는 **절차적** 언어