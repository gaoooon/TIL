## CSS Module.

css module의 장점

- 클래스 중첩 방지
- 가독성 향상
- 확장성

<hr>

#### 사용방법

파일명을 `이름.module.css`로 하고 원래 css를 하는것 처럼 사용하면 된다

```jsx
import "./Box.css"; // 일반 사용

import styles from "./Box.module.css"; // 모듈 사용
```

기존 CSS는 위에 있는것처럼 사용하지만 모듈은 컴포넌트를 import하는것처럼 사용한다

```jsx
import styles from "./Box.module.css";

function Box() {
  return <div className={styles.Box}>{styles.Box}</div>;
}
```

object를 사용하는것처럼 사용하면 된다
