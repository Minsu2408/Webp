
# 📘 5장.

## 🎯 학습 목표

1. HTML 태그의 출력 위치 조절
2. 리스트 꾸미기
3. 표 꾸미기
4. 폼(form) 꾸미기 및 입력 반응 처리
5. 애니메이션, 전환(transition), 변환(transform) 효과

---

## 1. 배치 (Layout)

* **배치 관련 주요 속성**

  * `display`
  * `position` (`static`, `relative`, `absolute`, `fixed`)
  * `left`, `right`, `top`, `bottom`
  * `float`
  * `z-index`
  * `visibility`
  * `overflow`

### 1-1. Display

* `block`: 줄 전체 차지
* `inline`: 한 줄 안에 배치
* `inline-block`: inline처럼 배치되지만 block 속성(width/height) 가짐
* `none`: 요소를 숨김 (자리도 차지 X)

### 1-2. Position

* **static**: 기본 배치
* **relative**: 원래 위치 기준으로 이동
* **absolute**: 부모 기준 좌표에 절대 위치
* **fixed**: 브라우저 창 기준 고정

### 1-3. Float

* `float: left/right` : 요소를 좌/우측에 배치

### 1-4. z-index

* 겹치는 요소의 앞뒤 순서 제어

### 1-5. visibility

* `visible`: 보임
* `hidden`: 안 보이지만 공간 차지

### 1-6. overflow

* `visible`: 넘치는 내용 표시
* `hidden`: 넘친 부분 잘림
* `scroll`: 스크롤바 생성

---

## 2. 리스트 꾸미기

* `list-style-position`: 마커 위치 지정 (inside, outside)
* `list-style-type`: 마커 종류 (circle, square, decimal, upper-roman 등)
* `list-style-image`: 마커를 이미지로 변경
* 네비게이션 메뉴로 응용 가능 (`<ul><li>` 조합)

---

## 3. 표(Table) 꾸미기

* **기본 속성**

  * `border`, `border-collapse`
  * `width`, `height`
  * `padding`, `text-align`

* **시각 효과**

  * `thead`, `tfoot`에 배경색 적용
  * `nth-child(even)` : 짝수 행 스타일링 (줄무늬 효과)
  * `tr:hover` : 마우스 올리면 색상 변경

---

## 4. 폼(Form) 꾸미기

* **기본**

  * `input[type=text] { color: red; }`
  * `border`, `border-radius`로 모양 지정

* **동적 스타일**

  * `:hover` : 마우스 올렸을 때
  * `:focus` : 입력창 포커스 시 효과

---

## 5. CSS3 동적 변화

### 5-1. 애니메이션 (animation)

* 작성 방법:

  1. `@keyframes`로 시간에 따른 변화 정의
  2. `animation-name`, `animation-duration`, `animation-iteration-count` 지정
* 예: 글자 색이 blue → green → red로 변하는 애니메이션

### 5-2. 전환 (transition)

* CSS 속성 변화가 **서서히 진행**되도록 설정
* `transition: 속성 시간`
* 예: `span:hover { font-size: 500%; }`

### 5-3. 변환 (transform)

* **2D 변환 함수**

  * `rotate(deg)` : 회전
  * `skew(x, y)` : 기울이기
  * `translate(x, y)` : 이동
  * `scale(x, y)` : 확대/축소

---

## ✅ 요약

* **배치**: display, position, float, z-index, overflow로 요소 위치 제어
* **리스트/표/폼**: 시각적으로 꾸미고, hover/focus로 동적 반응 추가
* **시각 효과**: 애니메이션, 전환, 변환을 통해 생동감 있는 웹 UI 구현
