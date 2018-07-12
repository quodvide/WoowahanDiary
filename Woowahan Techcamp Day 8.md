# Woowahan Techcamp Day 8

## 데일리 미팅 (9:00 ~ 9:10)
어제 좋았던 점 

- 현업에서 쓰는 것들을 더 알수있어서 좋았다 
- 짝이 대견했다.
- JH : 짝을보며 자기를 반성했다. (소프트웨어에 대한 진정성이 없는 자신을 ) 

아쉬웠던점

- 페어 바꿀때 구조에 대해서 서로 간단하게라도 이야기했으면 좋겠다. 갑자기 남이 짠 코드로 하게될수도 있으니까

오늘 하루는 ?

- jpa를 마스터하자. 열심히듣자 
- 재밌게 하자.  

## 포비님 강의 (9:10 ~ 10:10)

- @ExceptionHandler = 핸들러 어노테이션. ()의 예외를 처리할수 있다. 예외 발생시 호출  
@ControllerAdvice  
Public class ExceptionAdvice {  
	@ExceptionHandler(Exception.class)
} 이런식으로 사용할수있다. 
- 중복제거에 힘을 많이 써라.  
- 세션도 MockHttpSession 을 사용해서 테스트 할 수있다. 
- 유틸은 단위테스트 하기 쉬우니 왠만하면 하자  
userRepository.findByUserId(userId)  
		.filter(u -> u.matchPassword(password))  
		.orElseThrow(IllegalArgumentException::new);  
이처럼 옵셔널, 람다와 스트림등을 이용하면 더 간결하게 짤수잇다.  
- Jpa를 쓰면 여러개의 쿼리를 나눠서 날린다. 한방쿼리가 좋은게 아니다. 
- 객체관계 매핑 many-to-one one-to-many one-to-one many-to-many 
- 옵션의 fetch = FetchType.LAZY => 퀘션이 로딩되도 유저를 바로 로딩하지않는다 one-to-many many-to-many 의 디폴트 <=> eager은 반대
- answer추가하려면 answerRespository를 만들 수도 있지만 cascade 설정을 해주면 question에서 할수있다 메소드만들어서. 
- 의존성 때문에 전부다 관계를 맺지않고 적당히 끊어서 uni-direction으로 만든다 한쪽에서만 접근가능하게 

## 코딩(10:10 ~ 15:15) 
## 크롱님 강의(15:15 ~ 16:40)
## 포비님 강의(16:40 ~ 17:20)