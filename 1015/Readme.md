# 📘 7장. 자바스크립트 객체

## 🎯 학습 목표
1. 객체의 기본 개념 이해  
2. 코어 객체의 종류와 활용  
3. `Date` 객체 사용  
4. `String` 객체 사용  
5. 배열 생성 및 `Array` 객체 활용  
6. `Math` 객체 활용  

---

## 🧱 1. 객체(Object) 개념
- 현실 세계의 모든 것은 **객체들의 집합**
- 예:  
  - 자동차 → `{색상:오렌지, 배기량:3000CC, 제조사:한성}`  
  - 사람 → `{이름:이재문, 나이:20, 성별:남}`

### 자바스크립트 객체
```javascript
let account = {
  owner: "황기태",
  code: "111",
  balance: 35000,
  deposit: function() {},
  withdraw: function() {},
  inquiry: function() {}
};
```
- **프로퍼티**: 객체의 속성 (변수)  
- **메소드**: 객체 안의 함수  

---

## 🧰 2. 객체의 종류
| 유형 | 설명 | 예 |
|------|------|----|
| 코어 객체 | 어디서나 사용 가능한 기본 객체 | Array, Date, String, Math |
| HTML DOM 객체 | HTML 태그를 객체로 표현 | 문서 제어 |
| 브라우저 객체(BOM) | 브라우저 제어용 | window, location 등 |

---

## ⏰ 3. Date 객체
- 시간 정보를 담는 객체
- 생성 방법
```javascript
let now = new Date();
let startDay = new Date(2017, 2, 1);
```
- 주요 메소드
  - `getFullYear()`, `getMonth()`, `getDate()`, `getHours()`, `getMinutes()`, `getSeconds()`
- 예제: 방문 초가 짝수면 violet, 홀수면 lightskyblue 배경
```javascript
let current = new Date();
if(current.getSeconds() % 2 == 0)
    document.body.style.backgroundColor = "violet";
else
    document.body.style.backgroundColor = "lightskyblue";
```

---

## 🧵 4. 배열과 Array 객체
### 배열 생성 방법
```javascript
let cities = ["Seoul", "New York", "Paris"];
let week = new Array("월", "화", "수");
let empty = new Array(); // 빈 배열
```
- 인덱스는 0부터 시작
- 배열의 크기는 **자동으로 늘어나거나 줄어듦**

### `length` 프로퍼티
- 배열의 크기를 나타냄
- 값 변경 시 배열 크기 조절 가능

---

## 🧮 5. String 객체
- 문자열 저장용 객체
- 문자열 길이: `length` (읽기 전용)
- 배열처럼 `[]`로 문자 접근 가능

```javascript
let hello = new String("Hello");
let c = hello[0]; // 'H'
```

### 주요 메소드
| 메소드 | 설명 |
|--------|------|
| `charAt(i)` | i번째 문자 반환 |
| `concat()` | 문자열 연결 |
| `indexOf()` | 문자열 검색 |
| `slice()` / `substr()` | 부분 문자열 추출 |
| `toUpperCase()` | 대문자 변환 |
| `replace()` | 문자열 치환 |
| `split()` | 문자열 분할 |

---

## 📐 6. Math 객체
- 수학 계산용 객체 (new 없이 사용)
- 주요 메소드
  - `Math.random()` : 0~1 미만 난수
  - `Math.floor(n)` : 소수점 버림
  - `Math.sqrt(x)` : 제곱근
  - `Math.PI` : 파이 값

```javascript
for(let i=0; i<10; i++) {
  let m = Math.random()*100;
  let n = Math.floor(m);
  document.write(n + " ");
}
```

---

## 🧑‍💻 7. 사용자 객체 만들기
### 1) `new Object()` 방식
```javascript
let account = new Object();
account.owner = "황기태";
account.code = "111";
account.balance = 35000;
account.deposit = function(money) { this.balance += money; };
account.withdraw = function(money) { this.balance -= money; return money; };
account.inquiry = function() { return this.balance; };
```

### 2) 리터럴 표기법
```javascript
let account = {
  owner: "황기태",
  code: "111",
  balance: 35000,
  deposit: function(money) { this.balance += money; },
  withdraw: function(money) { this.balance -= money; return money; },
  inquiry: function() { return this.balance; }
};
```

### 3) 프로토타입(생성자 함수) 방식
```javascript
function Account(owner, code, balance) {
  this.owner = owner;
  this.code = code;
  this.balance = balance;
  this.deposit = function(money) { this.balance += money; };
  this.withdraw = function(money) { this.balance -= money; return money; };
  this.inquiry = function() { return this.balance; };
}

let account = new Account("황기태", "111", 35000);
```

---

## 📝 정리
- 자바스크립트는 **객체 기반 언어**로 다양한 객체 활용 가능
- 코어 객체: `Array`, `Date`, `String`, `Math`
- 사용자 정의 객체는 3가지 방법으로 생성 가능
- 프로토타입은 클래스와 유사한 역할 수행
