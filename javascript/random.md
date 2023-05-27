## random

### ramdom함수는 자신이 정한 범위 내에서 무작위로 값을 정하는 함수이다

```js
// 기본형
// 범위를 정하지 않으면 0~1 안의 값중 무작위로 random변수에 저장된다
const random = Math.random();
```

```js
// 범위 정하기
const random = Math.random() * 10; // 범위가 0~10의로 정해졌다
```

### random함수는 값이 실수로 나온다 정수로 나온다 정수로 나오게 하려면 여러가지 방법이 있다

```js
const random = Math.round(Math.random() * 5); // round함수는 소수점 첫번째자리에서 반올림하는 함수이다
// random의 저장 되는 최대 값은 5이다
```

```js
const random = Math.ceil(Math.random() * 5); // ceil함수는 소수점 첫번째 자리에서 무조건 올림하는 함수이다
// random의 저장 되는 최대 값은 5이다
```

```js
const random = Math.floor(Math.random() * 5); // floor함수는 소수점 첫번째 자리에서 무조건 내림하는 함수이다
// random의 저장 되는 최대 값은 4이다
```
