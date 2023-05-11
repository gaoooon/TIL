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

### flex-direction (container에 적용)

|     속성값     |                설명                |
| :------------: | :--------------------------------: |
|      row       |     아이템들이 가로로 배치된다     |
|  row-reverse   | 아이템들이 역순으로 가로 배치 된다 |
|     column     |     아이템들이 세로로 배치된다     |
| column-reverse | 아이템들이 역순으로 세로 배치 된다 |

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

|    종류     |                설명                |
| :---------: | :--------------------------------: |
| flex-basis  | 아이템의 기본 크기를 설정하는 속성 |
|  flex-grow  | 일정한 비율로 나누어 차지하는 속성 |
| flex-shrink | 아이템 줄어들때의 값을 정하는 속성 |

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
