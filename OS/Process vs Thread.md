# 프로세스(Process) vs 스레드(Thread)

## 프로세스 (Process)

> 메모리 상에서 실행중인 프로그램 작업

- 실행중인 프로그램을 Disk로 부터 메모리에 적재되어 CPU 할당을 받음
- 프로세스마다 최소 1개의 스레드(메인 스레드) 소유

### 프로그램(Program)과 프로세스(Process)

- 프로그램은 실행할 수 있는 파일(.exe)
- 프로세스는 메모리에 올라와 cpu를 할당받고 프로그램이 실행되고 있는 상태

</br>

### 프로세스 주소 공간

프로세스는 각각 별도의 주소공간을 할당한다. (독립적)

<img src="image\processAddrSpace.png" alt="processAddrSpace" width="50%" height="50%" />

* Code 영역: 코드 자체를 구성하는 메모리 영역 (프로그램 명령)

* Data 영역: 전역변수, 정적변수, 배열 등

* Heap 영역: 동적할당 시 사용 (new(), malloc() 등)

* Stack 영역: 지역변수, 매개변수, 리턴 값 (임시 메모리 영역)


</br>

## 스레드 (Thread)

> 프로세스 안에서 실행되는 여러 흐름 단위

- 스레드 ID, 프로그램 카운터(PC), 레지스터 집합, 스택으로 구성

- Code, Data, Heap은 공유한다

**프로세스는 자신만의 고유공간과 자원을 할당받는 반면,**
**스레드는 다른 스레드와 주소 공간/자원을 공유한다는 차이가 존재**

</br>

<img src="image\Thread.png" width="50%" height="50%"/>