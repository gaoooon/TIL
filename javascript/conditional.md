# if

### 특정 조건이 만족할때 작업을 수행할수 있다

```js
// 기본구조
if (조건) {
    조건이 만족할때 실행할 코드
}
else {
    조건이 만족하지 않을때 실행할 코드
}
```

```js
// 예시
// parseInt는 문자를 숫자로 변환하는 함수
const age = parseInt(prompt("how old are you?"));

// isNaN은 값이 NaN(not a number)이면 true 숫자면 flase로 반환한다
if (isNaN(age)) {
  console.log("please write a number");
} else {
  console.log("your age is " + age);
}
```
