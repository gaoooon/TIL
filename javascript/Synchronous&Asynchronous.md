## `Synchronous(동기)&Asynchronous(비동기)`

동기란 코드가 위에서 아래로 차례대로 실행되는 것이다

비동기란 위의 코드가 끝나는것에 상관 없이 다음 코드를 실행하는 것이다

- ### 예

```js
// 동기
console.log("1");
console.log("2");
console.log("3");
// 차례대로 1,2,3 이 로그 된다

// 비동기
console.log(1);
setTimeout(() => {
  console.log(2);
}, 1000);
console.log(3);
// 비동기처리가 되어 1,3,2 순서대로 로그된다
```
