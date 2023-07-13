## `destructuring`(비구조화 할당)

### destructuring이란 배열 또는 객체를 파괴하여 개별적인 변수에 할당하는 것이다

- #### (array)배열

```js
// 방법1
const num = [1, 2, 3];

const a = num[0];
const b = num[1];
const b = num[2];

console.log(a, b, c); // 각각 1, 2, 3이 나온다
```

```js
// 방법2
const num = [1, 2, 3];

const [a, b, c] = num;

console.log(a, b, c); // 각각 1, 2, 3이 나온다
```

- #### object(객체)

```js
// 방법1
const boy = { name: "gaon", height: 179.6, weight: 68 };

const boyName = boy.name;
const boyHeight = boy.height;
const boyWeight = boy.weight;

console.log(boyName, boyHeight, boyWeight); // 각각 gaon, 179.6, 68이 나온다
```

```js
// 방법2
const boy = { name: "gaon", height: 179.6, weight: 68 };

const { boyName, boyHeight, boyWeight } = boy;

console.log(boyName, boyHeight, boyWeight); // 각각 gaon, 179.6, 68이 나온다
```
