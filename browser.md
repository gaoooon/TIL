# 브라우저 동작 과정

## Navigation(탐색)

1. 브라우저 주소창에 원하는 url을 적는다 ex) example.com
2. 엔터를 누르면 DNS-Server에 요청을 보내서 example.com의 ip 주소를 받는다 ex) 127.250.206.206
3. 브라우저는 받은 ip 주소의 서버와 TCP 3way handshaking을 거쳐 신뢰성을 보장한다
4. 만약 https로 요청을 보낸다면 TLS handshaking을 거친다(TLS는 암호화된 데이터를 교환하기 위한 협상 과정이다, 암호화를 위한 암호를 결정하고 서로 주고 받음)
5. 서버에 요청을 보내 html 파일을 받는다

## Parsing(구문 분석)

Navigation의 과정을 거쳤다면 아래의 과정을 거쳐 Parsing을 한다

1. 서버로부터 받은 html 파일을 parsing(구문 분석)한다
   <br>
   1-1. 서버가 전송한 html을 바이트 형식으로 받는다
   <br>
   1-2. html에 정의된 인코딩에 따라서 렌더링 엔진이 문자로 변환한다
   <br>
   1-3. 변환된 문자열을 W3C(World Wide Web Consortium) 표준에 지정된 고유 토큰(문법적 의미를 갖는 최소 단위)으로 변환한다
   <br>
   1-4. 변환된 토큰을 부모 자식 관계로 나타낼수 있는 노드로 변환한다
   <br>
   1-5. html에 정의된 여러 태그간의 관계를 해석해서 DOM을 만든다

<img style="background-color:white" src="https://miro.medium.com/v2/resize:fit:1400/format:webp/0*rkjgCl-RSVTvRGgS"/>
   
html 파일을 parsing하는 과정중에 link tag, img tag, script tag를 만난다면 html parsing을 중단하고 각각 파싱을 하게 된다

### link tag

link tag는 주로 css를 불러올때 사용하기 때문에 css를 파싱하는것으로 예를 들어보자면

1. link tag href 주소로 css 파일을 요청해서 받아온다
2. html parsing 과정과 같이 css파일을 parsing해서 CSSOM을 만든다

### img tag

img tag를 만난다면 아래의 순서로 parsing 된다

1. img tag src 주소로 img 파일을 요청해서 받아온다
2. img를 받아올때 2진수 형식으로 받아와 브라우저에서 디코딩한다
3. 디코딩한 img를 메모리에 저장한다

### script tag

script tag는 js파일을 불러올때 사용된다
script tag를 html 파일 parsing 중에 만난다면 parsing이 중단되고 아래와 같이 작동 된다

1. script tag src 주소로 http 요청을 보내서 js 파일을 받는다
2. 브라우저에 있는 javascript 엔진이 js 코드를 토큰으로 변환 시킨다
3. 변환된 js 토큰을 활용하여 AST(Abstract Syntax Tree)로 만든다

## Rendering(표현)

rendering 순서

1. render tree 구성
2. layout
3. paint
4. js 실행
5. reflow, repaint

### render tree

화면에 렌더링되는 것만 모아놓은 tree이다
<br>
html을 parsing해 만든 DOM과 css를 parsing해 만든 CSSOM을 합쳐 render tree를 구성한다

### layout

layout은 render tree를 기반으로 노드의 크기, 위치, 색상 등등을 계산한다

### paint

paint는 layout에서 계산한것을 토대로 실제 화면에 그리는 것이다

### js 실행

위에서 AST로 변환한 js 파일을 중간 코드인 byte 코드로 변환후 인터프리터에 의해 실행된다
만약 실행된 js 파일에서 DOM이나, CSSOM을 조작한다면 다시 render tree를 만들고 layout후 paint 하는데 이것을 reflow, repaint 라고 부른다
