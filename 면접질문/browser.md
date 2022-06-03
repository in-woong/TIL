# 브라우저의 렌더링 과정

- user Interface : 사용자와 상호작용하는 인터페이스 (주소 표시줄, 이전/다음/새로고침 등)
- Browser Engine : User Interface 와 Rendering Engine을 연결

- Rendering Engine : HTML과 CSS를 파싱하여 웹 페이지를 표시

- Networking
- UIBackend
- Data Persistence: localStorage와 Cookie와 같은 데이터를 저장

## Critical Rendering Path

1. 유저가 접속하고자 하는 URL을 입력
2. 브라우저에서 사용자가 요청한 웹페이지를 파싱
3. HTML과 CSS를 DOM
4. 화면에 표시되어야 하는 정보를 포함하는 트리 (Render Tree)

# FlexBox 란?

- 행 또는 열을 기준으로 웹 요소들을 정렬하는 방식
- 크기가 유동적이어야 하는 상황에서 많이 사용 (화면 크기에 맞춰 화면의 아이템들의 높이와 넓이를 최적의 길이로 맞춰줌)

# CSS애니메이션과 JS애니메이션의 차이점은?

## CSS Animation

- Trasition과 Animation 속성이 존재
- Transition은 hover나 click과 같은 이벤트 트리거에 의해 동작
- 해당 element 의 변화를 일정 기간동안 일어나게 함
- 시작, 정지 반복까지 제어 가능

## JS애니메이션

- setInterval()과 같은 함수를 활용해 element에 변화를 줌

## 차이점

1. CSS 애니메이션은 IE를 잘 지원하지 않아 크로스 브라우징 측면에서 JS애니메이션이 선호됨
2. JS는 style.top, style.left와 같이 요소 하나하나와 동작을 관리해줘야 한다. 따라서 CSS는 css만 관리해주면 되기 때문에 관리가 용이하다. 대신 JS는 세밀한 동작까지 변형을 줄 수가 있다.

# 브라우저 저장소의 차이점 (localStorage, sessionStorage, Cookie)

## localStorage

- 가장 간단하게 key-value저장
- 최대로 저장하는 용량 제한(5~10MB)이 있다.
- 도메인이 같으면 전역적으로 데이터 공유

## sessionStorage

- 브라우저를 종료하면 초기화 (새로고침 제외)
- 게시판의 자동 임시 저장 용도로 자주활용
- 도메인이 같아도 브라우저가 다르면 데이터 공유가 안됨(브라우저 마다 별도의 sessionStorage가 생성됨)

## Cookie

- 데이터 유효 기간을 지정할 수 있음
- 저장할 수 있는 용량이 작은데 그 이유는 서버로 데이터를 전송할 때마다 쿠키 데이터가 담겨서 전송이 되기 때문

# SSR, CSR의 차이점

## SSR

- 페이지 내용을 서버에서 그린 다음 브라우저로 전달
- 페이지를 이동할 때마다 서버에 새로운 페이지를 요청

## CSR

- 페이지 내용을 브라우저에서 그린다.
- react예로, index.js파일만 로드하는 경우 (SPA)
- SEO에 단점이 있음. 웹봇이 크롤링 할때는 웹이 로드되기 전의 빈 상태 코드를 크롤링해 가기 때문이다.

## 차이점

- 화면에 뿌려줄 컨텐츠를 어디서 그려주냐의 차이
- 성능. 아무래도 렌더링된 HTML을 브라우저에 전달하는 SSR이 초기화면 로딩속도가 빠르다. 대신 CSR은 초기 로딩 이후 SSR보다 로딩 속도가 빠름
- SSR은 잦은 서버 요청에 따른 부하가 있을 수 있음.

> 기존에는 페이지를 이동할 때마다 서버에 리소스를 요청하고 화면에 렌더링 하는 방식을 사용,
> 최근에는 브라우저로 반드시 페이지를 전체 로드한 다음, 새로운 페이지 갱신에 필요한 데이터만을 전달받아 페이지를 갱신

# CORS란? 왜발생하는 것? 해결방법?

- Cross-Origin Resource Sharing: 도메인이 다르면 요청을 주고 받을 수 없게 하려는 초기 웹 브라우저의 정책으로 인해 발생한 문제.

- cross-origin 케이스: http, https, 도메인, 포트번호가 다른 경우

## 해결방법

- 프론트의 경우 Request Header에 CORS 관련 옵션 추가 및 서버 개발자에게 CORS 허용 요청
- 프록시 서버를 통한 우회(외부 도메인 서버에 바로 요청하는 것이 아닌 프록시 서버를 통해 외부 서버에 요청한 다음 결과값을 받는 방법)
