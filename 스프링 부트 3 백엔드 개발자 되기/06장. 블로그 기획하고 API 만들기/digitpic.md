
 
 ## REST API

 

- URL의 설계 방식

 
 ## REST API 특징

 

- URL만으로도 어떤 행동을 하는 API인지 알 수 있다
- HTTP 메서드 방식의 개수에 제한이 있다
- 공식적인 표준 규약이 없다

> 규칙 1. 동사가 아닌 자원을 표시해야 한다
> 

> 규칙 2. 동사는 HTTP 메서드 (GET, POST, PUT, DELETE)로 표현한다
> 

 
 ## @NoArgsConstructor

 

- 접근 제어자가 protected인 기본 생성자를 생성

 
 ## @RequiredArgsConstructor

 

- final 키워드나 @NotNull 애너테이션이 붙은 필드의 생성자를 추가

 
 ## 직렬화

 

- 자바 객체 to JSON
- writeValueAsString() 메서드

 
 ## 역직렬화

 

- JSON to 자바 객체

 
 ## @PathVariable

 

- URL에서 값을 가져오는 애너테이션

 
 ## @Transactional

 

- 해당 메서드를 하나의 트랜잭션으로 묶는 역할을 하는 애너테이션
