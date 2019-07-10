# Basic_Ajax

<a href="http://tcpschool.com/ajax/intro">참조_TCP School</a>

### Ajax(Asynchronous JavaScript and XML)
- HTML, CSS, JS, DOM, XML과 같이 기존에 사용되던 여러 기술을 함께 사용하는 새로운 개발 기법이다
- 동적인 웹 페이지를 만들기 위한 개발 기법
- 웹 페이지 전체를 다시 로딩하지 않고, 웹 페이지의 일부분만 갱신할 수 있다
- 다음과 같은 형태의 데이터를 주고받는다.
  - JSON
  - XML
  - HTML
  - 텍스트 파일 등
  
### Ajax 장점
- 웹 페이지 전체를 로딩하지 않고, 일부만 갱신할 수 있다
- 웹 페이지가 로드된 후 서버로 데이터 요청을 보낼 수 있다
- 웹 페이지가 로드된 후 서버로부터 데이터를 받을 수 있다
- 백그라운드 영역에서 서버로 데이터를 보낼 수 있다

### Ajax 한계
- 클라이언트 풀링 방식(클라이언트가 서버에 데이터를 요청)으로 서버 푸시 방식의 실시간 서비스는 만들 수 없다
- 바이너리 데이터를 보내거나 받을 수 없다
- Ajax 스크립트가 포함된 서버가 아닌 다른 서버로 Ajax 요청을 보낼 수 없다
- 클라이언트 PC로 Ajax요청을 보낼 수 없다

#### 클라이언트 풀링(Client Pooling)
- 사용자가 직접 원하는 정보를 서버에 요청하여 얻는 방식

#### 서버 푸시(Server Push)
- 사용자가 요청하지 않아도 서버가 알아서 자동으로 특정 정보를 제공
- Ex) 스마트 폰에서 각종 앱이 보내는 푸시 알림

### Ajax 구성 요소
- 웹 페이지의 표현을 위한 HTML과 CSS
- 데이터에 접근하거나 화면 구성을 동적으로 조작하기 위해 사용되는 DOM 모델
- 데이터의 교환을 위한 JSON이나 XML
- 웹 서버와의 비동기식 통신을 위한 XMLHttpRequest 객체
- 사용자의 작업 흐름을 제어하는 데 사용되는 JS

### Ajax 동작 원리
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

### 문서 객체 모델 DOM(Document Object Model)
- HTML문서나 XML문서에 접근하기 위한 인터페이스
- 문서 내의 모든 요소의 목적과 특징 정의, 각 요소에 접근하는 방법 제공
<img src="http://tcpschool.com/lectures/img_js_htmldom.png" />
ajax에서 이러한 DOM을 이용하여 웹 페이지의 일부 요소만 변경할 수 있다

### DOM 요소의 선택
JS로 DOM요소를 다루기 위해선 해당 요소를 선택해야한다
DOM 요소를 선택하는 방법
- 태그 이름(tag name)
- 아이디(id)
- 클레스(class)
- CSS 선택자(Selector)
- HTML 객체 집합 (Ojbect Collection)

### DOM 요소의 내용 변경
DOM을 이요하면 DOM 요소의 내용(content)이나 속성값 등을 쉽게 변경할 수 있다
DOM 요소의 내용을 바꾸는 가장 쉬운 방법은 innerHTML 프로퍼티를 이용하는 것이다
DOM 요소의 속성 이름을 이용하면 속성값을 바로 변경할 수 있다

### 노드(NODE)
DOM은 노드라고 불리는 계층적 단위에 정보를 저장한다
DOM은 이러한 노드들을 정의하고, 그들 사이의 관계를 설명해 주는 역할을 한다

### 노드 트리(Node Tree)
문서의 정보는 노드 트리(node Tree)라고 불리는 계층적 구조에 저장된다
노드 트리는 노드들이 집합, 노드 간의 관계를 보여준다

### 노드 간의 관계
노드 트리의 모든 노드들은 서로 계층적 관계를 가지고 있다
<img src="http://tcpschool.com/lectures/img_js_node_relationship.png">
노드 트리의 가장 상위에는 단 하나의 루트 노드(root node)가 존재한다

루트 노드를 제외한 모든 노드는 단 하나의 부모 노드(parent node)만을 가진다
모든 요소 노드는 자식 노드(child node)를 가질 수 있다

형제 노드(sibling node)란 같은 부모 노드를 가지는 노드
조상 노드(ancestor node)란 부모 노드를 포함해 계층적으로 현재 노드보다 상위에 존재하는 노드
자손 노드(descendant node)란 자식 노드를 포함해 계층적으로 현재 노드보다 하위에 존재하는 노드

### 노드로의 접근
JS로 DOM노드에 접근하는 방법
1. getElementsByTagName() 메소드
2. 노드 간의 관계를 이용

### 노드에 대한 정보
DOM 노드에 대한 정보는 다음과 같은 속성을 통해 접근
1. nodeName : 노드 고유의 이름 명시
2. nodeValue : 노드의 값 명시
3. nodeType : 노드 고유의 타입 명시

### 노드 리스트(node list)
노드 리스트는 getElementsByTagName() 메소드나 childNodes 속성의 속성값으로 반환되는 객체이다
이 객체는 HTML 문서와 같은 순서로 문서 내의 모든 노드를 리스트 형태로 저장하고 있다
<img src="http://tcpschool.com/lectures/img_js_node_list.png">

### DOM API
Ajax를 이용하여 웹 페이지의 일부만을 갱신하려면 다양한 DOM 속성을 활용해야 한다
따라서 DOM과 관련된 다양한 API를 이용하여 노드를 동적으로 생성하고, 조작할 수 있어야 한다

### 노드의 추가
1. appendChild() : 새로운 노드를 해당 노드의 자식 노드 리스트에 맨 마지막 노드로 추가
2. insertBefore() : 새로운 노드를 특정 노드 바로 앞에 추가
3. insertData() : 텍스트 노드의 텍스트 데이터에 새로운 텍스트 추가

#### appendChild() 예제
```javascript
function appendNode()
{
  var parent = document.getElementById("list"); // 아이디가 list인 요소 선택
  var newItem = document.getElementById("item"); // 아이디가 item인 요소 선택
  parent.appendChild(newItem);
}
```
### 노드의 생성
1. createElement() : 새로운 요소 노드 생성
2. createAttribute() : 새로운 속성 노드 생성
3. createTextNode() : 새로운 텍스트 노드 생성

#### createElement() 예제
```javascript
funciton createNode()
{
  var criteriaNode = document.getElementById("text"); // 기준이 되는 요소, 아이디가 text인 요소를 선택
  var newNode = document.createElement("p"); // 새로운 <p> 요소를 생성
  newNode.innerHTML = "새로운 단락입니다.";
  document.body.insertBefore(newNode, criteriaNode); // 새로운 요소를 기준이 되는 요소 바로 앞에 추가
}
```

### 노드의 제거 
1. removeChild() : 기존의 노드 리스트에서 특정 노드 제거
2. removeAttribute() : 속성의 이름을 이용하여 특정 속성 노드 제거

#### removeChild() 예제
```javascript
var parent = document.getElementsById("list") // 아이디가 list인 요소 선택
var removedItem = document.getElementById("item") // 아이디가 "item"인 요소 선택
parent.removeChild(removedItem); // 지정된 요소 삭제
```

### 노드의 복제
1. cloneNode() : 특정 노드를 복제

#### cloneNode() 예제
```javascript
function cloneElement()
{
  var parent = document.getElementsById("list"); // 아이디가 list인 요소 선택
  var originItem = document.getElementsById("item"); // 아이디가 item인 요소 선택
  parent.appendChild(originItem.cloneNode(true)); // 해당 노드를 복제하여 리스트의 맨 마지막에 추가
}
```

### 노드의 값 변경
1. nodeValue의 프로퍼티를 사용하면 특정 노드의 값을 변경할 수 있다
2. setAttribute() : 속성 노드의 속성값을 변경할 수 있다

#### nodeValue 예제
```javascript
var para = document.getElementById("text"); // 아이디가 text인 요소 선택
funciton changeText()
{
  para.firstChild.nodeValue = "텍스트 변경 완료!";
}
```

### 노드의 교체
1. replaceChild() : 특정 노드 그자체를 다른 노드로 바꿀 수 있다

#### replaceChild() 예제
```javascript
var parent = document.getElementsById("parent"); // 부모 노드 선택
var first = document.getElementsById("first");
var third = document.getElemnetsById("third");
function changeNode()
{
  parent.replaceChild(third, first); // first 요소를 삭제하고, 그 대신 third 요소를 삽입
}
```

## XMLHttpRequest 객체
### XMLHttpRequest 객체
- Ajax의 가장 핵심적인 구성 요소는 XMLHttpRequest객체이다
- XMLHttpRequest객체는 웹 브라우저가 서버와 데이터를 교환할 때 사용된다

### XMLHttpRequest 객체의 생성
- 대부분의 주요 웹 브라우저는 XMLHttpRequest 객체를 내장하고 있다
- 객체를 생성하는 방법은 브라우저의 종류에 따라 나뉜다

1. XMLHttpRequest 
  - IE7 이상의 버전, chrome, firefox, safari, opera에서 사용가능
  ```javascript
    var 변수이름 = new XMLHttpRequest();
  ```
2. ActiveXObject
  - IE5, 6버전에서 사용
  ```javascript
    var 변수이름 = new ActiveXObject("Microsoft.XMLHTTP");
  ```
3. 모든 버전에서 XMLHttpRequest 인스턴스 생성 예제
  ```javascript
  var httpRequest;
  function createRequest()
  {
    if(window.XMLHttpRequest)
    {
       return new XMLHttpRequest();
    }
    else
    {
      return new ActiveXObject("Microsoft.XMLHTTP");
    }
  }
  ```
4. IE7 이상 인스턴스 생성 예제
  ```javascript
    var httpRequest = new XMLHttpRequest();
  ```
  
## 서버에 요청하기
### 서버에 요청(request)하기
- 서버에 요청을 보내기 위해 XMLHttpRequest 객체 생성
- XMLHttpRequest 인스턴스의 open() 메소드와 send() 메소드를 사용하여 요청

### open() 메소드
- 서버로 보낼 Ajax 형식 설정
```javascript
open(전달방식, URL주소, 동기여부);
```
- 전달 방식 : GET 방식과 POST 방식 중 선택
- URL 주소 : 요청을 처리할 서버의 파일 주소
- 동기 여부 : 요청을 동기식으로 전달할지 비동기식으로 전달할지 전달

### send() 메소드
- 작성된 Ajax 요청을 서버로 전달
- 전달 방식에 따라 인수를 안 가질 수도 있다
```javascript
send(); // GET방식
send(문자열); // POST 방식
```
#### GET 방식과 POST 방식
GET
- 주소에 데이터를 추가하여 전달
- HTTP요청이 브라우저에 의해 캐시되어 저장
- 쿼리 문자열에 포함되어 전송, 길이의 제한이 있다
- 보안상 취약, 중요한 데이터는 POST 방식 이용

POST
- 데이터를 별도로 첨부하여 전달
- HTTP요청이 브라우저에 캐시되지 않음, 브라우저 히스토리에도 남지 않음
- 쿼리 문자열과는 별도로 전송
- 데이터의 길이에 제한이 없고 GET 방식보다 보안성이 높다

#### GET 방식으로 요청예제
- 서버로 전송하고자 하는 데이터는 URI에 포함되어 전송된다
```javascript
httpRequest.open("GET", "/example/request_ajax.php?city=seoul&zipcode=111", true)
httpRequest.send();
```

#### POST 방식으로 요청예제
- 서버로 전송하는 데이터는 HTTP 헤더에 포함되어 전송
- setRequestHeader() 메소드를 이용하여 헤더를 작성한 후, send() 메소드로 데이터 전송
```javascript
httpRequest.open("POST", "/example/request_ajax.php", true)
httpRequest.setRequestHeader("Content-Type", "application/x-www-form-urlencoded");
httpRequest.send("city=seoul&zipcode=111");
```

#### XMLHttpRequest 객체의 현재 상태와 서버 상의 문서 존재 유무 확인
```javascript
if(httpRequest.readyState == XMLHttpRequest.DONE && httpRequest.status == 200) {}
```
- XMLHttpRequest.DONE : 서버에 요청한 데이터의 처리가 완료, 응답 준비 완료
- status == 200 : 요청한 문서가 서버 상에 존재

### 비동기식(asynchronous) 요청
- 서버에 비동기식 요청 : open() 메소드의 세 번째 인수로 true를 전달한다
- 서버로 비동기식 요청을 보내면, JS는 서버로부터의 응답을 기다리면서 동시에 다른 일을 할 수 있다

- 서버에 동기식 요청 : open() 메소드의 세 번째 인수로 false를 전달한다
- JS는 서버로부터 응답이 도착할 때까지 대기한다
- 사용자는 대기하는 동안 다른 작업을 할 수 없게 된다

## 서버로부터의 응답
### 서버로부터의 응답(response) 확인
