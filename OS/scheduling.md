# 스케쥴링 (Scheduling)

> CPU를 효율적으로 사용하기 위해 프로세스들 사이의 우선 순위를 관리

### 스케쥴러의 목적

* 처리율/CPU이용률 ↑

- 오버헤드/응답시간/반환시간/대기시간 ↓

### 프로세스 스케쥴러(Process Scheduler) 

OS의 일부로, 특정 시점에서 어떤 프로세스가 실행될지 결정한다.

<img src="image/process_scheduler.JPG" width="80%" height="80%" />

출처: https://rebas.kr/860

1. **장기 스케쥴러 (Long-term/admission scheduler)**

   > 어떤 프로세스를 메모리에 할당하고 READY QUEUE로 보낼지 결정

   디스크 내의 작업을 어떤 순서로 메모리에 가져올지 결정하는 프로그램

2. **중기 스케쥴러 (Medium-term scheduler, Swapping)**

   > Memory에서 프로세스를 일시적으로 제거하여 Disk에 배치 혹은 그 반대로 배치
   > (Swap-in, Swap-out)

   많은 프로세스들이 한번에 메모리에 올라왔을 때 디스크에 임시로 저장되는데, 이때 <u>어떤 프로세스를 메모리에 할당할지</u> 결정한다.

3. **단기 스케쥴러 (Short-term scheduler, <u>CPU scheduler</u>)**

   > READY QUEUE에 존재하는 프로세스 중 어떤 프로세스를 RUNNING 시킬지 결정

   CPU와 메모리 사이의 스케줄링을 담당하며, <u>프로세스에 CPU를 할당</u>한다 (**scheduler dispatch**). 이때, 프로세스를 CPU에 할당한다.

   

------

### CPU 스케쥴링 알고리즘

> READY QUEUE에 존재하는 프로세스 중 하나를 선택해 CPU를 할당하는 것 (*단기 스케쥴러)

* FCFS
* SJF
* Priority Scheduling
* Round Robin
* Multilevel-Queue
* Multilevel-Feedback-Queue