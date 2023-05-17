## grid

### grid란?

#### grid는 flex와 마찬가지로 레이아웃을 배치하는 기능이다 <br>flex와는 조금 다른데 flex는 1차원으로만 레이아웃을 배치 했다면 grid는 2차원으로 레이아웃을 배치 가능하다

#### grid도 사용하기 위해서는 container에 display 속성의 값으로 grid를 적용시켜야 한다

### container에 적용하는 grid 속성들

|     종류      |                          설명                          |
| :-----------: | :----------------------------------------------------: |
| grid-template |        행이나 열을 몇개로 할건지를 정하는 속성         |
|   grid-gap    | item사이사이의 간격을 정할수있다(row나 column만도가능) |

### item에 적용하는 grid 속성들

|    종류    |                    설명                    |
| :--------: | :----------------------------------------: |
| grid-start | item이 어디서부터 시작할건지를 정하는 속성 |
|  grid-end  |    item이 어디서 끝날건지를 정하는 속성    |

### grid-template-areas

#### grid-item에 이름을 붙이고 그 이름을 이용해서 배치하는 방법입니다.

```css
.container {
  grid-template-areas:
    "a a a"
    "b b c"
    "b b c";
}
```

#### 이런식으로 하면 item에 grid-area로 a라고 지정해 놓은것은 a영역을 다차지하고 b로 지정한것은 b영역, c로 지정한것은 c영역을 차지한다

### grid-template-areas를 활용해 만들어본 것이다

```html
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
        object-fit: cover;
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
      <div class="item img1">
        <img
          src="https://file2.nocutnews.co.kr/newsroom/image/2023/01/21/202301210408091762_0.jpg"
        />
      </div>
      <div class="item img2">
        <img
          src="https://img.wkorea.com/w/2022/08/style_62fb07cdb8835-525x700.jpg"
        />
      </div>
      <div class="item img3">
        <img
          src="https://spnimage.edaily.co.kr/images/photo/files/NP/S/2023/02/PS23021600103.jpg"
        />
      </div>
      <div class="item img4">
        <img
          src="https://img1.daumcdn.net/thumb/R1280x0.fjpg/?fname=http://t1.daumcdn.net/brunch/service/user/cnoC/image/U5u-6CeJlogKbzBf5Hh159n6i8o"
        />
      </div>
      <div class="item img5">
        <img
          src="https://image.ajunews.com/content/image/2023/01/29/20230129141136216204.jpg"
        />
      </div>
      <div class="item img6">
        <img
          src="https://img.sbs.co.kr/newimg/news/20220729/201686644_1280.jpg"
        />
      </div>
      <div class="item img7">
        <img
          src="https://cdn.eyesmag.com/content/uploads/posts/2022/09/06/1-e2d4a903-464a-4a1e-b821-a0988507581b.jpg"
        />
      </div>
    </div>
  </body>
</html>
```
