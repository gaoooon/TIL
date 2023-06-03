## for문

### for문은 똑같은 코드를 일정 횟수만큼 반복하도록 하는 명령문이다

``` js
// 1부터 10까지 로그를 생기게 한다
for(let i = 1; i <= 10; i++) {
  console.log(i)
}

// 위에있는 반복문과 같이 10번 반복하지만 10부터 1까지 역순으로 로그를 생기게 한다
for(let i = 10; i >= 1; i--) {
  console.log(i)
} 
```

## while문
### while문은 for문과 같이 코드를 일정 횟수만큼 반복하도록 하는 명령문이다

```js
const fruit = ["banana", "apple", "orange", "grape", "peach"]

let i = 0;

// 조건이 거짓이 될때까지 반복한다
whlie(i < 5) {
  console.log(fruit[i]);
  i++;
}
```

## do while문
### do while문은 do안에 있는 코드를 실행하고 while의 조건이 거짓이 되면 빠져나오는 명령문이다

### while문과 do while문의 차이점

- ### while문은 조건이 처음부터 거짓이라면 1번도 실행하지 않지만 do while문은 무조건 1번은 실행하게 된다

``` js
// 이런식으로 사용가능하다
do {
  const i = 1;
  const plus = 0;
  plus += i + 3;
  i++;
} 
while (plus < 20) { // 4번 반복하고 plus가 22가 되어 조건이 거짓이 되서 plus의 값을 로그로 남긴다
console.log(plus)
}