## queryQelector

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

## createElement

### js에서 element를 만들때 사용한다

```js
// 이미지 태그를 만들고 변수에 저장했다
const imgTag = document.createElement("img");
```

### js에서 element를 만들었지만 아직은 html에 적용이 안되어있다 html에 만든 element를 추가해 줘야 한다

```js
// append함수를 써서 html body에 imgTag를 적용해 줬다 (prepend를 쓰면 body 맨앞에 적용할수 있다 append는 맨뒤)
document.body.appenChild(imgTag);
```
