## Firebase

![](./img/firebase.png)

Firebase Realtime Database는 **NoSQL 클라우드 호스팅 데이터베이스**이다. 데이터는 JSON으로 저장되며 연결도니 모든 클라이언트에 실시간으로 동기화된다. 교차 플랫폼 앱 개발 시 모든 클라이언트가 하나의 실시간 데이터베이스 인스턴스를 공유하고 자동 업데이트로 최신 데이터를 수신한다. 

[출처 : Firebase Docs](https://firebase.google.com/docs/database)

</br>

### 왜 NoSQL인가? 

- Firebase는 SQL을 사용하지 않고 JSON 방식의 문서를 사용한다.
- Key-Value와 Document 스타일의 JSON을 사용한다.

</br>

### 사용 시 장점

- 개발 시간 단축

  Database가 실시간으로 연동되기 때문에 backend 개발에 대한 시간 투자 줄일 수 있음, 애플리케이션 서버가 불필요함

- Offline 기능

  데이터를 디스크에 유지하므로 Firebase 앱은 오프라인일 때도 원활하게 작동함

- 다양한 클라이언트에 동기화 가능

  ios, Android, 자바스크립트 로 교차 플랫폼 개발 시 하나의 데이터베이스를 공유할 수 있음

### 사용 시 단점

- 응답 속도가 느림

  응답 속도가 느릴 수 있음 (서버가 해외에 있기 때문에 처리 속도에 지연 발생)

- NoSQL의 단점을 가지고 있음 