## flex

### flex란?

#### Flexible Box, Flexbox 라고 부르기도 하며 레이아웃 배치 기능이다.

```html
<!-- 기본 구조 -->
<head>
  <style>
    .container {
      display: flex;
    }
  </style>
</head>
<body>
  <div class="container">
    <div class="item">a</div>
    <div class="item">b</div>
    <div class="item">c</div>
  </div>
</body>
```

### container에 적용하는 flex 속성들

- ### flex-direction

|     속성값     |                설명                |
| :------------: | :--------------------------------: |
|      row       |     아이템들이 가로로 배치된다     |
|  row-reverse   | 아이템들이 역순으로 가로 배치 된다 |
|     column     |     아이템들이 세로로 배치된다     |
| column-reverse | 아이템들이 역순으로 세로 배치 된다 |

- ### flex-warp

#### container칸에 아이템이 다 차면 어떻게 할건지를 정하는 속성이다

|     속성값     |              설명               |
| :------------: | :-----------------------------: |
| nowrap(기본값) |      아무것도 하지 않는다       |
|      wrap      | 다음 아이템부터 다음줄로 내린다 |
|  wrap-reverse  |       wrap의 반대로 한다        |

- ### flex-flow

#### flex-direction과 flex-warp을 한번에 지정할수 있다

```html
flex-flow:[flex-direction의 속성값][flex-warp의 속성값];
```

- ### justify-content(main-axis)
- ### align-content(cross-axis)

#### 아이템들을 어떻게 배치할건지를 정하는 속성이다

|       속성값       |            설명            |
| :----------------: | :------------------------: |
| flex-start(기본값) |       왼쪽 정렬된다        |
|      flex-end      |  start의 반대로 정렬된다   |
|       center       |     가운데로 배치된다      |
|    space-around    | 아이템들이 띄어서 배치된다 |

- ### align-items
  |  속성값  |                설명                |
  | :------: | :--------------------------------: |
  | baseline | 텍스트 줄에 맞춰 아이템을 배치한다 |

<hr/>

### 특정 아이템 지정하기

```html
<head>
  <!--특정 아이템 지정하기-->
  <style>
    .item:nth-child(1) {
      color: blue;
    }

    .container {
      display: flex;
    }
  </style>
</head>
<body>
  <div class="container">
    <div class="item">a</div>
    <div class="item">b</div>
    <div class="item">c</div>
  </div>
</body>
```

#### item에 적용하는 속성들

|    종류     |                 설명                 |
| :---------: | :----------------------------------: |
| flex-basis  |  아이템의 기본 크기를 설정하는 속성  |
|  flex-grow  |  일정한 비율로 나누어 차지하는 속성  |
| flex-shrink |  아이템 줄어들때의 값을 정하는 속성  |
|    order    |     아이템의 순서를 바꾸는 속성      |
| align-self  | 각각의 아이템의 위치를 배치하는 속성 |

### holy grail layout

#### holy grail layout

<img src="https://s3-ap-northeast-2.amazonaws.com/opentutorials-user-file/module/2367/4744.png" width="500"/>

```html
<!DOCTYPE html>
<html lang="ko">
  <head>
    <style>
      .container {
        display: flex;
        flex-direction: column;
      }
      header {
        border-bottom: 1px solid black;
        padding: 10px;
        text-align: center;
      }
      footer {
        border-top: 1px solid black;
        padding: 10px;
        text-align: center;
      }
      .content {
        display: flex;
      }
      .content nav {
        border-right: 1px solid black;
      }
      .content aside {
        border-left: 1px solid black;
      }
      nav,
      aside {
        flex-shrink: 0;
      }
      main {
        text-align: center;
        padding: 10px;
        flex-shrink: 0;
        flex-grow: 5;
      }
      nav {
        flex-grow: 1;
      }
    </style>
  </head>
  <body>
    <div class="container">
      <header>
        <h1>NewJeans</h1>
      </header>
      <section class="content">
        <nav>
          <ul>
            <li>소개</li>
            <li>맴버</li>
            <li>노래</li>
          </ul>
        </nav>
        <main>4세대 아이돌 뉴진스</main>
        <aside>ad</aside>
      </section>
      <footer>
        <a href="https://www.youtube.com/channel/UCMki_UkHb4qSc0qyEcOHHJw"
          >NewJeans YouTube</a
        >
      </footer>
    </div>
  </body>
</html>
```

#### 이런식으로 holy grail layout을 만들 수 있다
