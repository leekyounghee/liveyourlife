### JOIN(결합)의 종류
- 크로스결합, 내부결합, 외부결합 등..

TABLE A 의 레코드 수 : R(A)
TABLE B 의 레코드 수 : R(B)

* 크로스결합으로 출력되는 레코드 수 
+ R(A) * R(B) -> A테이블 전체 행에 대해 B의 전체 행과 결합시킨 결과 출력
* 내부결합은 크로스결합의 부분집합
* 외부결합은 크로스결합의 부분집합이 아님 ( 내부결합과 외부결합은 배타적인 관계이기 때문)


### JOIN ALGORITHM (결합 알고리즘)
- DBMS의 옵티마이저가 실행계획 세울 때 데이터 크기, 결합키의 분산에 따라 알고리즘 선택
* Nested Loops  
![이미지](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FRebRq%2FbtqwjvvlYgM%2Fno5HNEQBVtVlxBdRLlhFK1%2Fimg.png)  
    + 좌측테이블을 구동테이블, 외부테이블이라 부르고 우측테이블을 내부테이블이라 칭한다. 
    + 2개의 테이블의 결합이 실행될 때 구동테이블의 크기가 작아야 성능이 좋다. 
    + 구동테이블의 크기만 작을 것이 아니라, 내부테이블 내 결합키 인덱스가 있어야 한다. (유니크할수록 성능 좋음->반복을 줄일 수 있기 때문)
* Hash
* Sorted Merge
