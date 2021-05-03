# TODAY I LEARN
매일 배운것을 기록하는 일지
## 배운 개념 List
### SCSS : Sassy CSS(멋진 CSS)
### SASS : Syntactically Awesome Style Sheets (문법적으로 짱 멋진 스타일시트)
### mixin : 객체 지향 프로그래밍 언어에서 믹스인은 다른 클래스의 부모클래스가 되지 않으면서 다른 클래스에서 사용할 수 있는 메서드를 포함하는 클래스
## 일지
### 20210430
지뢰찾기 예제를 찾아 분석함. 주소:https://wsss.tistory.com/1458\
html5면 canvas를 사용하는 방식만 생각했었는데 구조가 다름.\
html div에 자식 div요소를 지뢰찾기 판 크기만큼 javascript로 생성하고 scss를 이용해 게임화면처럼 꾸밈.\
\
scss에 대해 간략히 공부. https://velog.io/@jch9537/CSS-SCSS-SASS\
약간의 약자의 차이가 있지만 scss나 sass는 비슷한 것이다.(scss가 sass의 3버전에서 정의된 구문 https://heropy.blog/2018/01/31/sass/)\
scss는 css로 완전히 호환 되지만 sass는 아닐 수 있다. https://designmeme.github.io/ko/blog/write-sass-with-scss/ \
scss, sass는 변수를 사용할 수 있어서 유지관리에 장점이 있다. eg. 홈페이지 테마를 바꿀 때 배경색 등을 일일이 바꾸지 않고 변수만 바꿀 수 있음.\
브라우저는 결국 css를 요구하기 때문에 컴파일 과정을 거쳐 css로 변환시켜야 한다.

### 20210503
지뢰찾기를 html5로 직접 만들어보기로 함.\
예제와 달리 게임판은 table을 쓰기로함. 행과 열을 다루기 더 적합함.\
이벤트는 addEventListener함수로 처리하는게 좋음. \
이유1.하나의 이벤트에 여러 핸들러를 연결할 수 있다.  2.캡처링과 버블링을 지원한다.  3.html외의 모든 DOM 요소(HTML, XML, SVG)에 대해 사용할 수 있다. \
캡처링과 버블링은 다음에 공부

이벤트 리스너의 콜백함수의 사용법 node.addEventListener("click", 함수명). **함수명 대신 함수()를 쓰면 함수가 실행돼버리고 리턴값이 콜백함수로 등록되는것 같다.** 
콜백 함수에 인자를 넘겨줘야 할 경우 node.addEventListener("click", function(e){ 함수(arg1, arg2, ...) }) 익명함수로 처리. 
콜백함수는 다음에 제대로 공부해야함. 
