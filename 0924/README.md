# 📘 4장.

## 🎯 학습 목표

1. CSS3 언어의 개념 이해
2. CSS3 스타일 시트 작성 방법 학습
3. CSS3 셀렉터(selector) 작성법 학습
4. 텍스트 꾸미기
5. 색상과 모양 꾸미기
6. 박스 모델(Box Model) 이해 및 활용
7. 배경과 테두리 꾸미기
8. 그림자 효과 만들기

---

## 1. CSS3 개요

* **CSS(Cascading Style Sheet)** : HTML 문서의 색상, 모양 등 외관을 꾸미는 언어
* CSS 발전: CSS1 → CSS2 → **CSS3** → CSS4(표준화 진행 중)
* 주요 기능:

  * 색상과 배경
  * 텍스트/폰트 제어
  * 박스 모델
  * 시각적 효과
  * 리스트, 테이블, UI 제어

---

## 2. CSS3 스타일 시트 작성 방법

1. `<style>` 태그 내부 작성 (문서 전체 적용)
2. `style` 속성 사용 (해당 태그에만 적용)
3. 외부 `.css` 파일 작성 후 불러오기

   * `<link>` 태그 사용
   * `@import` 구문 사용

---

## 3. CSS3 규칙

* **상속**: 자식 태그는 부모의 스타일 일부를 상속받음
* **합치기(Cascading) & 오버라이딩(Overriding)**

  * 여러 스타일이 적용될 경우 **우선순위** 존재
  * 우선순위: 브라우저 기본 < 외부 CSS < `<style>` 태그 < `style` 속성

---

## 4. 셀렉터(Selector)

* **태그 셀렉터** : 태그 이름 사용
* **class 셀렉터 (`.class`)** : 여러 태그를 그룹화
* **id 셀렉터 (`#id`)** : 특정 태그에만 적용 (고유 ID 필요)
* **자식 셀렉터 (`>`)** : 직계 자식 선택
* **자손 셀렉터 (공백)** : 모든 하위 요소 선택
* **전체 셀렉터 (`*`)** : 모든 태그에 적용
* **속성 셀렉터** : 특정 속성을 가진 태그 선택 (`input[type=text]`)
* **가상 클래스(pseudo-class)**

  * `:hover` → 마우스 올렸을 때
  * `:visited` → 방문한 링크
  * `:first-letter` → 첫 글자 등

---

## 5. 색상 표현

* 3가지 방법

  * **16진수 코드**: `#8A2BE2`
  * **RGB**: `rgb(138, 43, 226)`
  * **색 이름**: `blueviolet`
* **관련 프로퍼티**

  * `color` : 글자색
  * `background-color` : 배경색
  * `border-color` : 테두리 색

---

## 6. 텍스트 꾸미기

* `text-align` : 정렬 (left, center, right, justify)
* `text-indent` : 들여쓰기
* `text-decoration` : 밑줄, 취소선, 윗줄
* **폰트 관련 프로퍼티**

  * `font-family` : 폰트 지정
  * `font-size` : 크기(px, em, %, medium 등)
  * `font-style` : italic, oblique
  * `font-weight` : bold, 100~900

---

## 7. 박스 모델(Box Model)

* 구성 요소:

  1. **Content** : 실제 내용
  2. **Padding** : 내용과 테두리 사이 여백
  3. **Border** : 테두리
  4. **Margin** : 박스와 박스 사이 간격
* 관련 속성:

  * `width`, `height`
  * `margin`, `padding`
  * `border` (굵기, 색상, 스타일 지정)
  * `border-radius` : 둥근 모서리
  * `border-image` : 이미지 테두리

---

## 8. 배경 꾸미기

* `background-color` : 배경 색
* `background-image` : 배경 이미지
* `background-position` : 배경 위치
* `background-repeat` : 반복 여부 (repeat, repeat-x, repeat-y, no-repeat)
* `background-size` : 크기 지정
* `background` (단축 프로퍼티)

---

## 9. 그림자 효과

* **텍스트 그림자** : `text-shadow`

  * 예: `text-shadow: 3px 3px 5px red;`
* **박스 그림자** : `box-shadow`

  * 예: `box-shadow: 10px 10px 5px gray;`

---

## 10. 마우스 커서 제어

* `cursor` 속성으로 커서 모양 변경
* 예:

  * `cursor: pointer;` (손가락 모양)
  * `cursor: crosshair;` (십자)
  * `cursor: help;` (도움말)

