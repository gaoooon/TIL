# if, else if, else

### 특정 조건이 만족할때 작업을 수행할수 있다

```js
// 기본구조
if (조건) {
    조건이 만족할때 실행할 코드
}
// else는 있어도 되고 없어도 된다
else {
    조건이 만족하지 않을때 실행할 코드
}
```

### else if

#### else if는 조건이 여러개 일때 사용한다

```js
else if (조건) {
    조건이 만족할때 실행할 코드
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

```js
// else if를 사용한 예시

const age = parseInt(prompt("how old are you?"));

if (isNaN(age)) {
  console.log("please write your age");
} else if (age < 19) {
  console.log("you are so young");
} else {
  console.log("you can drink");
}
```

### 논리연산자

### and(&&) 연산자

```js
// and 연산자는 두개다 참이여야지 참이 된다
true && true === true;
true && false === false;
false && true === false;
false && false === false;
```

<hr>

### or(||) 연산자

```js
// or 연산자는 둘중 한개라도 참이면 참이 된다
true || true === true;
true || false === true;
false || true === true;
false || false === false;
```

<hr>

### not(!) 연산자

```js
// not 연산자는 반대로 된다
!true === false;
!false === true;
```
