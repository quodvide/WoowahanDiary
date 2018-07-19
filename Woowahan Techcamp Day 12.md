# Woowahan Techcamp Day 12

## Daily Meeting (9:00 ~ 9:10)

- ATDD로 들어오고 난 후 난이도가 확 올라간것 같다. 코드파악이 힘들었다. 
- 내가 지금 잘 소화하고 있는가에 대해 의문이 든다.
- 스프링에 대해서 전체적인 큰 흐름을 찾지는 못하는거 같아서 어려움이 있다. 

## 포비님 강의 (9:10 ~ 10:00) 

### 조금 더 행복하게 일 할 수 있는 방법? 

- 포비 : 경험적으로 내 영역만 보는것이 아니라 소프트웨어 전체 영역에 관심을 가지고 일을 할 때 새로운 시야가 생기고, 창의적 접근 방식이 생기면서 즐거웠던것 같다. 대체로 정형화된 프로세스가 있는 곳은 이미 많은 것이 정해져 있고 내 생각을 주장하기 힘들기 때문에 지루함을 느낄 가능성이 높다.

### ATDD 미션 팁
 
- sout대신 log를 써라. 로그레벨 설정이 가능하다. 
- 문자열 합치는것도 성능 많이 잡아먹어서 String.format이나 "{}", target이런식의 사용이 좋다.
- 자신만의 라이브러리를 만들 줄 알아야 한다. 
- 다양한 처리를 모두 컨트롤러에서 하면 기능이 너무 많아져서 보통 userService등의 서비스를 만들어서 사용한다. 
- 즉 서비스는 기능을 조합하는 역할을 한다. 
- 컨트롤러는 사용자의 접점에서 input, output을 결정하는데 transaction까지 담당하면 기능이 너무 많아지기 때문에 서비스와 역할분담을 하는것이 일반적인 방법이다.
- Repository로 데이터를 끌어오고, 데이터 변경시 DB에 적용해주는 기능 등을 담당한다.
- Business로직은 서비스가 담당하면 안된다. Domain객체가 담당하게 해야한다. 
- @Transaction 어노테이션은 따로 save를 하지않아도 변경이 되는것을 추적해서 알아서 저장해준다. 연관된 객체까지 알아서 save해주기 때문에 훨씬 깔끔하게 구현할 수 있다.
- 유효성 체크는 도메인 객체 내에서 해주는것이 가장 좋다. 
- 혹은 HandlerMethodArgumentResolver 인터페이스를 사용하여 @LoginUser와 같은 어노테이션을 직접 만들어서 사용해주는것도 좋은 방법이다.

## 코딩(10:00 ~ 17:30)	