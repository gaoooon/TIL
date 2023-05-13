## 캐스 캐이딩이란?

#### 우선순위를 어떻게 설정하는가에 대한 규칙이다

### 우선순위

#### 1. style attribute(스타일 속성)<br>2. id selector(아이디 선택자)<br>3. class selector(클래스 선택자)<br>4. tag selector(태그 선택자)

#### 이 순서대로 적용된다, 하지만 !important를 사용하면 1순위가 된다

```css
<head>
    <style>
        p {color: red;}
        #color {color: blue !important;}
        /*원래 였다면 1순위인 스타일 속성의 색깔인 노란색으로 적용되야*/
        /*하지만 class 선택자에 !important를 썻기 때문에 파란색으로 적용 된다*/
        .class {color: green;}
    </style>
</head>
<body>
    <p id="color" class="class" style="color:yellow">안녕하세요</p>
</body>
```

## block, inline

### block

#### block은 <p> 태그와 같이 다음 요소가 줄바꿈이 되는것들을 말한다

### inline

#### inline은 <a> 태그와 같이 다음 요소가 줄바꿈이 되지 않고 이어지는 것을 말한다

### display 속성으로 inline으로 할지 block으로 할지 정할수 있고<br>inline방식은 width와 height 값이 적용 되지 않는다

```css
<head>

    <style>
        a {display: block;}
        p {display: inline;}
    </style>

</head>
<body>

    <a href="https://www.instagram.com/" >intstagram</a>

    <p>facebook</p>

</body>
```

## box-sizing

### box-sizing은 박스의 크기를 어떤 것을 기준으로 계산할지 정하는 속성이다

- content-box: 콘텐트 영역을 기준으로 크기를 정한다(기본값)
- border-box: 보더를 기준으로 크기를 정한다

## position

### 종류

|  속성값  |                    설명                    |
| :------: | :----------------------------------------: |
|  static  |    원래있어야 할 위치에 있는다(기본값)     |
| relative | 원래있어야 할 위치를 기준으로 바꿀 수 있다 |
| absolute |     조상 요소를 기준으로 바꿀 수 있다      |
|  fixed   |             화면에 고정이 된다             |

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

## grid

### grid란?

#### grid는 flex와 마찬가지로 레이아웃을 배치하는 기능이다 <br>flex와는 조금 다른데 flex는 1차원으로만 레이아웃을 배치 했다면 grid는 2차원으로 레이아웃을 배치 가능하다

#### grid도 사용하기 위해서는 container에 display 속성의 값으로 grid를 적용시켜야 한다  

### container에 적용하는 grid 속성들

|    종류     |                 설명                 |
| :---------: | :----------------------------------: |
|grid-template|행이나 열을 몇개로 할건지를 정하는 속성|
|grid-gap|item사이사이의 간격을 정할수있다(row나 column만도가능)|

### item에 적용하는 grid 속성들

|    종류     |                 설명                 |
| :---------: | :----------------------------------: |
|grid-start|item이 어디서부터 시작할건지를 정하는 속성|
|grid-end|item이 어디서 끝날건지를 정하는 속성|

### grid-template-areas
#### grid-item에 이름을 붙이고 그 이름을 이용해서 배치하는 방법입니다.

``` css
.container {
  grid-template-areas:
      "a a a"
      "b b c"
      "b b c"
      }
```
#### 이런식으로 하면 item에 grid-area로 a라고 지정해 놓은것은 a영역을 다차지하고 b로 지정한것은 b영역, c로 지정한것은 c영역을 차지한다

### grid-template-areas를 활용해 만들어본 것이다
``` html
<!DOCTYPE html>
<html lang="en">
<head>
    <style>
      .container {
    padding: 3rem;
    display: grid;
    grid-template-columns: repeat(4, 10%);
    grid-template-rows: 1fr 1fr 1fr;
    grid-gap: 1rem;
    grid-template-areas: 
        "a a a d"
        "b c f g" 
        "b e e e";
}
img {
    width: 100%;
    height: 100%;
    object-fit:cover;
}

.img1 {
    grid-area: a;
}
.img2 {
    grid-area: b;
}
.img3 {
    grid-area: c;
}
.img4 {
    grid-area: d;
}
.img5 {
    grid-area: e;
}
.img6 {
    grid-area: f;
}
.img7 {
    grid-area: g;
}
    </style>
</head>
<body>
<div class="container">
    <div class="item img1"><img src="https://file2.nocutnews.co.kr/newsroom/image/2023/01/21/202301210408091762_0.jpg"></div>
    <div class="item img2"><img src="https://img.wkorea.com/w/2022/08/style_62fb07cdb8835-525x700.jpg"></div>
    <div class="item img3"><img src="https://spnimage.edaily.co.kr/images/photo/files/NP/S/2023/02/PS23021600103.jpg"></div>
    <div class="item img4"><img src="https://img1.daumcdn.net/thumb/R1280x0.fjpg/?fname=http://t1.daumcdn.net/brunch/service/user/cnoC/image/U5u-6CeJlogKbzBf5Hh159n6i8o"></div>
    <div class="item img5"><img src="https://image.ajunews.com/content/image/2023/01/29/20230129141136216204.jpg"></div>
    <div class="item img6"><img src="https://img.sbs.co.kr/newimg/news/20220729/201686644_1280.jpg"></div>
    <div class="item img7"><img src="https://cdn.eyesmag.com/content/uploads/posts/2022/09/06/1-e2d4a903-464a-4a1e-b821-a0988507581b.jpg"></div>
</div>
</body>
</html>