# 2장 요약: HTML 기초

## 강의 목표

* HTML 태그 기초 학습
* HTML5 기본 문서 구조 이해
* 이미지, 표, 하이퍼링크 삽입
* 인라인 프레임(iframe) 활용
* 오디오, 비디오 삽입

---

## 1. HTML5 기본 구조

```html
<!DOCTYPE html>
<html>
<head>
    문서제목, 스크립트, CSS, 메타데이터 정의
</head>
<body>
    본문 내용 (텍스트, 이미지, 테이블, 동영상 등)
</body>
</html>
```

### 태그 특징

* 대부분 시작/종료 태그 필요 (`<html>...</html>`)
* 단일 태그: `<br>`, `<hr>`
* 대소문자 구분 없음
* 속성 값의 공백은 표준 위반

---

## 2. 텍스트 관련 태그

* 제목: `<h1>` \~ `<h6>`
* 단락: `<p>`
* 수평선: `<hr>`
* 줄바꿈: `<br>`
* 특수문자: `&lt;`, `&copy;`, `&sum;`
* 서식: `<b>`, `<strong>`, `<em>`, `<i>`, `<mark>`, `<sup>`, `<sub>`
* 원본 서식 유지: `<pre>`

---

## 3. 블록 vs 인라인 태그

* **블록 태그**: `<p>`, `<div>`, `<ul>` → 한 줄 전체 차지
* **인라인 태그**: `<span>`, `<a>`, `<img>` → 블록 내부 일부

---

## 4. 메타데이터

* `<base>`: 기본 URL 설정
* `<link>`: 외부 리소스 연결 (예: CSS)
* `<meta>`: 저작자, 설명, 키워드, 문자셋 지정

---

## 5. 이미지 삽입

```html
<img src="media/Elvis1.jpg" width="150" height="200" alt="Elvis">
```

* 지원 포맷: BMP, GIF, PNG, JPG, animated-GIF
* `alt`: 이미지 없을 때 대체 텍스트

---

## 6. 리스트

* 순서 있는 리스트: `<ol>`
* 순서 없는 리스트: `<ul>`
* 정의 리스트: `<dl>`, `<dt>`, `<dd>`

---

## 7. 표 (Table)

* `<table>`, `<caption>`, `<thead>`, `<tfoot>`, `<tbody>`
* 행: `<tr>` / 제목 셀: `<th>` / 데이터 셀: `<td>`

---

## 8. 하이퍼링크

* 기본 링크: `<a href="url">텍스트</a>`
* 이미지 링크 가능
* 색상: 링크(파랑), 방문 후(보라), 클릭 중(빨강)
* `target` 속성: `_blank`, `_self`, `_parent`, `_top`, 프레임 이름
* 앵커: `<a id="chap1">`, `href="#chap1"`
* 파일 다운로드: `<a href="file" download>`

---

## 9. 인라인 프레임 (iframe)

* 다른 HTML 문서 내장: `<iframe src="url" width height></iframe>`
* `srcdoc`: 태그 내에 직접 HTML 작성 가능
* 윈도우 관계: parent, child, top

---

## 10. 미디어 삽입

* **비디오**: `<video src="video.mp4" width height controls></video>`
* **오디오**: `<audio src="music.mp3" controls loop></audio>`
* 브라우저 보안상 autoplay 제한 → 사용자 클릭 필요

---

## 핵심 정리

* HTML5는 웹 문서의 구조를 정의하는 표준 언어.
* 시맨틱 태그, 멀티미디어 태그를 활용해 풍부한 콘텐츠 제작 가능.
* CSS와 함께 사용하면 스타일링 및 레이아웃 제어 가능.
