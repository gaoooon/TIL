## axios

### react에서 서버에 요청을 보내서 정보를 가져오는 방법은 여러가지가 있다 첫번째는 js에서 기본으로 사용할수 있는 fetch가 있고 또 한개의 방법으로는 axios가 있다

- #### 사용 방법

```
npm install axios
<!-- 터미널에서 axios를 설치해준다 -->
```

```jsx
import axios from "axios";
// 사용할곳에서 import해준다

const api = async () => {
  const response = await axios.get("get요청을 보낼 주소"); // get위치에 다른 method를 넣어서 사용할수도 있다
  console.log(response);
};
// axios를 사용하면 fetch를 사용할때 보다 더 간편하게 사용할수 있다
```
