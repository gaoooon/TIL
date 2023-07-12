# `Function`

## function 기본 구조

```js
function [함수 이름]() {
    실행할 코드
}
// 실행할때

[함수이름]();

```

## function에 매개변수를 넣을때

```js
function [함수 이름](매개변수1, 매개변수2) {
    실행할 코드
}
// 괄호안에 넣고 쉼표로 구분한다
```

#### example

```js
function hello(name) {
  console.log("hello my name is", name);
}

hello("방가온");

// "hello my name is 방가온" 이런식으로 나온다
```

## 함수 `선언식(declarations)`과 `표현식(expressions)`

- ### 선언식

```js
// 함수 선언식은 변수를 선언할때는 const나 let으로 하듯이 함수를 선언 할때는 function으로 시작해서 선언한다

function example() {
  console.log("example");
  console.log("test");
}
```

- ### 표현식

```js
// 표현식은 함수를 선언하고 선언한 함수를 변수에 할당하는 식으로 된다
const example = function () {
  console.log("example");
  console.log("test");
};

// arrow function
const example = () => {
  console.log("example");
  console.log("test");
};
```
