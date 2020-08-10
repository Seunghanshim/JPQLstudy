# JPQL
  - JPQL은 객체지향 쿼리 언어다. 따라서 테이블을 대상으로 쿼리하는 것이 아니라 엔티티 객체를 대상으로 쿼리한다.
  - JPQL은 SQL을 추상화하기 때문에 특정 데이터베이스 SQL에 의존하지않는다.
  - JPQL은 결국 SQL로 변환된다.
  
# JPQL 문법
  - select m from Member as m where m.age > 18
  - 엔티티와 속성은 대소문자 구분을 한다. (Member, age)
  - JPQL 키워드는 대소문자 구분을 하지 않는다. (SELECT, FROM, where)
  - 엔티티 이름 사용한다. (default는 Class 이름) (주의! 테이블 이름이 아님)
  - 별칭은 필수다. (m) (as는 생략가능)
  
# TypeQuery, Query
  - TypeQuery: 반환 타입이 명확할 때 사용한다.
  - Query: 반환 타입이 명확하지 않을 때 사용한다.
  - TypeQuery<Member> query = em.createQuery("select m from Member m", Member.class);
  - Query query = em.createQuery("select m.username, m.age from Member m");
  
# 결과 조회 API
  - query.getResultList(): 결과가 하나 이상일 때, 리스트로 반환한다. (결과가 없으면 빈 리스트 반환)
  - query.getSingleResult(): 결과가 정확히 하나일때, 단일 객체를 반환한다. (결과가 없을 때, 둘 이상일 때 모두 Exception 발생)
  

# 예시 객체 모델
  ![객체모델](https://user-images.githubusercontent.com/68942616/89766643-728ed600-db33-11ea-8352-e0693ac8a46e.PNG)
  
# 예시 DB 모델
  ![DB 모델](https://user-images.githubusercontent.com/68942616/89766645-73276c80-db33-11ea-867a-679fd433f815.PNG)
