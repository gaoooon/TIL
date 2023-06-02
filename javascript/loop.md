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