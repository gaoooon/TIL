## toastify

toastify는 app에 알림이 필요할때 쉽게 추가 할 수 있는 라이브러리이다

<img src="https://velog.velcdn.com/images/vanillovin/post/962fd243-2d0c-4254-9571-08b8626ba95e/image.gif" width="1000px" >

<hr>

- ### 사용법

```jsx
import { ToastContainer, toast } from "react-toastify";
import "react-toastify/dist/ReactToastify.css";

const App = () => {
  const notify = () => toast("GSM Kim Ju Eun");

  return (
    <div>
      <button onClick={notify}>toast</button>
      <ToastContainer />
    </div>
  );
};
```

toast는 알람을 실행시키는 함수이다, 괄호안에 보여주고 싶은 메세지를 넣으면 된다

ToastContainer는 알람 실행시 표시될 컨테이너에 넣어 주면 된다

```js
const success = () => toast.success("Success!"); // 초록색 창

const error = () => toast.error("Error!"); // 빨간색 창

const warning = () => toast.warning("Warnning!"); // 노란색 창

const info = () => toast.info("Info!"); // 파란색창
```

알람의 종류는 success, error, warning, info 4가지가 있다
