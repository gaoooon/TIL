# Cross Browsing

크로스 브라우징이란 다양한 브라우저와 다양한 버전에서 자신의 웹페이지를 일관되게 동작하고 표시 할 수 있도록 하는 기술이다

## Cross Browsing 문제를 해결하기 위한 방법들

### Reset CSS

브라우저마다 기본 css 지정값들이 다 다르다
<br>
그래서 초기 css값을 reset을 해서 브라우저마다의 기본값들을 통일을 해주면 크로스 브라우징 문제를 완화할수 있다

### 많은 브라우저에서 지원하는 html tag, css attribute, js method 사용

브라우저마다 지원하는 html tag, css attribute, js method가 다 다르다
<br>
다 다르기 때문에 MDN 같은 곳에서 호환성이 좋은 tag, attribute, method를 찾아서 사용하는것이 좋다

<img width="799" alt="스크린샷 2024-11-12 오후 9 06 55" src="https://github.com/user-attachments/assets/d1c2fc6f-36ec-400b-8a91-a3e692c5a34f">
ex) css background-color 속성 같은 경우에는 모든 브라우저에서 지원하는 속성이여서 크로스 브라우저 문제를 해결할수 있다

### 다양한 브라우져 테스트

사실 모든 브라우저에서 테스트를 해보는게 가장 확실한 방법이다
<br>
직접 디자인과 비교하면서 테스트를 한다면 바로바로 다른점을 알 수 있어 해결하기도 더 편할것이다
