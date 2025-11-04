# 8장

## 강의 목표

1. HTML DOM의 필요성을 이해한다.  
2. DOM 트리와 HTML 페이지의 관계를 이해한다.  
3. DOM 객체의 구조와 HTML 태그와의 관계를 이해한다.  
4. DOM 객체를 통해 HTML 태그의 출력 모양과 콘텐츠를 제어할 수 있다.  
5. `document` 객체를 이해하고, `write()` 메소드를 활용할 수 있다.  
6. `createElement()` 등을 통해 동적으로 DOM 객체를 웹 페이지에 추가, 삭제할 수 있다.  

---

## HTML 페이지와 자바스크립트 객체

자바스크립트 코드는 브라우저로부터 3가지 유형의 객체를 제공받아 활용할 수 있다.

```html
<html>
<head>
<script>
let sum = 0;
for(let n=0; n<10; n++)
  sum += n;
alert("합은 = " + sum);
</script>
<body>
…
</html>
```

- **BOM 객체**: `window`, `history`, `navigator`, `screen`, `location` 등  
- **HTML DOM 객체**: `document`, `body`, `p`, `form`, `span`, `input`, `hr` 등  
- **코어 객체**: `Array`, `Date`, 등  

---

## HTML DOM (Document Object Model)

- 웹 페이지의 각 HTML 태그마다 DOM 객체 생성
- DOM 객체를 통해 태그의 **모양**(CSS)과 **콘텐츠**를 제어 가능
- HTML 태그의 포함관계에 따라 **DOM 트리(tree)** 형성  
- DOM 트리는 **부모-자식 관계**를 가짐
- 각 HTML 태그당 하나의 DOM 객체 생성 → 이를 **DOM 노드(node)** 또는 **DOM 엘리먼트(element)** 라고 함

---

## DOM 트리의 특징

- 루트는 `document` 객체  
- DOM 객체의 종류는 HTML 태그 종류만큼  
- HTML 태그당 DOM 객체 하나 생성  
- HTML 태그의 포함 관계에 따라 부모-자식 관계 형성  

브라우저의 HTML 렌더링 과정:

1. `document` 객체 생성  
2. HTML 태그를 읽어 DOM 트리에 객체 생성  
3. DOM 객체를 화면에 출력  
4. HTML 문서 로딩 완료 → DOM 트리 완성  
5. DOM 객체 변경 시, 브라우저는 해당 태그의 화면을 즉시 갱신  

---

## HTML 태그의 요소

HTML 태그(엘리먼트)는 다음 5가지로 구성된다:

1. 엘리먼트 이름  
2. 속성(attribute)  
3. CSS3 스타일  
4. 이벤트 리스너  
5. 콘텐츠(innerHTML)  

---

## DOM 객체의 구성 요소

- **프로퍼티(property)**: HTML 속성을 반영  
- **메소드(method)**: 태그 제어 함수  
- **컬렉션(collection)**: 자식 DOM 객체들의 집합  
- **이벤트 리스너(event listener)**: 이벤트 처리  
- **CSS3 스타일**: 스타일 정보 (`style` 프로퍼티로 접근)

---

### 예제 8-1 DOM 객체의 구조 출력 (p 객체 사례)

```html
<p id="firstP" style="color:blue; background:yellow" 
   onclick="this.style.color='teal'">
이것은 <span style="color:red">문장입니다.</span>
</p>

<script>
let p = document.getElementById("firstP");
let text = "p.id = " + p.id + "\n";
text += "p.tagName = " + p.tagName + "\n";
text += "p.innerHTML = " + p.innerHTML + "\n";
text += "p.style.color = " + p.style.color + "\n";
text += "p.onclick = " + p.onclick + "\n";
text += "p.childElementCount = " + p.childElementCount + "\n";
text += "너비 = " + p.offsetWidth + "\n";
text += "높이 = " + p.offsetHeight + "\n";
alert(text);
</script>
```

---

## DOM 객체 다루기

### 1️⃣ 객체 찾기

```js
let p = document.getElementById("firstP");
```

### 2️⃣ CSS 스타일 변경

```js
p.style.color = "red";
span.style.fontSize = "30px";
span.style.border = "3px dotted magenta";
```

---

### 예제 8-2 `<span>`의 CSS3 스타일 동적 변경

```html
<input type="button" value="스타일변경" onclick="change()">
```

버튼 클릭 시 `change()` 함수가 호출되어 스타일 변경.  
인라인 박스가 블록 박스로 변함.

---

## innerHTML 프로퍼티

`innerHTML`은 태그 내부의 HTML 콘텐츠를 의미하며, 수정하면 콘텐츠가 즉시 변경된다.

```js
p.innerHTML = "나의 <img src='puppy.png'> 강아지";
```

---

### 예제 8-3 innerHTML 활용

마우스를 클릭하면 텍스트가 이미지로 변경됨.

---

## this 키워드

- 객체 자신을 가리킴  
- DOM에서 자기 자신을 조작할 때 사용  

```html
<button onclick="this.style.backgroundColor='orange'">버튼</button>
```

---

### 예제 8-4 this 활용

```html
<button onclick="change(this, '30px', 'red')">버튼</button>
<div onclick="change(this, '25px', 'orange')">여기 클릭하면 색 변경</div>
```

---

## document 객체

HTML 문서 전체를 나타내는 객체  
- **프로퍼티**: 문서의 전반 속성  
- **메소드**: DOM 검색, 생성, 제어  
- DOM 트리의 최상위 루트  

접근 방식: `window.document` 또는 `document`

> `document` 자체는 DOM 객체가 아니며 CSS 스타일을 가질 수 없다.

---

### 예제 8-5 document 객체의 주요 프로퍼티

출력 항목:
- `location`, `URL`, `title`, `head.id`, `body.style.color`, `domain`, `lastModified`, `readyState`, `referrer`, `activeElement` 등  

---

## DOM 트리에서 객체 찾기

- **태그 이름으로 찾기**: `document.getElementsByTagName()`
- **class 속성으로 찾기**: `document.getElementsByClassName()`

---

### 예제 8-6 getElementsByTagName()

모든 `<span>` 태그의 색과 크기를 변경.

---

### 예제 8-7 getElementsByClassName()

`class="place"`와 `class="food"`를 가진 태그의 스타일을 각각 변경.

---

## document.write() / writeln()

HTML 페이지 로딩 중에 `document.write()`를 사용하면  
새 HTML 태그를 DOM 트리에 추가하여 즉시 렌더링함.  

- `write()` : 문자열 그대로 추가  
- `writeln()` : 문자열 끝에 `\n` 추가  

⚠️ **주의:** 로드 후 `document.write()` 사용 시 기존 페이지가 지워짐.

---

### 예제 8-8 write()와 writeln() 활용

```js
document.write("<h3>동물원에 소풍갑시다</h3>");
document.writeln("5명입니다.<br>");
```

---

### 예제 8-9 write() 잘못 사용한 예

클릭 시 기존 페이지가 삭제되고 새로운 내용이 출력됨.

---

## document.open() / close()

- `document.open()`: 현재 문서 내용 지우고 새 HTML 페이지 시작  
- `document.close()`: 새 문서 작성 완료  

새 창(`window.open()`)에서도 사용 가능.

---

### 예제 8-10 HTML 문서 작성기 만들기

`<textarea>`에 HTML 코드를 작성하고 버튼 클릭 시 새 창에 표시.

---

## 문서의 동적 구성

DOM 객체를 동적으로 생성, 추가, 삭제 가능  

### 생성
```js
let newDIV = document.createElement("div");
newDIV.innerHTML = "새로 생성된 DIV입니다.";
```

### 추가
```js
p.appendChild(newDIV);
```

### 삭제
```js
parent.removeChild(myDiv);
```

---

### 예제 8-11 HTML 태그의 동적 추가 및 삭제

링크 클릭 시 `<div>` 생성 → 생성된 박스를 클릭하면 삭제됨.  


9장 수업내용 요약
HTML과 DOM
HTML 문서 구조 이해 (<!DOCTYPE html>, <html>, <head>, <body> 등)

DOM(Document Object Model) : HTML 요소를 자바스크립트로 조작 가능하게 만든 구조

주요 이벤트: onclick, onmouseover, onmouseout, onkeydown 등

xml
<p id="example" onmouseover="this.style.backgroundColor='orchid'" onmouseout="this.style.backgroundColor='white'">예제 문장</p>
이벤트 처리
이벤트 리스너 등록 : addEventListener 이용

이벤트 객체(event)의 활용 방법

이벤트 버블링, 캡처링 개념 및 차이점

javascript
element.addEventListener('click', function(e) {
  e.preventDefault(); // 기본 이벤트 방지
  alert('클릭됨');
});
##폼과 입력 요소

다양한 입력 요소: input, checkbox, radio, select

폼 이벤트: submit, reset, 입력값 유효성 검사

이미지 및 스타일 제어
이미지 변경 및 스타일 변화 예제

onload, onerror 이벤트 활용

자바스크립트 함수와 변수
함수 선언과 이벤트 핸들러 연결 방법

변수 사용과 스코프 이해

