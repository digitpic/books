<aside>
💡 프레젠테이션 계층 == Controller

</aside>

- HTTP 요청을 받고 해당 요청을 비즈니스 계층으로 전송하는 역할

<aside>
💡 비즈니스 계층 == Service

</aside>

- 서비스를 만들기 위한 로직(=비즈니스 로직)을 처리하는 역할

<aside>
💡 퍼시스턴스 계층 == Repository

</aside>

- 모든 데이터베이스 관련 로직을 처리하는 역할

<aside>
💡 DTO (=Data Transfer Object)

</aside>

- 데이터를 전송하기 위한 객체

<aside>
💡 DAO (=Data Access Object)

</aside>

- 데이터베이스 계층과 상호작용 하기 위한 객체

> 계층 == 개념 영역
> 
> 
> Controller, Service, Repository == 실제 구현을 위한 영역
> 

- 테이블과 클래스를 매핑하기 위한 작업에는 인터페이스 파일(=Repository)이 필요

<aside>
💡 스프링 부트 res-req 과정

</aside>

1. HTTP 요청이 들어온다
2. 스프링 부트의 디스패처 서블릿이 URL을 분석하고 이 요청을 처리할 수 있는 컨트롤러를 찾아 전달
3. HTTP 요청과 매핑되는 메서드(프레젠테이션 계층)를 만나 비즈니스 계층, 퍼시스턴스 계층을 통과해 필요한 데이터를 처리
4. 뷰 리졸버라는 템플릿 엔진을 통해 HTML 문서를 만들거나 JSON, XML 등의 데이터를 생성
5. 생성된 데이터를 return
