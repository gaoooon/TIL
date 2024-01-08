## appRouter

Next에서는 app 라우터라는 폴더를 기준으로 path를 나눌수 있는 기능을 제공한다

### 특징

- 각각의 폴더 이름으로 path가 나누어져 간편하다

### 사용방법

#### 정적 path 만들기

```
src
└── app
    ├── profile
    |        └─ page.tsx
    └── page.tsx
```

위에 있는 것을 보면 app 폴더 안에서 라우팅 하는데 폴더 이름이 path가 된다
<br>
그래서 만약 서비스 주소가 gaon.com이라면 `gaon.com/profile`이라는 경로가 된다
<br>
`gaon.com/profile`에서 페이지를 보여주고 싶을때는 path 폴더 안에 `page.js(ts, jsx, tsx)` 파일을 만들어 주면 된다

#### 동적 path 만들기

```
src
└── app
    ├── profile
    |     └─ [username]
    |            └─ page.tsx
    └── page.tsx
```

이런식으로 폴더 이름을 []로 감싸서 만들면 동적 path를 만들수 있다
<br>
경로는 `gaon.com/profile/[다양한 주소]`가 된다 이런식으로 동적으로 path를 받아 값에 따라 화면을 그릴수 있게 된다

### layout

next에서는 ui를 공유할수 있는 layout이라는 기능을 제공합니다 이 기능으로 모든 페이지에서 공통적으로 사용되는 ui(header, menu)를 layout에서 만들어 반복되는 부분을 줄일수 있습니다

#### layout 파일 위치

```
src
└── app
    ├── profile
    |     └─ [username]
    |            ├── layout.tsx
    |            └── page.tsx
    ├── layout.tsx
    └── page.tsx
```

layout 파일에 위치는 app 폴더 안에 위치한다
<br>
root위치에 위치하면 모든 경로에서 layout을 사용하게 되고 root layout이라고 부르고 필수로 있어야 한다
<br>
그리고 app폴더 하위 폴더에 layout을 위치하게 한다면 path에서만 layout을 사용한다

```tsx
const Layout = ({ children }: { children: React.ReactNode }) => (
  <div>{children}</div>
);

export default Layout;
```

layout 구조는 node를 받아 ui를 추가해 반한하는 형식이다

root layout은 <html>와 <body>을 필수로 가지고 있어야 한다

```tsx
export default function RootLayout({ children }) {
  return (
    <html lang="en">
      <body>{children}</body>
    </html>
  );
}
```

만약 페이지를 그룹화해서 원하는 페이지에만 layout을 배치하고 싶지만 path 때문에 걱정이라면?
<br>
그럴때에는 폴더를 `(폴더이름)` 폴더이름을 정해주고 ()로 감싸서 하면 path에는 영향을 미치지 않는 폴더가 생성된다
<br>
이제 이 폴더 안에 layout.tsx를 만들어 layout을 원하는 페이지 에만 적용시킬수 있다

```
src
└── app
    ├── profile
    |     └─ [username]
    |            ├── layout.tsx
    |            └── page.tsx
    ├──(useHeader)
    |     ├── search
    |     |      └── page.tsx
    |     ├── home
    |     |     └── page.tsx
    |     └── layout.tsx
    ├── layout.tsx
    └── page.tsx
```

이런식으로 그룹화 시켜 `search`와 `home` path에만 특정 layout을 적용시키게 할수 있다
