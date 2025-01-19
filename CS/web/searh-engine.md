## 검색 엔진 작동 방식

​
SEO 최적화를 하기 전에 일단 검색 엔진이 어떻게 동작하는지를 알면 최적화 시키는 방법이 어디서 도움이 되는지를 알수 있기 때문에 작동 방식부터 알아보겠다.
​
구글 검색 엔진의 경우 3단계로 이루어져 작동한다.
​
1\. 크롤링 (Crwaling)
​
2\. 색인 생성 (Indexing)
​
3\. 검색 결과 게재(Serving Search Results)
​

### 크롤링 (Crwaling)

​
크롤러라는 로봇이 인터넷을 탐색하면서 여러 웹페이지를 수집한다.
​
기존 데이터베이스에 저장된 URL에서 시작해서 페이지 내의 링크를 따라가면서 더 많은 페이지를 찾는다.
​
크롤러가 발견한 모든 페이지를 크롤링하지는 않고 페이지 내의 robots.txt 파일과 메타 태그를 참고하여 크롤링을 허용한 페이지만 접근한다.
​

### 색인 생성 (Indexing)

​
페이지가 크롤링 되면 페이지의 내용을 파악해야 한다.
​
페이지의 title tag, alt 속성, 이미지, 동영상 등 텍스트 콘텐츠 및 핵심 태그와 속성을 분석하고 구조화 하여 데이터베이스에 저장한다.
​

### 검색 결과 게재 (Serving Search Results)

​
사용자가 검색을 하면 데이터베이스에서 페이지의 품질이 높고 사용자의 검색어와 관련성이 크다고 판단되는 결과를 반환한다.
​
관련성은 사용자의 위치, 언어, 기기(데스크톱 or 핸드폰)와 같은 여러 정보를 따셔 결정된다
​

---

## SEO 최적화 하기

### title tag

​
title tag는 브라우저의 제목 표시줄이나 페이지 탭에 표시 되고 페이지 내에는 표시 되지 않는다.
​
title tag는 텍스트로만 구성 되어야하고 동적으로도 생성 가능하다.
​
title tag를 작성할때는 해당 페이지를 잘 나타낼수 있는 키워드를 골라야한다.
​

### meta 태그 사용

​
meta tag는 페이지의 메타 데이터와 여러 설정들을 할 수 있는 태그이다. (head tag 안에서 사용 가능하다)
​
간단하게 사용하는 방법을 보여주자면
​

```html
<head>
  <meta charset="UTF-8" />
  <!-- 인코딩 방식 설정 -->

  <meta name="keyword" content="vlog, html, css, js" />
  <!-- 검색 키워드 설정 -->

  <meta name="description" content="vlog 입니다" />
  <!-- 페이지 설명 -->

  <meta name="author" content="gaoooon" />
  <!-- 작성자 설명 -->
</head>
```

### 캐노니컬 태그

캐노니컬 태그는 사이트 내 URL 주소는 다르지만 동일한 내용의 종복된 페이지가 있을 떄 페이지에 코드를 삽입하여 검색 엔진에 대표가 되는 URL 주소를 알려주는 역할을 한다.

URL 뒤에 query나 hash가 붙어 URL이 여러개가 되는 경우, 서브 도메인을 다르게 설정해 URL이 여러개가 되는 경우

```html
<head>
  <link rel="canonical" href="https://www.web.com" />
</head>
```

### 반응형 웹

```html
<head>
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
</head>
```

해당 태그를 사용해 모바일 친화적이라는것을 검색엔진에 알린다.

물론 알리기전에 잘 만들어진 반응형 웹이 있어야 된다.

### 시맨틱 태그 사용

시맨틱 태그를 사용하면 크롤러가 메인 콘텐츠, html의 구조를 분석하는데 도움이 되어 페이지의 의도를 정확하게 전달할수 있어 최적화가 가능하다.

### https

https는 http의 암호화된 버전여서 구글에서 사용하기를 권장한다.

### URL

단순한 URL 구조를 유지하는것이 좋다고 한다.

권장하지 않는 URL 구조

- ASCII가 아닌 문자를 사용하는 경우 (https://www.example.com/نعناع)
- 너무 긴 ID 숫자를 사용하는 경우 (https://www.example.com/index.php?id_sezione=360&sid=3a5ebc944f41daa6f849f730f1)
- 밑줄(\_)이 사용된 경우 (https://www.example.com/summer_clothing/filter?color_profile=dark_grey)
- 단어가 통합된 경우 (https://www.example.com/greendress)
