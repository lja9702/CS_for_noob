## AMQP(응용 계층 메세지 전달 표준)

> **AMQP**(Advanced Message Queuing Protocol, 어드밴스트 메시지 큐잉 프로토콜)는 [메시지 지향 미들웨어](https://ko.wikipedia.org/wiki/메시지_지향_미들웨어)를 위한 [개방형 표준](https://ko.wikipedia.org/wiki/개방형_표준) [응용 계층](https://ko.wikipedia.org/wiki/응용_계층) 프로토콜이다.



과거 미들웨어 표준들은 API 레벨에서 구현되어 여러 구현체간 상호 운용성을 제공하지 않았다.

하지만, AMQP는 API 레벨이 아닌 **와이어 레벨 프로토콜**로 구현

​	와이어 레벨 프로토콜: 바이트 스트림으로 네트워크를 경유하며 송신되는 데이터의 형식을 기술

그렇기 때문에 이런 데이터를 만들고 해석할 수 있는 **도구**라면 구현 언어와 상관없이 **상호 운용이 가능!**



### AMQP 특징

+ 이기종 간 메세지 교환

  이기종 시스템간 벤더 종속 없이 표준화된 네트워크 프로토콜 사용

+ 속도 및 응답성

  비용, 시간적 측면에서 최대한 효율적인 메세지 교환

### AMQP 기본 구성

+ Publisher: 메세지 생성 및 Broker에 전달
+ Broker: Subscriber에 pub과 메세지 매칭 및 전달
+ Subscriber: Broker로부터 메세지 수신