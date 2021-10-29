# TIW
Today I Worked

# 210929
- focusout과 alert이 함께 처리되어 무한루프를 발생 -> 비동기 문제 

# 210930 
- button sumbit이 여러번 클릭되면 여러 번 post를 보내 db 데이터를 계속 생성. -> 버튼 한번만 클릭가능
- 주문 결과 페이지에서 새로고침하면 db 데이터가 또 생성됨. -> 주문-처리&결과 에서 -> 주문-처리-결과로 나눠서 작업. 

# 211001
- html페이지가 교차되서 출력되는 파일 발견. 이유 찾아보기
-> body 에서 출력되는 순서가 있다. \<header\> 다음에 \<nav\>
- what is iframe? 
- 처리과 결과출력 페이지를 구분하기 위해 iframe이 닫히면 리다이렉트 하는 법을 찾는 중..
- iframe에 대한 접근권한이 없어서, 1. 입력&결제 -> 2.DB삽입&라다이렉트 -> 3. 결과 출력으로 작업해보기

# 211005
- ajax로 서버에 post로 데이터를 전송하려고 했음. <br/>
-> 서버에서 데이터를 받지 못하고 있었음. -> 이유는 post로 데이터를 전송하고 location.href=""통해서 리다이렉트를 했는데, 리다이렉트할 때 get을 전송하고 이동. -> ajax는 싱글페이지에서 데이터를 바꿔주기 위한 용도이므로 데이터를 전해주면서 페이지를 넘기는 경우엔 form을 사용하는게 좋다. 
- 입력 -> &DB처리&결제&결과 에서
- 입력 -> DB처리 -> 결제 & 결과로 페이지 구분하여, 결과 페이지에서 새로고침해도 DB가 수정되지 않게 작업. 결제 페이지와 결과 페이지를 구분하고 싶었으나, 결제 페이지가 iframe으로 삽입되어 컨트롤 할 수 없었다.

# 211013
- aquanplay api로 북마크 기능 추가. 

# 211029
- CORS 이슈가 있었음
- I finally found the answer, in this RFC about CORS-RFC1918 from a Chrome-team member. To sum it up, Chrome has implemented CORS-RFC1918, which prevents public network resources from requesting private-network resources - unless the public-network resource is secure (HTTPS) and the private-network resource provides appropriate (yet-undefined) CORS headers
- There's also a Chrome flag you can change to disable the new behavior for now: chrome://flags/#block-insecure-private-network-requests
- https가 아니거나 올바른 cors헤더가 아닐 경우, 퍼블릭 네트웍이 프라이빗 네트웍에 요청을 보내는 것을 크롬이 막는다.. 
