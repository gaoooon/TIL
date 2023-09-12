## event Bubling

이벤트 버블링이란 자식요소의 event가 부모요소로 전파 되는것을 말한다

<hr>

```jsx
<div
  id="1"
  onClick={(e) => {
    console.log(e.target.id, "clicked");
  }}
>
  <div
    id="2"
    onClick={(e) => {
      console.log(e.target.id, "clicked");
    }}
  >
    <div
      id="3"
      onClick={(e) => {
        console.log(e.target.id, "clicked");
      }}
    ></div>
  </div>
</div>
```

이런 식의 div 태그가 있다고 생각해보면 id가 "3"인 div를 클릭 한다면 console에는 log가 3,2,1 차례대로 클릭 된다고 나온다 이유는 z축으로 봤을때는 div 태그 모두를 관통하기 때문에 모두 log가 찍힌다

<hr>

### 해결 방법

id가 "3"인 div를 클릭했을때 그 div의 onClick 이벤트를 실행시키고 싶다면 id가 "2"인 곳에 버블링을 막는 stopPropagation() 함수를 사용하면 된다

```jsx
<div
  id="1"
  onClick={(e) => {
    console.log(e.target.id, "clicked");
  }}
>
  <div
    id="2"
    onClick={(e) => {
      e.stopPropagation();
      console.log(e.target.id, "clicked");
    }}
  >
    <div
      id="3"
      onClick={(e) => {
        console.log(e.target.id, "clicked");
      }}
    ></div>
  </div>
</div>
```

이런 식으로 사용한다
