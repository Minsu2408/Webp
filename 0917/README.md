# 3장요약

## 학습 목표
- HTML5 문서 구조화와 시맨틱 태그 이해  
- 시맨틱 태그로 구조화된 웹 페이지 작성  
- 웹 폼의 목적 이해 및 활용  

---

## 1. HTML5 문서 구조화
- 기존 한계: `<div>`, `<table>` 등으로 구조 표현 → 의미 전달 어려움  
- 필요성: 검색 엔진 최적화, IoT 시대 정보 검색, 사용자 탐색 편의  
- 시맨틱 웹: 의미 중심 구조화 → 정보 검색·분석 용이  

### 주요 시맨틱 태그
- `<header>` : 머리말(제목, 소개)  
- `<nav>` : 내비게이션(목차, 링크)  
- `<section>` : 장/절 구분  
- `<article>` : 독립 콘텐츠(기사, 블로그 글 등)  
- `<aside>` : 보조 정보(참고, 노트)  
- `<footer>` : 꼬리말(저작권, 작성자)  

---

## 2. 확장 시맨틱 태그
- **블록 태그**  
  - `<figure>` : 그림, 코드, 삽화  
  - `<details>` + `<summary>` : 접기/펼치기 정보  
- **인라인 태그**  
  - `<mark>` : 강조 텍스트  
  - `<time>` : 시간  
  - `<meter>` : 수치 데이터  
  - `<progress>` : 진행률  

**제거된 태그**: `<font>`, `<center>`, `<big>`, `<frame>`, `<applet>` 등  

---

## 3. 웹 폼(Form)
- 목적: 사용자 입력 수집 (로그인, 검색, 예약, 쇼핑 등)  
- `<form>` 주요 속성  
  - `action` : 데이터 처리 서버  
  - `method` : 전송 방식 (`GET`, `POST`)  
  - `name` : 폼 이름  

---

## 4. 폼 요소

### 입력 요소
- 텍스트: `<input type="text">`, `<input type="password">`, `<textarea>`  
- 자동완성: `<datalist>`  
- 버튼: `<input type="button|submit|reset|image">`, `<button>`  

### 선택 요소
- 체크박스: `<input type="checkbox">`  
- 라디오버튼: `<input type="radio" name="...">` (같은 name 그룹화)  
- 콤보박스: `<select><option>`  

### 캡션
- `<label>` : 폼 요소와 설명 연결  

### 특수 입력
- 색상: `<input type="color">`  
- 날짜/시간: `<input type="date|time|month|week|datetime-local">`  
- 숫자: `<input type="number">`, `<input type="range">`  
- 형식 검증: `<input type="email|url|tel|search">`  

### 그룹화
- `<fieldset>` : 입력 요소 그룹  
- `<legend>` : 그룹 이름  

---

## 5. 예제 모음
- 시맨틱 태그로 작성된 웹 페이지 (엘비스, 모차르트)  
- 로그인 폼  
- 체크박스, 라디오 버튼, 콤보박스  
- 색상 선택, 날짜·시간 입력  
- 회원가입 폼 (그룹 박스 활용)  
