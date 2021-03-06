# Woowahan Techcamp Day 2

먼저 아침에 15분간 조끼리 DailyMeeting을 진행했다. 그 과정에서 나온 조 규칙은 다음과 같다. 

 1. 페어를 바꾸기전에 페어간에 코드리뷰 할 것
 2. 전날 공부한 것정리(공통) + 약간의 팁(돌아가면서) 블로그(or 깃헙)에 정리
 3. 지각하면 커피 쏘기(18층 배민카페)
 4. 2주에 한번 회식(금요일)  
    

## 포비님 강의(9:30 ~ 11:30) 

 1. 코딩 컨벤션(Coding Convention) 
	 - 가로 format 맞추기 : 120자 정도로 행 길이를 제한
	 - Naming Convention
	    - Java에서는 CamelCase. 
	    - Class는 대문자시작 ex) CalculateSystem, CarWash
	    - Method, Variable는 소문자시작 ex) countingStars, stringParse
	    - Package는 왠만하면 단어로 만들자. 그래서 StringParser보다 string.parser이런식의 구조로.
	    - Naming은 아주 중요하다. 무시하면안되고 많은 시간을 들여야함 
	- 문단을 나눈다는 의미는 다른 컨텍스트라는 의미기 때문에 이걸 메소드로 나누는 단위가 될 수도 있다.
	- Method 
	    - 작게 만들어라(조금 더 비 효율적이 되어도 상관없다) 
	    - 한가지만 해라 
	    - 서술적인 이름을 사용하라(길어도 괜찮다) 
	    - 함수 인수(이상적인 갯수는 0개, 다음은 1개, 다음은2개, 3개부터는 피하라. 4개는 절대 사용하지마라)
	        - 혹시 2,3개이상의 인수가 필요하다면 독자적인 클래스를 생성 할 수 있는지 검토해 본다
	    - Side effect를 만들지 마라 
	    - 반복하지 마라. 중복은 SW의 악의 근원이다. 

2. 테스트하기 쉬운 코드란? 
	- 테스트 하기 어렵다 => 설계가 잘못되었을 수도 있다는 힌트 
	- 테스트 하기 어렵다 => 테스트 하기 쉬운 코드로 만들어야한다.
	- 불확실성(non-deterministric) - 외부 세상에서 값을 읽어오는 것과 관련
	    - 랜덤수, 전역변수, 로컬머신에 존재하는 파일내용, DB특정 레코드, HTTP - get등 ..
	- 부수효과(side-effect) - 외부 세상에 값을 기록하는 것과 관련
	    - 전역변수, 로컬 머신에 존재하는 파일 내용, DB특정 레코드, HTTP - POST등 
	- 순수함수 : 불확실성과 부수효과가 없는 함수 => 테스트하기 쉬운 코드 
	- 반환값이 있는 경우가 테스트 하기 쉬운 코드 
	- 최대한 테스트하기 쉬운코드, 어려운 코드를 분리하여서 쉬운코드를 테스트하라. 
	- 테스트를 하는 과정을 설계에 대한 힌트로 생각하라 


## 미션활동(11:30 ~ 17:50)