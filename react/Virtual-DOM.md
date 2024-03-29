## Virtual DOM

Virtual DOM(가상 돔)이란 돔을 가볍게 만든 자바스크립트 객체이다

#### react 에서는 가상 돔을 이용하여 돔을 조작하는 것을 간편하게 만들어준다

<hr>

#### 기존 돔 조작 방법

```js
document.querySelector("#title").style.color = "red";
```

이런식으로 돔을 조작해 글씨 색깔을 red로 수정을 한다면 아래와 같은 과정이 수행된다

-> `해당 element를 찾고 해당 element와 자녀 element를 제거`<br>
-> `새롭게 수정된 element들로 교체` <br>
-> `css를 다시 계산` <br>
-> `레이어 정보를 알맞게 수정`<br>
-> `렌더링`

사실 돔트리에 있는 정보를 수정해주는것은 그렇게 어렵지 않다<br>
하지만 매번 돔을 조작할때 마다 렌더링하는 것은 꽤나 비효율적이다

<hr>

#### 리액트에서 가상돔을 사용해서 돔을 조작하는 방법

- 리엑트는 항상 2개의 가상돔 객체를 가지고 있다 (한개는 렌더링 이전의 가상돔 다른 한개는 렌더링 이후의 가상돔)

-> `리액트에서는 상태가 변경`<br>
-> `렌더링이 되고 보일 가상돔을 생성`<br>
-> `렌더링 이전의 가상돔과 비교`(비교하는 과정을 Diffing이라고 한다) <br>
-> `바뀐 element부분만 실제 돔에 적용`(이 전체 과정을 Reconciliation(재조정)이라고 부른다)

- 리액트의 재조정 과정은 바꾼 모든부분을 한번에 실제돔에 적용시키기 때문에 굉장히 효율적이다
