## TCP 흐름제어

> TCP는 신뢰성있는 전송을 보장
>
> 흐름제어 기법은 TCP의 신뢰성을 보장해주는 수단 중 하나
>
> 송수신 측의 데이터 처리 속도 차이로 발생하는 <u>문제</u>를 해결
>
> 수신측이 주체

#### 어떤 문제?

1. 각 소켓은 I/O 버퍼를 가지고 있다.
2. 각 버퍼의 용량에는 한계가 존재한다.
3. 만약 송신자의 처리 속도가 수신자보다 빠를 경우에는?
4. 언젠가 수신자의 버퍼는 꽉차게 되고 나머지 데이터는 손실 ~~신뢰성의 TCP~~ 

*****

### 방식

1. Stop and Wait 방식
2. **Windowing 방식**

*****

#### Stop and Wait

<img src="image\flow_control.png" alt="Stop_and_Wait" style="zoom:100%;" />

Timeout 시간안에 ACK가 도착하면 그 다음 데이터를 전송

하나 받고 하나 보내는 방식이기 때문에 **비효율적**

*****

#### Windowing 방식 (Sliding Window) 

> 하나씩 보내는 Stop-and-Wait와 달리 여러 데이터를 한번에 보내는 방식
>
> 수신 측의 윈도우 크기만큼 송신 측에서 확인 응답 없이 데이터를 전송
>
> 수신자의 여유 버퍼에 따라 윈도우를 크기를 동적으로 제어

<img src="image\sliding_window.png" alt="sliding_window" style="zoom:100%;" />

TCP/IP를 사용하는 호스들은 Receive/Send 윈도우를 보유

3-way handshaking 과정에서 각 호스트는 서로의 window 크기를 공유하여 

수신자의 Receive window 크기에 송신자의 Send window크기를 맞춤



1. 윈도우에 포함되는 모든 패킷을 일단 전송
2. 수신자는 해당 패킷을 받았다고 송신자에게 ACK
3. 송신자가 ACK를 받으면 그만큼 윈도우를 이동시켜 다른 패킷을 전송