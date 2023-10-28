## promise

promise는 javascript에서 비동기 처리를 도와주는 객체이다

### 장점

- 콜백지옥 탈출

### promise 객체 만들기

```js
promise 객체 생성

const promise = new Promise((resolve, reject) => {...});
```

promise 객체를 생성할때 인자로 executor라고 불리는 함수를 받는다
<br>
executor는 인자로 resolve와 reject라는 콜백함수를 받는다
<br>
executor함수 안에서는 어떤 상황이든 콜백을 호출 해야한다

- resolve(value) — executor함수 안에서 코드가 성공적으로 끝난 경우 그 결과를 나타내는 value와 함께 호출
- reject(error) — 에러 발생 시 에러 객체를 나타내는 error와 함께 호출

<hr>

promise 객체는 3가지의 상태가 존재한다

- Pending(대기) : 로직이 완료 되지 않은 상태
- Fulfilled(이행) : 코드가 성공적으로 끝나 값을 반환한 상태
- Rejected(실패) : 코드가 실패하거나 오류가 난 상태

#### pending -> fulfilled

```js
const promise = new Promise((resolve, reject) => {
  setTimeout(() => {
    resolve("성공");
  }, 3000);
});

// resolve가 실행 되기 전까지는 pending 상태였다가 resolve를 실행해 fulfilled 상태가 된다
```

#### pending -> rejected

```js
const promise = new Promise((resolve, reject) => {
  setTimeout(() => {
    reject("실패");
  }, 3000);
});

// reject가 실행 되기 전까지는 pending 상태였다가 reject를 실행해 rejected 상태가 된다
```

## then, catch

## then

then메서드는 promise 객체가 fulfilled 상태로 값을 반환했을때 사용할 수 있다

```js
const promise = new Promise((resolve, reject) => {
  setTimeout(() => {
    resolve("성공");
  }, 3000);
});

promise.then((result) => console.log(result)); // 성공
```

## catch

catch메서드는 promise 객체가 rejected 상탤 값을 반환했을때 사용할 수 있다

```js
const promise = new Promise((resolve, reject) => {
  setTimeout(() => {
    reject("실패");
  }, 3000);
});

promise.catch((error) => console.log(error)); // 실패
```
