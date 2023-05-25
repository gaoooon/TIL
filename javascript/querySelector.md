## query selector

### html에 있는 element를 가져올때 사용한다

```js
// hello라는 변수에 html에서 hello라는 클래스이름을 가지고 있는 element를 가져온다
const hello = document.querySelector(".hello");
```

#### querySelector는 element를 하나만 가져올 수 있다

#### 여러개를 가져오고 싶다면 querySelectorAll을 사용하면 된다 (배열 형태로 가져온다)

```js
// div태그안에 hello라는 클래스이름을 가지고 있는 element모두를 가져온다
const good = document.querySelectorAll("div .hello");
```

```js
//예
const hello = document.querySelector("#hello");
// hello라는 변수에 hello라는 아이디를 가지고 있는 element를 가져와서 innerText를 변경했다
hello.innerText = "bye";
```
