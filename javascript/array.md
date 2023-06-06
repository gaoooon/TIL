## array

#### array(배열)은 여러개의 데이터를 동시에 가질 수 있다

```js
const fruit = ["apple", "grape", "banana"];
/*                0        1         2    */

/* 추가로 값 할당하기(맨뒤에 추가된다)*/
fruit.push("watermelon");

/* grape를 불르고 싶을때*/
console.log(fruit[1]);
```

## array에 쓸수 있는 함수

```js
// foreach()
fruit.foreach(eatFruit); // 배열 안에 있는 각각의 항목 만큼 eatFruit함수를 실행한다

// filter()
fruit.filter((fruit) => fruit !== "banana");
```
