<aside>
💡 스프링의 목적

</aside>

- 엔터프라이즈 애플리케이션 개발을 더 쉽도록 도움

<aside>
💡 스프링 부트의 목적

</aside>

- 스프링 개발을 더 쉽도록 도움  

<aside>
💡 스프링

</aside>

- 환경 구성 수동, 내장 WAS 무

<aside>
💡 스프링 부트

</aside>

- 환경 구성 자동, 내장 WAS 유

<aside>
💡 제어의 역전 (IoC == Inversion of Control)

</aside>

- 객체를 직접 생성, 제어하지 않고 스프링 컨테이너가 객체를 관리, 제공한다

<aside>
💡 의존성 주입 (DI = Dependency Injection)

</aside>

- 어떤 클래스가 다른 클래스에 의존한다 == 스프링 컨테이너에 있는 빈을 주입한다

<aside>
💡 빈 (Bean)

</aside>

- 스프링 컨테이너에서 관리하는 객체

> ***의존성 주입(DI)을 통해 제어의 역전(IoC)을 구현한다***
> 

<aside>
💡 관점 지향 프로그래밍 (AOP == Aspect Oriented Programming)

</aside>

- 프로그래밍에 대한 관심을 핵심 관점, 부가 관점으로 나누어 모듈화 하는 행위
- (핵심 관점 코드에 집중할 수 있으며 프로그램 변경과 확장에도 유연성을 지닌다)

<aside>
💡 이식 가능한 서비스 추상화 (PSA == Portable Service Abstraction)

</aside>

- 스프링에서 제공하는 기술들을 추상화하여 개발자가 쉽게 사용하는 인터페이스를 의미

> localhost == loopback == 127.0.0.1
> 

<aside>
💡 @RestController == @ResponseBody + @Controller

</aside>

- 라우터 역할을 하는 애너테이션 라우터 : HTTP 요청과 메서드를 연결하는 장치 (1:1 Mapping)

<aside>
  
💡 @Controller

</aside>

- View(html)에 HTTP 요청을 매핑 시키는 애너테이션
