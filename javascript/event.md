## event

### event는 마우스를 클릭했을 때, 키를 입력했을 때 등 어떤사건을 발생시키는 것을 말한다

```js
//각 element가 가지고 있는 event를 알고 싶을때
const hello = document.querySelector(h1);
console.dir(hello);
// console 창에 on~~~~ 라고 되있는것들이 event 이다
```

### event가 만족했을때 코드를 실행하는 방법

```js

const header = document.querySeletor(.div h1);

function handlehederclick() {
    console.log("header was clicked");
}
//addEventListener는 event가 만족했는지 판단하는 함수
header.addEventListener("click",handleheaderclick);
```

### if,else를 사용

```js
function handleColorclick() {
  const currentColor = h1.style.color;
  if (currentColor === "red") {
    h1.style.color = "orange";
  } else {
    h1.style.color = "red";
  }
}

h1.addEventListener("click", handlecolorclick);
```

### css에서 스타일을 지정해 놓고 class를 바꾸는 방법도 있다

```js
function handleColorclick() {
  h1.className = "bigger";
}

h1.addEventListener("click", handlecolorclick);
//하지만 이렇게 사용하면 원래있던 클래스를 바꾸기 때문에 불편하다
//이럴때는 classlist를 사용하면 된다
```

### classList를 사용

```js
function handleColorclick() {
  const clickedClass = "clicked";
  if (h1.classList.contains(clickedClass)) {
    h1.classList.remove(clickedClass);
  } else {
    h1.classList.add(clickedClass);
  }
}

h1.addEventListener("click", handlecolorclick);
```

```js
//위의 코드를 간결하게 toggle을 사용해 줄일수 있다
function handleColorClick() {
  h1.classList.toggle("clicked");
}

h1.addEventListener("click", handleColorClick);
```
