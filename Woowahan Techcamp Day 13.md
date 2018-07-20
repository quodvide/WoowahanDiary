# Woowahan Techcamp Day 13

## Daily Meeting (9:00 ~ 9:10)

- ATDD로 들어오고 난 후 난이도가 확 올라간것 같다. 코드파악이 힘들었다. 
- 내가 지금 잘 소화하고 있는가에 대해 의문이 든다.
- 스프링에 대해서 전체적인 큰 흐름을 찾지는 못하는거 같아서 어려움이 있다. 

## 크롱님 강의 (9:10 ~ 10:00) 

### 브라우저 동작방식 

- User Interface : 뒤로가기 버튼, 주소표시창 등의 브라우저의 UI이다. 
- Browser Engine : Rendering Engine과 UI Interface사이의 동작을 제어
- Rendering Engine : HTML을 parsing해서 DOM Tree를 만들고, Render Tree를 만들고 CSS를 더해서 Layout을 만들고 그것을 이용해 painting을 해주는엔진. 브라우저마다 다르다.
	- 파이어폭스는 모질라에서 직접 만든 게코(Gecko)엔진을 사용하고, 사파리와 크롬은 웹킷(Webkit)엔진을 사용한다. 동작방식이 조금씩 다르다. 
	- Rendering Engine의 동작방식은 다음과 같다. 
		- HTML을 파싱해서 DOM Tree를 만든다. 
		- CSS를 해석하여 Render Tree를 만든다. 
		- Render Tree를 알맞은 위치에 배치시킨다.
		- Render Tree를 그려서 사용자에게 화면을 보여준다. 
- Network : HTTP요청과 같은 네트워크 호출에 사용된다. 플랫폼 독립적인 인터페이스이고 각 플랫폼 하부에서 실행된다.
- Javascript Interpreter : 자바스크립트의 해석을 담당한다. 
- UI Backend : 콤보박스와 창같은 기본적인 장치를 그린다. 플랫폼에서 명시하지 않은 일반적인 인터페이스로써, OS 사용자 인터페이스 체계를 사용한다. 
- Data Persistance : 자료를 저장하는 계층이다. 쿠키와 같은 자원은 하드디스크에 저장할 필요가 있다. HTML5 명세에는 브라우저가 지원하는 '웹 데이터 베이스'가 정의되어 있다.

### HTML과 CSS

- HTML문서의 모든 엘리먼트는 모두 Box Model이다. 
- 모든 엘리먼트 공통적으로 width, height을 가지는 박스이며, padding, border, margin 값을 가지고있다. 이 속성들이 모두 모여 Box Model을 이룬다. 
- 그래서 특정 엘리먼트의 가로넓이는 정확하게 말하면 margin-right + border-right + padding-right + width + padding-left + border-left + margin-left의 값이다.
- 엘리먼트마다 default값 속성이 있을 수 있고, CSS 혹은 style 태그로 Override가 가능하다. 
- 엘리먼트간의 배치(Layout)과 관련된 속성은 다음과 같다. 
	- Display : 요소의 표현 방식을 결정하는 속성
		- Block : 기본적으로 width:100%로 적용이 되고 위에서 아래로 박스가 쌓이는 방식
		- Inline : Block과 달리 자동 줄바꿈이 되지않고 width, height을 지정할수 없다.
		- Inline-block : Inline처럼 자동 줄바꿈이 되지 않지만, Block처럼 width, height을 정할 수 있다. 
	- Position : 박스의 위치를 지정하는 여러가지 속성
		- Static(default) : 기본값. 자동적으로 배치되며, 위치를 지정할 수 없다.
		- Relative : 기본값으로 배치되는 위치를 기준으로 위치를 정할 수 있다. 
		- Absolute : Static이 아닌 상위의 엘리먼트를 기준으로 위치를 정할수 있다. 
		- Fixed : 스크롤과 상관없이 항상 문서의 좌측상단을 기준으로 위치 시킨다.
	- Float : 떠다니는 것처럼 자연스럽게 흐르듯 배치되는 속성
		- Left : 왼쪽으로 흐름
		- Right : 오른쪽으로 흐름

## 코딩(10:00 ~ 17:30)