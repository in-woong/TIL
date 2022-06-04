# 리액트의 Lifecycle API

- Mount : 컴포넌트가 브라우저 상에 나타날 때 (componentDidMount)
- Update : 컴포넌트의 props나 state가 업데이트 될 때(componenetDidUpdate)
- Unmount : 컴포넌트가 브라우저 상에서 사라질 때(componenetWillUnmount)

# JSX(Javascript XML)

- 자바스크립트에 XML을 추가한 것 (eXtensible Markup Language)
- 공식적인 자바스크립트 문법은 아님

- 하나의 파일에서 자바스크립트와 HTML을 동시에 작성할 수 있어 편리함

# React Hooks란?

- class Componenet의 불편함을 해결하기 위해 Functional Componenet를 사용하는 리액트 훅이 등장
- Functional Componenet에서 state를 가질 수 있게 해줌
- 리액트 훅으로 함수형 컴포넌트에서도 클래스형 컴포넌트의 작업들을 할 수 있게 됨

# 클래스형 컴포넌트와 함수형 컴포넌트의 차이점

## 클래스형 컴포넌트

- componenet를 상속받음(extends Component)
- render()함수가 필요
- state와 생명주기 함수들을 사용할 수 있다.(State를 컴포넌트 내에서 구현하기 때문에 복잡한 UI 로직을 갖고 있음)
- constructor, this, binding 등 지켜야 할 규칙이 많아 코드가 길고 복잡함.

## 함수형 컴포넌트

- state를 사용하지 않고 props를 통해 데이터를 받아 UI에 뿌려줌

# Redux란?

- 상태 관리를 도와주는 라이브러리

- props를 사용하지 않고도 store에서 상태를 꺼내 사용할 수 있음
- 주로 로그인 후 유저의 인증정보를 유지하기 위해 사용

# state와 props의 차이

- 데이터를 처리하기 위해 사용한다.
- props는 부모 컴포넌트에서 상속 받은 데이터 이며, props는 직접 수징이 불가하다.
- state는 컴포넌트에서 내부에서 생성되고 값 변경이 가능
