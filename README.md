# Basic_Ajax

<a href="http://tcpschool.com/ajax/intro">참조_TCP School</a>

### Ajax 개요
Ajax(Asynchronous JavaScript and XML)
- HTML, CSS, JS, DOM, XML과 같이 기존에 사용되던 여러 기술을 함께 사용하는 새로운 개발 기법이다
- 동적인 웹 페이지를 만들기 위한 개발 기법
- 웹 페이지 전체를 다시 로딩하지 않고, 웹 페이지의 일부분만 갱신할 수 있다
- 다음과 같은 형태의 데이터를 주고받는다.
  - JSON
  - XML
  - HTML
  - 텍스트 파일 등
  
Ajax 장점
- 웹 페이지 전체를 로딩하지 않고, 일부만 갱신할 수 있다
- 웹 페이지가 로드된 후 서버로 데이터 요청을 보낼 수 있다
- 웹 페이지가 로드된 후 서버로부터 데이터를 받을 수 있다
- 백그라운드 영역에서 서버로 데이터를 보낼 수 있다

Ajax 한계
- 클라이언트 풀링 방식(클라이언트가 서버에 데이터를 요청)으로 서버 푸시 방식의 실시간 서비스는 만들 수 없다
- 바이너리 데이터를 보내거나 받을 수 없다
- Ajax 스크립트가 포함된 서버가 아닌 다른 서버로 Ajax 요청을 보낼 수 없다
- 클라이언트 PC로 Ajax요청을 보낼 수 없다

클라이언트 풀링(Client Pooling)
- 사용자가 직접 원하는 정보를 서버에 요청하여 얻는 방식

서버 푸시(Server Push)
- 사용자가 요청하지 않아도 서버가 알아서 자동으로 특정 정보를 제공
- Ex) 스마트 폰에서 각종 앱이 보내는 푸시 알림

Ajax 구성 요소
- 웹 페이지의 표현을 위한 HTML과 CSS
- 데이터에 접근하거나 화면 구성을 동적으로 조작하기 위해 사용되는 DOM 모델
- 데이터의 교환을 위한 JSON이나 XML
- 웹 서버와의 비동기식 통신을 위한 XMLHttpRequest 객체
- 사용자의 작업 흐름을 제어하는 데 사용되는 JS

Ajax 동작 원리
- 위에서 언급한 구성 요소들을 사용한다
- JS를 통해 웹 서버와 통신
<img height="500px" src="http://tcpschool.com/lectures/img_ajax_ajax_application.png" />

1. 사용자에 의한 요청 이벤트 발생
2. 이벤트 핸들러에 의해 JS 호출
3. XMLHttpRequest 객체를 사용하여 서버로 요청
4. 서버는 전달받은 XMLHttpRequest 객체를 가지고 Ajax 요청 처리
5. 서버는 처리 결과를 HTML, XML, JSON 형태로 웹 브라우저에 전달
6. 5~6
7. 전달받은 데이터를 가지고 페이지의 일부만을 갱신하는 JS 호출
8. 페이지의 일부만 다시 로딩되어 표시

문서 객체 모델 DOM(Document Object Model)
- HTML문서나 XML문서에 접근하기 위한 인터페이스
- 문서 내의 모든 요소의 목적과 특징 정의, 각 요소에 접근하는 방법 제공
<img src="http://tcpschool.com/lectures/img_js_htmldom.png" />
