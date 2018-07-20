# Woowahan Techcamp Day 15

## Daily Meeting (9:00 ~ 9:20)

- A : 장한평역에 곱창집을 갔는데 사람이 너무 많아서 테이크아웃해서 집에서 먹었다. 맛있었다.
- B : 곱창은 그럭저럭이었다. 
- C : 곱창은 그럭저럭이었다. 부추맛.? 
- D : 어제 데이터베이스를 하루만에 훑어서 조금 시간이 부족했던것같다. 아쉬웠다.  

## 커밋로그 팀컨벤션 정하기 (9:20 ~ 9:40)

### 7조 커밋로그 컨벤션

- 한글로 커밋로그를 남긴다.
- 제목은 명령조 (수정, 추가, 삭제, 구현 etc … 습니다. (x)) 
- 제목과 본문을 빈행으로 분리
- 제목 끝에 마침표는 넣지않는다.
- 본문에서 각 기능에 대한 간단한 설명( -, > 표시로 구분)

예시

>미로그인 회원이 글 작성할 수 있었던 버그 수정

> \- 세션 검사 추가  
> \> 어쩌고저쩌고해서 이렇게저렇게 하는 방법으로 추가했습니다.  
> \- 로그인 검사  
> \> 어쩌고저쩌고해서 이렇게저렇게 하는 방법으로 추가했습니다.  

## 크롱님 CSS리뷰 (9:40 ~ 10:10) 

- 왠만하면 id보다는 Class로 만드는 것이 낫다. 
- id는 unique한 요소를 지정하여 JS로 컨트롤하는 경우가 많다. 
- list에는 목록에 필요한 요소들만 넣는 식으로 의미에 맞게 짜라. 
- classname등의 이름에 알맞은 의미를 부여하여 만들어라. 
- 가운데 정렬을 할때 margin: 0 auto 명령으로 해주면 좋다. 또한 width를 꼭 지정해야한다.

## 크롱님 JavaScript (10:20 ~ 17:00) 


### 여러가지 문법

- Object, Map, Set
	- Object : 가장 기본적인 객체이고, key값을 모두 String으로 저장한다. 일반적으로 각각 값들에 대해 다른 로직을 수행하는 상황일때 자주 쓰인다.
	- Map : Object와 다르게 Map은 key값에 아무값이나 올 수 있다. 일반적으로 key, value들의 타입이 각각 같을때 map을 쓰는것이 좋다.
	- Set : 값들의 집합이다. 그러나 배열과 달리 중복을 허용하지 않는다. 삽입된 순서대로 반복처리 할수있다(iterable). 배열과 상호변환 할 수 있다. 
		- Array.from(Set)으로 Array로변환, new Set(Array)로 Set으로 변환.
		- 그러나 Array -> Set에서는 중복을 제거하기 때문에 값이 사라질수도 있다. 

- foreach
	- Foreach 메소드는 **배열** 요소마다 한 번씩 제공한 **함수**를 실행한다.
	- arr.forEach(function(v,i,o) {}) 처럼 사용할 수 있고, 여기서 v, i, o 와 같이 세개까지 인자가 올 수 있는데 이름과 상관없이 순서대로 value, index, object를 의미하게 된다.
- for ... of	...
	-  **반복가능한 객체**들(Array, Map, Set, String등)에 대해서 반복하고 각 개별 속성값에 대해 실행되는 문이 있는 사용자 정의 반복 후크를 호출하는 루프를 생성한다.
	-  for (let element of arr) { 반복 후크 }
	-  for (let [key, value] of map) { 반복 후크 } 
	-  처럼 사용이 가능하다. 
- for ... in ...
	- 객체의 **열거형 속성**들을 모두 적절한 순서에 의해 반복하게 한다.(Array, Object..) 
	- for (let index in arr) { }로 하면 배열의 인덱스를 활용 할 수 있다. 
	- for (let key in object) { }로 하면 오브젝트의 키를 활용 할 수 있다. 
	- Map, Set등은 사용할 수 없다. 
- map
	- map()은 배열 내의 모든 요소 각각에 대하여 제공된 함수(callback)를 호출하고, 그 결과를 모아서 새로운 배열을 반환한다.
	- arr.map(x => x*2) => arr의 모든 요소를 2배로 만들어 배열로 반환 
	- 혹은 이런식으로 메소드를 삽입하거나 불러올수 있다. 
		- arr.map(x => { if(x < 10) ...... });
		- arr.map(x => isPositive(x)); 
- filter
	- filter는 제공된 함수로 구현된 테스트를 통과하는 모든 요소가 있는 새로운 배열을 만든다.
	- words.filter(word => word.length > 6) 처럼 사용할 수 있고, 
	- words.filter(word => hasEorNot(word)) 처럼 메소드가 들어가도 된다. 
- reduce
	- reduce는 왼쪽에서 오른쪽으로 이동하며 배열의 각 요소마다 누적 계산값과 함께 함수를 적용해 하나의 값으로 줄인다.
	- reduce(callback[, initialValue])로 사용하며, 보이는 것 처럼 초기값(initialValue)를 주어도 되고, 주지 않아도 된다. 그러나 초기값이 없는경우 빈 배열이나 맵이 올때 TypeError가 생기기때문에 초기값이 주는것이 안전하다. 
	- 또한 callback 함수는 최대 4개의 인자를 가질수 있으며, 순서대로 accumulator, currentValue, currentIndex, arr 이다. 필요할경우 모두를 인자로 가지는 callback함수를 만들어 사용하면 된다. 
	- reduce(callback(prev, curr) => { return prev + curr; }) 처럼 사용할 수 있으며, 배열의 sum을 구한다.

### 여러가지 팁들

- JavaScript는 Java가 아니다.
- JavaScript는 동적으로 변하는 컨텐츠와 웹페이지를 만드는 것부터 시작했지만 현재 서버사이드 까지 쓰이고 있다. 
- HTML, CSS로 구조와 스타일등을 정해두고, 자바스크립트 엔진으로 자바스크립트가 실행된다.
- JS는 타입이 실행타이밍에 결정된다.
- ES(ECMA Script)에따라 문법이 결정된다. 
- 클래스 선언없이 객체를 표현해서 만들수있다. 
- 변수등을 선언 후 기본적으로 아무설정없거나 실행을 안한다면 undefined
- 최대한 성공시키려는 경향이 있다. 타입캐스팅을 왠만해선 되게 하려고함 -> 문자열 + 숫자도 가능, 문자열 + undefined도 가능 
- Override 개념은 없다. 두번째 선언된것이 첫번째 것을 덮어씌운다.
- false로 취급되는 값들 : false, “”, 0, NaN, null undefined 
- Compatibility(브라우저, 버전..) 를 항상 보고 써야한다. 
- 자기 스코프 안에 찾고자하는 변수가없으면 위로 올라간다.(Scope Chaining) 없으면 에러난다.
- New 키워드도 잇지만 별 이득이없어서 안쓴다
- return; 은 없다. 자동으로 undefined반환  


## Team Evaluation (17:00 ~ 17:30)