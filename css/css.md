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

## float, clear

### float라는 단어는 원래 ‘뜨다’ 라는 의미이다, 웹페이지에서 이미지를 어떻게 띄워서 텍스트와 함께 배치할 것인가에 대한 속성이다

| 값 종류 |                    설명                     |
| :-----: | :-----------------------------------------: |
| inherit |             부모 요소에서 상속              |
|  left   | 왼쪽에 이미지를 배치한고 오른쪽에 글을 배치 |
|  right  | 오른쪽에 이미지를 배치하고 왼쪽에 글을 배치 |
|  none   |          아무것도 적용하지 않는다           |

### clear는 float를 적용하고 일부만 적용하고 싶지 않을떄 사용한다

| 값 종류 |                     설명                      |
| :-----: | :-------------------------------------------: |
|  none   |           아무것도 적용하지 않는다            |
|  left   |     왼쪽으로 붙는 float 정렬을 취소 한다      |
|  right  |    오른쪽으로 붙는 float 정렬을 취소 한다     |
|  both   | 오른쪽이나 왼쪽에 붙는 float 정렬을 취소 한다 |

```html
<!-- 이런식으로 사용가능 -->
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>Document</title>
    <style>
      .float {
        margin-top: 100px;
      }
      img {
        float: left;
      }
    </style>
  </head>
  <body>
    <div class="float">
      <img src="float.jpg" width="600px" />
      <p>
        float left float right float none float left float right float none
        float left float right float none float left float right float none
        float left float right float none float left float right float none
        float left float right float none float left float right float none
        float left float right float none float left float right float none
        float left float right float none float left float right float none
        float left float right float none float left float right float none
        float left float right float none float left float right float none
      </p>
    </div>
  </body>
</html>
```
