# TCP (전송 계층 프로토콜)

> 네트워크 통신에서 신뢰적인 연결 방식(전송 중 데이터가 소멸되지 않음을 보장)
>
> 비신뢰적인 네트워크에서 <u>신뢰적인 네트워킹을 보장할 수 있도록 하는 프로토콜</u>
>
> 전송 순서대로 데이터를 수신하며 데이터의 경계가 없음
>
> 1:1의 소켓 연결 구조 



### **3 way handshake**

<u>통신하기 앞서</u>, 논리적인 접속을 성립하기위해 3 way handshake 과정을 진행한다.

**Server:** 포트가 열린 상태로 연결 요청 대기중 (LISTEN)

**Client:** 포트가 닫힌 상태 (Closed)

<img src="image/3_way_handshake.JPG" alt="3_way_handshake" width="80%" height="80%" />

출처: https://hyeonstorage.tistory.com/286



1.  Client에서 Server에 연결 요청을 하기위해 SYN(동기화) 패킷을 보낸다.

2. Server의 해당 포트는 SYN 패킷을 받고 SYN_RCV(동기화 패킷 받음)으로 상태가 변경된다. 
   그리고 ACK (정상적으로 받음)와 Client도 포트를 열어달라는 SYN를 같이 보낸다.

3. Client가 ACK+SYN을 받고 ESTABLISHED로 상태를 변경하고, 서버에 요청을 잘 받았다는 ACK를 전송한다. ACK를 받은 서버는 ESTABLISHED로 변경된다.

   

---------------

### **4 way handshake**

<u>통신을 해제</u>하기 위해 4 way handshake 과정을 진행한다.

Server와 Client 모두 ESTABLISHED 상태

<img src="image/4_way_handshake.JPG" alt="4_way_handshake" width="80%" height="80%" />

1. Client는 Server에게 FIN(연결종료)을 보낸다.

2. Server는 FIN을 받고, 확인했다는 ACK를 Client에게 보낸다. 

3. 데이터를 모두 보내면, FIN을 Client에게 보낸다.

4. Client는 FIN을 받고, 확인했다는 ACK를 서버에게 보낸다. 
   (서버로 부터 아직 받지 못한 데이터가 있을 수 있어 TIME_WAIT로 대기) 

5. 이후 둘다 Closed => 연결해제
