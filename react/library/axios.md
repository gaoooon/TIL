## axios

axios는 http 통신을 쉽고 간편하게 사용 할 수 있게 만든 promise 기반으로 만들어진 라이브러리이다

### 특징

- http method를 쉽게 사용할수 있다
- js 내장 함수인 fetch에 비해 기능이 다양하다
- 요청을 보내거나 받기전 인터셉트가 가능하다
- 자동으로 JSON으로 변환해준다

<hr>

### install

```js
// using npm
$ npm install axios

// using yarn
$ yarn add axios
```

<hr>

### http method

```js
axios.get("getUrl"); //get

axios.post("postUrl", { data }); //post

axios.delete("deleteUrl"); //delete

axios.put("putUrl", { data });
```

> 이처럼 http method를 뒤에 붙여주면 바로 사용가능하다

<hr>

### example

```js
import axios from "axios";
// 사용할곳에서 import해준다

const api = async () => {
  const response = await axios.get("getUrl");
  console.log(response.data);
};
```

> fetch를 사용하였다면 JSON으로 변환해주어야 했지만 axios를 사용한다면 axios에서 자동으로 JSON으로 변환해주어 간편하다

<hr>

### instance

인스턴스는 base url과 다른 기타 설정들을 미리 변수에 설정 해놓는다고 생각하면 된다

```js
import axios from "axios";

export const axiosInstance = axios.create({
  baseURL: "base url...",
  headers: { Authorization: APIKEY },
});

const fetchUserInfo = async () => {
  const { data } = await axiosInstance.get("getUrl");
  console.log(data);
};
```

> create 메서드를 사용해 baseURL과 API key를 설정해 주었다

<hr>

### interceptor

interceptor는 요청을 보내기전, 응답을 받기전에 가로채 request config나 response를 추가, 삭제, 수정등을 할 수 있게 도와준다

- #### request inteceptor

```js
axiosInstance.interceptors.request.use((config) => {
  config.headers.Authorization = APIKEY;

  return config;
});
```

> 이런식으로 요청을 보내기전에 가로채서 APIKEY를 추가해주었다

- #### response interceptor

```js
axiosInstance.interceptors.response.use((response) =>
  response.status == 200 ? response.data : Promise.reject(response.data)
);
```

> 응답을 가로채 응답의 상태가 200라면 정상적인 데이터를 아니라면 reject에 넣어서 반환한다
