## `state`

### state는 한국어로 상태라는 뜻이다 react에서도 크게 다르지 않다<br>react에서 state는 상태가 바뀔때 마다 다시 렌더링한다

### state를 사용하기 위해서는 import 해야 한다

```jsx
import { usestate } from "react";
```

### 사용 예

```jsx
const [num, setNum] = useState(0); // 선언
setNum(4); // num의 값 변경하기
```
