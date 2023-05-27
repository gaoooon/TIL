### 자바스크립트에서 setInterval()함수로 일정한 시간마다 코드를 반복하게 할 수있다

```js
// 사용 방법
setInterval(실행할 함수, 간격);
```

```js
// 예시
const clock = document.querySelector("h2#clock");

function getClock() {
  const date = new Date(); // 현재 날짜 및 시간이 date에 저장됨
  const hours = String(date.getHours()).padStart(2, "0"); // getHours함수는 date변수에 저장되어있는 날짜와 시간중에서 시를 가져온다
  const minutes = String(date.getMinutes()).padStart(2, "0"); // String은 가져온 시간을 문자열로 바꾸어준다
  const seconds = String(date.getSeconds()).padStart(2, "0"); // padstart는 c언어로 치면 %02d와 같은것이다
  clock.innerText = `${hours}:${minutes}:${seconds}`;
}

setInterval(getClock, 1000); // getClock함수를 1초마다 실행한다

// 이런식으로 시계를 만들수 있다
```
