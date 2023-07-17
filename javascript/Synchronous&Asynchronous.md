## `Synchronous(동기)&Asynchronous(비동기)`

### 동기는 위에서부터 차례대로 코드가 실행되는 것이고

### 비동기는 위의 코드가 끝나는것에 상관 없이 다음 코드를 실행하는 것이다

- #### 예

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

## `Promise`

### Promise는 비동기 작업을 조금 더 편하게 처리 할 수 있도록하는 기능이다

- #### 사용방법

```js
// promise 만들기
const testPromise = new Promise(
  (reslove /*성공일때 사용*/, reject /*실패일때 사용*/) => {
    const a = 1;
    setTimeout(() => {
      if (a === 1) {
        reslove(1);
      } else {
        reject(new Error());
      }
    }, 1000);
  }
);

testPromise //
  .then((n) => console.log(n)) // 성공일때 실행됨
  .catch((error) => console.log(error)); // 실패일떄 실행됨
```

## `async/await`

### async/await은 Promise를 더 쉽게 사용할수 있게 해준다

- #### 사용방법

```js
// 함수 선언 할때 앞에 async를 붙인다
async function test() {
  const response = await fetch(URL); // URL 주소로 요청을 보내고
  const json = await response.json();
  console.log(json);
}
```
