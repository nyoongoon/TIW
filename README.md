# TIW
Today I Worked

# 210929
- focusout과 alert이 함께 처리되어 무한루프를 발생 -> 비동기 문제 

# 210930 
- button sumbit이 여러번 클릭되면 여러 번 post를 보내 db 데이터를 계속 생성. -> 버튼 한번만 클릭가능
- 주문 결과 페이지에서 새로고침하면 db 데이터가 또 생성됨. -> 주문-처리&결과 에서 -> 주문-처리-결과로 나눠서 작업. 

# 211001
- html페이지가 교차되서 출력되는 파일 발견. 이유 찾아보기
![html body](https://t1.daumcdn.net/cfile/tistory/261BFE435539390B1B)
-> body 에서 출력되는 순서가 있다. \<header\> 다음에 \<nav\>
- what is iframe? 
- 처리과 결과출력 페이지를 구분하기 위해 iframe이 닫히면 리다이렉트 하는 법을 찾는 중..
- iframe에 대한 접근권한이 없어서, 1. 입력&결제 -> 2.DB삽입&라다이렉트 -> 3. 결과 출력으로 작업해보기
