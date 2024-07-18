# HTML CSS JAVASCRIPT

# HTML

웹서버와 웹브라우저 사이에 문서를 전송하기 위해 사용되는 통신 규약이름 : HTTP

HTTP 프로토콜의 포트번호 : 80

> 웹요소의 각 역할
> 
- HTML - 화면 구조 정의
- CSS - 화면 꾸미기
- Javascript - 화면에 동적인 기능을 제공

> 주요태그
> 

시작태그 : `<html>`

제목태그 : `<h1> <h2> <h3> <h4> <h5> <h6>`  `<h1>`글자가 가장 크고 `<h6>`글자가 가장 작다

이미지 태그 :  `<img src="a.jpg" alt="대체글자">`

링크태그 : `<a href="URL" target="_blank" >`글자`</a> target="_blank"` 새창 띄우기

데이터 입력및 전송: `<form action="url" method="GET">`

전송방식 : method="GET" 또는 "POST"

| GET 방식  | POST 방식 |
| --- | --- |
| 헤더에 데이터를 보내기때문에 데이터가 보임 | 본문으로 보내기 때문에 데이터가 보이지 않음 |
| 전송데이터의 길이제한(4K) | 전달 길이 무제한 |
| 주소에 데이터를 추가하여 서버에 전달하는 방식이며 중요도가 낮은 데이터를 전달할 때 주로 사용 | 데이터를 별도로 첨부(파일 업로드, 첨부파일)하여 전달하는 방식이며 보안성 및 활용성이 GET 방식보다 뛰어나다. |

`<input type="text"> type=text/radio/checkbox/date/submit/reset/…` 입력모양을 결정함

`<select>`

`<textarea>`

테이블태그  `<table><thead> <tbody> <tr>  <th><td>`

`<div>` 블록타입: 앞뒤의 줄바꿈

`<span>` 인라인타입: 앞뒤 같은줄에 그려짐

---

# CSS

### 선택자

id 선택자: #아이디명

- #mid <div id="mid">

class 선택자: .class명

- .mc <div class="mc">

태그 선택자: 태그명

- div <div>

자식 선택자: 부모선택자 > 자식선택자

자손 선택자: 부모선택자 자손선택자

글자색 지정  div { **color**: blue; }

배경색 지정  div { **background-color:** red; }

테두리 지정 div {border: 3px **solid** red;}

크기지정 div{ **width**: 100px; **height**: 100px; }

위치지정 div {**position**: **absolute**; left: 10px; top: 10px; }

위치지정 div {**position**: **relative**; left: 10px; top: 10px; }

float 속성: 요소를 가로배치

플로팅 .left { float:left; }

플로팅 .right { float:right; }

clear 속성: float된 요소와 아닌 요소간 영역 겹침을 해소하기 위한 속성 

플로팅해제 .bottom{ clear: both; }

---

# Javascript

### 호이스팅
```jsx
a = 100
var a = 100
let a = 100 → 에러
```

```jsx
var age;
console.log(age) // undefined
```

```jsx
let age;
console.log(age) // undefined
```

```jsx
console.log(age) 
// js03_hoisting.html:8 Uncaught ReferenceError: age is not defined
//    at js03_hoisting.html:8:21
```

```jsx
console.log(age) // undefined 
var age = 30; 
```

```jsx
console.log(age)
let age = 30; 
// js03_hoisting.html:8 Uncaught ReferenceError: age is not defined
//    at js03_hoisting.html:8:21
```

### 구문

if, for, continue, break

### 팝업창

메시지 팝업창 alert("메시지")

입력 팝업창 let ans = prompt("이름은?","")

### 태그선택

| 요소 접근 메서드 | 방식 | 설명 |
| --- | --- | --- |
| getElmentById() | 단수형 | id 속성값으로 특정값을 갖는 요소 반환 |
| getElementsByTagName() | 복수형 | 특정 태그(tag)을 갖는 모든 요소 반환 |
| getElementsByClassName() | 복수형 | class 속성값으로 특정값을 갖는 모든 요소 반환 |
| getElementsByName() | 복수형 | name 속성값으로 특정값을 갖는 모든 요소 반환 |
| querySelector() | 단수형 | 특정 CSS 선택자 형식과 일치하는 첫번째 요소 반환 |
| querySelectorAll() | 복수형 | 특정 CSS 선택자 형식과 일치하는 모든 요소 반환 |

```jsx
let mid = document.getElementById("id")
let tags = document.getElementsByTagName("tag")
let cls = document.getElementsByClassName("cls")
let a = document.querySelector("#mid") 
```

### BOM

- 브라우저내 기본으로 제공하는 객체
- browser: 웹브라우저 자체정보제공
- window: 내장객체의 최상위에 있어 브라우저창에 관한 속성과 메서드를 제공한다.
- document: html 문서정보를 가지고 있는객체
- location: 브라우저의 현재 URL정보를 가지는 객체

### 일반적인 요소의 내용접근

document.getElementById("id").innerText 의 값을 읽거나 씀. html태그의 기능이 발휘안됨

document.getElementById("id").innerHTML 의 값을 읽거나 씀. html태그의 기능이 발휘됨

```jsx
document.querySelector("#result").innerText = "Hello" // 값 입력기능 없음. 출력전용
document. querySelector ("#result") .innerHTML = "<b>HELLO</b>" // 값 입력기능. 입력전용
```

`<input><select><textarea>`의 입력값접근

document.getElementById("id").value  입력된 값을 읽거나 쓰기 위해 사용

```jsx
document.querySelector(”#mid”).value // input 값 출력전용
document.querySelector(”#mid”).value = “user01” // input 값 입력전용
```

### 이벤트

이벤트 처리속성 : on이벤트이름

인라인 이벤트 등록 `<h1 onclick="스크립트코드">`

> 이벤트 핸들러 click 처리
> 

**이벤트 핸들러, 리스너**

```jsx
  // 이벤트 대상 + 이벤트 트리거 + 이벤트 핸들러 
  // 단순형태에서 주로 사용
  // 덮어쓰기 기능
  document.querySelector('.btn-danger').onclick = function() {
    console.log('이벤트 핸들러#1');
  }

  document.querySelector('.btn-danger').onclick = function() {
    console.log('이벤트 핸들러#2');
  }

  // 이벤트 대상 + 이벤트 트리거 + 이벤트 리스너
  // 복잡한형태에서 주로 사용 
  // 따로 기능 작동 
  document.querySelector('.btn-warning').addEventListener('click', function() {
    console.log('이벤트 리스너#1');
  });

  document.querySelector('.btn-warning').addEventListener('click', function() {
    console.log('이벤트 리스너#2');
  });

// 출력결과  
이벤트 핸들러#2
이벤트 리스너#1
이벤트 리스너#2
```

### 이벤트 기본동작 취소 3가지

1. `<form onsubmit="return false">`  전송 안됨
2. `<a href="url" onclick="return false">` url을 로딩못함. 웹페이지가 안바뀜
3. 이벤트처리코드가 return false하면 해당태그의 고유동작이 취소됨

```jsx
1. 
<a onclick="alert(100); return false;" href="[http://www.naver.com](http://www.naver.com/)">네이버</a>

2. 가장 많이 쓰는 방법 
<a onclick="check(evt);" href="[http://www.naver.com](http://www.naver.com/)">네이버</a>
<script> 
	function check(evt) { 
		evt.preventDefault(); //동작중지
	}
</scirpt>

3.
<a onclick="return check()" href="http://naver.com">네이버</a>
<script>
  function check(){
    return false ; //동작중지
  }
</sciprt>
```

### AJAX

클라이언트와 서버 간 **자바스크립트 및 XML**을 **비동기 방식**으로 처리하며 **전체 페이지를 새로 고치지 않고도 웹페이지 일부 영역만을 업데이트**할 수 있도록 하는 기술

장점: 유지보수가 쉽다 / 단점: 느림 

특징

- 효율적인 빠른처리를 위해서 xml 데이터 사용
- SOP 같은 서버에서만 자원을 가져올 수 있다.
- CORS 다른 서버와의 자원공유 금지
- 프록시 서버로 대신 해줌 (jsp 생성)

```jsx
let xhr =  new XMLHttpRequest()
xhr.open("GET","url")
xhr.send()
xhr.onreadystatechange = function(data){
if(this.status == 200 && this.readyState == 4) {
alert(this.responseText)
}
```

### Websoket

웹서버와 실시간 통신 지원
