## `CORS ERROR`

#### 내가 최근에 open API를 사용하다가 겪은 일이다

#### postman이나 다른 곳에서는 API가 잘 받아오지다가 내가 만든 페이지에서는 CORS 에러가 뜨는 것이다

#### 왜 그런 것일까?

## `CORS란?`

#### CORS란 Cross-Origin Resource Sharing으로 교차 오리진(출처) 리소스 공유이다

#### CORS를 알기전 sop를 먼저 알아야 쉽게 이해 할 수 있다

#### SOP는 Same-origin-policy로 동일 오리진 정책으로 같은 출처끼리만 리소스를 공유할수 있는 것이다

#### 왜 같은 origin끼리만 가능한가 그이유는 예를들어 악성사이트에서 요청을 보낸것을 그대로 정보를 준다면 보안에 취약해 지기 때문이다

#### 다시 돌아와서 CORS가 생긴 이유는 웹이 발달 하면서 오리진이 달라도 서로 리소스 교환이 필요한 상황들이 많이 생겨 CORS가 생겨난 것이다

## `결론?`

#### CORS error는 origin이 달라서 예외 처리를 해줘야 하는데 하지 않으면 브라우저 단에서는 origin이 달라서 리소스를 공유할수 없다고 error가 생기는 것이다
