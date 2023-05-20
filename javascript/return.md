# return

## 사용 용도

### return은 함수를 중단하거나 주어진 값을 함수에서 값을 반환할때 사용할 수 있다

```js
// 함수를 중단할때
function add(a, b) {
  const add = a + b;
  return;
}
```

```js
// 함수에서 값을 반환할때
function minus(a, b) {
  return a - b;
}

const minus = minus(3, 5);
console.log(minus);
```
