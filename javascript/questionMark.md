## ?

### js에서는 3가지의 ?사용법이 존재한다

- #### 삼항 연산자(Ternary Operator)

```js
const a = true;

// 물음표 앞의 것이 참이라면 "Tim"을 name에 할당하고 거짓이라면 "James"를 name에 할당하는 구조이다
const name = a ? "Tim" : "James";

// 똑같은 코드이지만 삼항연산자를 사용할때가 더 간편하다
if (a) {
  const name = "Tim";
} else {
  const name = "James";
}
```

- #### 선택적 연결 (Optional Chaining)

```js
const human = {
  name: "Tim",
  age: 20,
  height: { cm: 180, inch: 300 },
};

// 이러면 weight가 없는 속성이라서 오류가 난다
const weight = human.weight.kg;
console.log(weight);

// 하지만 ?.을 하면 오류대신에 undefiend를 리턴한다
const weight = human.weight?.kg;
console.log(weight);
```

- #### 무효화 합체 (Nullish Coalescing)

```js
// 무효화 합체는 ?? 왼쪽의 값이 null이거나 undefiend일때 ?? 오른쪽의 값을 출력하는 것이다

const test = 0;
console.log(test ?? 100); // 0을 출력

console.log(null ?? "hi"); // 'hi'을 출력
```
