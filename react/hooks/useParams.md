## useParams

useParams은 react-router를 사용할때 파라미터의 정보를 가져와 활용할때 useParams를 사용할수 있다

```jsx
import { useParams } from "react-router-dom";
```

사용하기 위해서는 router설치와 import를 해준다

```jsx
//"/detail/:id" 만약 URL이 이런 형식이라면

const userData = {
  kim: { name: "min jae", no: "3", team: "뮌헨" },
  son: { name: "heung min", no: "7", team: "토트넘" },
  lee: { name: "kang in", no: "19", team: "파리" },
};

const User = () => {
  const { id } = useParams(); //useParams을 사용해서 비구조 할당으로 파라미터의 값을 받을수 있다
  const profile = userData[id];
  if (!profile) {
    return <div>존재하지 않는 유저입니다.</div>;
  }
  return (
    <div>
      <h3>
        {profile.name}({profile.no})
      </h3>
      <p>{profile.team}</p>
    </div>
  );
};
```
