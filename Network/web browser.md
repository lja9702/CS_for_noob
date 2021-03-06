# 웹 브라우저 동작 과정

> 브라우저 주소창에 URI를 입력했을 때 어떤 과정을 거쳐 화면에 보이는지 알아보자



### 큰 틀에서의 동작 과정

1. 클라이언트(브라우저)에서 자원(html 문서, pdf, image, ..)을 서버에 요청한다.
2. 서버는 자원을 넘기고 연결을 끊고, 브라우저에서는 자원을 받고 연결을 끊는다.

### 세부적인 동작 과정

1. 주소창에 url을 입력하고 enter를 누르면, **서버에 요청이 전송**
2. 서버가 해당 페이지에 존재하는 **여러 자원들이 브라우저로 보냄**
3. 이제 브라우저는 자원이 담기 html과 css를 W3C명세에 따라 해석(**'렌더링 엔진'**)
4. 렌더링 엔진은 html 파싱을 하고, html 파서가 문서에 존재하는 어휘와 구문을 분석하면서 DOM트리를 구축
5. 이후 css 파싱하고, css파서가 모든 css정보를 스타일 구조체로 생성
6. 이 두가지를 연결시켜 **렌더 트리**를 만듬. 렌더트리를 통해 문서가 시각적 요소를 포함한 형태 구성이 됌
7. **화면에 배치를 시작**하고, UI백엔드가 노드를 돌며 형상을 그림
8. 이때 빠른 브라우저 화면 표시를 위해 **'배치와 그리는 과정'을 자원을 전송받는 동시에 일부분을 먼저 화면에 표시하고, 기다림**