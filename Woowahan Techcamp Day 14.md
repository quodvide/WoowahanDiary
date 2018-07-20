# Woowahan Techcamp Day 14

## Daily Meeting (9:00 ~ 9:10)

## Git Test (9:10 ~ 10:15)

## 호눅스님 강의 (10:15 ~ 17:30) 

### MySQL, Sequal Pro 설정 팁 + DATABASE

- MySQL 설치 시 Root password를 꼭! 넣어주어야한다. 
- MySQL설정시 'userId'@'%' => 모든 외부에서 접속해서 사용하기위함
- GRANT ALL ON mydb.* To 'userId'@'%' => 해당 데이터베이스의 권한 허용 
- HOST라는 물리적인 컴퓨터 안에서 돌아가는 것이 SERVER이다
- PK는 기본적으로 인덱스(B tree)를 만들어준다. -> 중복검사를위해
- Key - pk, Value  - RID(page, slot number)로 B tree생성 
- Clustered index (B tree(primary index) + 툼스톤등으로 표현하는 저장방식(secondary index))
- DB를 HDD에 저장하는 방식에는 Column Store, Record Store의 방식이 있다. RDB는 보통 Record(전자상거래는 보통 Record 전체를 본다) Store 방식이다.

### 다음시간 

ISO의 Transaction isolation level  
=> 엄격할수록 Integrity 올라가고 Throughput 느려짐 

- serializable
- Read uncommitted 
- Read committed 
- Repeatable read