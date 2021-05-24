# TODAY I LEARN
매일 배운것을 기록하는 일지
## 배운 개념 List
### SCSS : Sassy CSS(멋진 CSS)
- 반복문 사용법: 일지 20210504참조
- SASS : Syntactically Awesome Style Sheets (문법적으로 짱 멋진 스타일시트). scss가 sass의 파생문법.
#### 용어 
- mixin : 객체 지향 프로그래밍 언어에서 믹스인은 다른 클래스의 부모클래스가 되지 않으면서 다른 클래스에서 사용할 수 있는 메서드를 포함하는 클래스
### 알고리즘
- Knuth Shuffle 알고리즘 : Fisher-Yates shuffle 알고리즘에서 한단계 발전. 피셔 예이츠는 임시 리스트에 하나씩 랜덤으로 뽑아가며 섞었으나 크누쓰 알고리즘은 섞으려는 리스트 내에서 치환해가면서 섞음. 남은 element를 셀 필요가 없고 임시리스트가 필요없다는 장점이 있음.
### Javascript
- DOM animation : DOM을 자바스크립트로 조작해서 애니메이션 효과 주기 [20210518](./20210518.md)
- async  
  - 비동기처리가 끝날때까지 기다리는 방법 [20210519](./20210519.md). 
  - 버튼 이벤트를 받을때까지 대기하는 방법 [20210520](./20210520.md).
- arguments : 함수에 전달된 인자 객체 [20210524](./20210524.md).
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
이유1.하나의 이벤트에 여러 핸들러를 연결할 수 있다. \
2.캡처링과 버블링을 지원한다. \
3.3.html외의 모든 DOM 요소(HTML, XML, SVG)에 대해 사용할 수 있다. \
캡처링과 버블링은 다음에 공부 \
\
이벤트 리스너의 콜백함수의 사용법 node.addEventListener("click", 함수명). \
**함수명 대신 함수()를 쓰면 함수가 실행돼버리고 리턴값이 콜백함수로 등록되는것 같다.** \
콜백 함수에 인자를 넘겨줘야 할 경우 node.addEventListener("click", function(e){ 함수(arg1, arg2, ...) }) 익명함수로 처리. \
콜백함수는 다음에 제대로 공부해야함.

### 20210504
난이도 변경기능 추가 \
재귀적 탐색 추가(주변에 지뢰가 없는 빈칸일 경우 재귀적으로 주변 칸을 탐색) \
승리조건 추가(전체 칸수-지뢰갯수만큼 탐색에 성공하면 승리) \
\
scss반복문 사용 \
@for $i from 1 through 8 { \
    .cell_#{$i}{ \
        color: hsl(360/8*$i, 100%, 50%); \
    } \
#{}:인터폴레이션. 정확한 의미는 모름. 변수값을 평문 텍스트로 바꿔주는 기능 같음. \
cell값에 따라 cell_1~cell_8까지 클래스를 나누는데 scss반복문을 사용하여 글자색을 변경. 편의상 hsv컬러에서 360도 회전을 8로 나눈 45씩 회전 \
\
border-color값을 따로 지정하지 않으면 color값을 따라간다. \

html요소를 중앙정렬 하려면 margin:auto 사용 display:block인 상태여야하는듯.

### 20210506
지뢰찾기를 제작하며 이해가 안됐던 부분 보충 정리 \

html요소.innertext 변경과 alert이 붙어있을 경우 순서에 상관없이 alert이 먼저 실행되는 문제에 관하여 \
해당 작업들은 web api를 통해서 이뤄지고 비동기 방식으로 처리. html.innerText가 코드상 먼저 오더라도 webAPI를 호출한 뒤 응답을 기다리지 않고 다음 코드 진행. \
브라우저에서 alert을 호출 받으면 다른 작업들 중지. html안의 요소를 바꾸는 작업중에 중지된 것으로 예상됨. \
**결론. alert은 다른 작업을 중단해야할 정도로 긴급한 상황 아니면 프로그램에 쓰지 말자.**

콜백에 인자 전달하는 방법에 대하여 \
addEventListener("click", callback(a)) <-이런 식으로 썼을 때 클릭 이벤트에 대해 callback함수가 등록되는것이 아닌 callback(a)를 실행한 **리턴값**이 콜백함수로 등록됨. \
javascript의 콜백 함수는 다음과 같음. \
function asd(arg, callback) { \
    console.log(arg); \
    callback(); \
} \
function callbackfunc(){ \
    console.log('callback'); \
} \
asd('hello world!', callbackfunc); \
이벤트 등록함수에서 콜백에 인자를 직접 전달하고 싶었는데 달리 방법이 없음. 익명함수로 콜백 함수를 다시 호출하거나 전역변수를 사용. \

javascript에서의 this \
https://www.w3schools.com/js/js_this.asp \
메소드의 경우 오너 객체 \
단독으로 쓰일 경우 글로벌 객체 (브라우저:window, nodejs:global) \
함수의 경우 글로벌 객체 \
strict mode의 함수의 경우 undefined \
이벤트의 경우 이벤트가 발생한 element \
call, apply메스드로 this 지정 가능 \
메소드와 함수의 차이: 전역에서 정의되면 함수. 객체 내에서 정의되면 메소드.

### 20100508
텍사스 홀덤 제작 시작.
자바스크립트를 객체지향적으로 짤 예정.
카드 덱 클래스 코딩.
카드리스트와 뽑은 카드리스트와 카드뽑기, 섞기, 초기화 메소드로 구성.
카드는 0~51까지의 숫자로 구분. 각 무늬마다 13장의 카드가 있으므로 카드id/13=무늬, id%13=숫자
셔플 알고리즘으로 기존에 쓰던 fisher yates shuffle 대신 knuth shuffle을 사용. 메모리 재할당이 필요없다는 점이 장점.
**셔플이 정말로 랜덤한건지 검증하는 방법이 필요.**

### 20100510
7장의 카드로 패를 판별하는 코딩 진행중.
스트레이트 판별 함수를 만듦. 각 패별로 따로 판별하면 반복적으로 순회하게 되는 부분이 만족스럽지 못하지만 딱히 방법이 떠오르지 않음. 프로그램에 크게 지장은 없을듯 하여 일단 진행.
