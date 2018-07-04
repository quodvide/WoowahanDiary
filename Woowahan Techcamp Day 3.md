# Woowahan Techcamp Day 3

오늘도 오전에 오자마자(9:00 ~ 9:15) Daily Meeting을 진행했다. 나온 이야기는 다음과 같다. 

#### 어제의 미션과 페어 프로그래밍에 대한 느낀 점 

**좋았던 점**

- 단축키와 상대방의 생각하는 방법을 배울 수 있을 것 같다 
- 원래 적당히 하고 끝낼 것을 게속 하니까 어려웠다 
- 돌아가게만 하는게 아니라 정답이 없는 설계에 대한 문제라 새로웠고 힘들었다

**아쉬웠던 점**

- 빡세기때문에 쉬는시간도 잘 지켜야될거같다 페어프로그래밍시 -> 50분코딩, 10분쉬는시간 갖자

**발견된 문제와 해결방법**

- 문제가 발견되지 않았고 우리조가 자유롭게 소통할 수 있는 분위기라 좋은것같다

**오늘 하루할 일** - 내일 있을 우동소를위해 서로를 알아가며 배우자!


## 포비님 강의(9:30 ~ 10:50)

**Test Driven Development(TDD)**

- TDD = TFD(Test-First Development) + 리팩토링
- TDD 장점 
    - 디버깅 시간을 줄여준다 
    - 동작하는 문서 역할을 한다(API에 대한 사용법을 알려줄수있다) 
    - 변화에 대한 두려움을 줄여준다. 
- TDD의 Cycle = Test fails -> Test passes -> Refactor 반복 
- TDD 원칙
    - 원칙1 - 실패하는 단위 테스트를 작성할 때까지 프로덕션 코드(Production code)를 작성하지 않는다.
    - 원칙2 - 컴파일은 실패하지 않으면서 실행이 실패하는 정도로만 단위 테스트를 작성한다. 
    - 원칙3 - 현재 실패하는 테스트를 통과할 정도로만 실제 코드를 작성한다 

- ex) 자동차 TDD - 요구사항을 보고 큰 단위로 to-do-list를 만든다 그후 todo, done으로 구분하여 완성한 목록관리, 그후 우선순위에 따라 개발순서
    1. 컴마 구분으로 이름을 받아 자동차 생성 
        - List<Car> cars = A.create(“honux,crong,pobi”);
        - assertThat(cars).contains(new Car(“hounx”)).contains(new Car(“crong”)).contains(new Car(“pobi”)); 
        - equals, hashCode, toString를 override해야함!! 
    		- equals, hashcode는 Acar.equals(Bcar)과 같은 객체들간의 동등성 비교를 위한 메소드이다. 기본적으로 override전 equals함수는 
    		- public boolean equals(Object obj) { return (this == obj); }
    		- 와 같이 되어있어서 equals를 알맞게 Override 하지않으면 같은 객체가 아니라면 무조건 false를 반환하게 되어 올바른 결과를 얻을 수 없다. 또한 equals메소드를 오버라이드 했다면 hashCode메소드도 오버라이드 해주어야 하는데 Acar.equals(Bcar)이 참이라면 Acar.hashCode() == Bcar.hashCode()라는 조건이 성립해야하기 때문이다.   
    
        - 입력값에 대한 유효성 검증을 까먹지말자
    - 경주가 끝난 자동차에서 우승 자동차를 추출 
        - Arrays.asList(Object, Object,,,,) 로 객체리스트 생성
        - 생성자 중복시 인자가 많은쪽에서 모두 구현하고 인자가 적은쪽에서는 많은쪽을 불러오면 중복제거에 도움된다.  
        - 객체지향에서는 객체끼리 비교등, 객체에 대한 프로그래밍을 한다 => 객체가 일을하게하라. 물어보지말고 말을하게하라. 그렇지않으면 절차지향이된다 
        - car.getPosition() == maxPosition     =>     car.isMaxPosition(maxPosition) 으로 
        - MVC로 만들려고 노력하여서 Model부분에 단위테스트를 적극 활용하라
    - 우승 자동차에서 화면에 표시할 문자열 생성 
    - 자동차 위치에 따라 화면에 표시한 문자열 생성 
    - 이름 입력 값이 null 또는 빈 문자열인 경우 
- 단축키들 
	- Option Command m => Method로 Extract
	- shift Fn F6 (두번)=> Rename 리팩토링
	- ALT Commend v => 로컬변수로 빼준다

## 오늘의 팁

### Java8의 중요한 특징인 Stream
#### Stream

- Stream은 간단한 업무를, 하지만 아주 많은 양을 처리할때 손쉽게 할 수 있는 고마운 존재입니다. 
- 따라서 익혀둔다면 좋은 프로그래밍 도우미가 될 것이라고 생각합니다. 

 > **"Stream은 간단하지만 양은 아주 많은 업무를 병렬로 손쉽게 처리해준다."**
 
- list.stream().filter(i -> i > 10).mapToInt(i -> i).sum();
- 이와 같은 형태로 사용이 가능하고 직관적으로도 list의 요소중 10보다 큰 요소의 합을 구하려 한다는 것을 손쉽게 유추 할 수 있습니다. 

1. map메소드 - Stream의 타입을 바꾸어주는 메소드 
2. filter메소드 - 조건을 충족하는 새로운 Stream 생성
3. mapToInt메소드 - Stream의 타입을 인자에 있는 int값으로 바꾸어주는 메소드 
4. max메소드 - Stream의 값들중 최대값을 반환 
5. average메소드 - Stream의 값들의 평균을 반환 

- 이외의 자세한 내용은 다음내용에 추가하겠습니다.
