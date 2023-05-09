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
