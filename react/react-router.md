## `react router`

### react router를 알기전 routing의 개념을 간단히 알아 보겠다<br>routing이란 사용자가 요청한 URL에 맞는 페이지로 이동하는 것이다<br>react router는 routing을 해주는 라이브러리이다

### 그러면 a태그와의 차이를 물어볼 수 있다 <br>차이점은 a태그를 사용해 다른 페이지로 이동할때는 새로고침을 한다음에 페이지를 이동한다는 단점이 있다 <br>하지만 react router를 사용해 페이지를 이동한다면 새로운 페이지를 로드하지 않기 때문에 불필요한 렌더링을 막을 수 있다

- #### 사용방법

```jsx
<Routes>
  URL뒤에 path안에 있는 문자열이 있으면 element안의 컴포넌트가 return된다
  <Route path="/" element={<Home />} />
  <Route path="/detail" element={<Detail />} />
</Routes>
```
