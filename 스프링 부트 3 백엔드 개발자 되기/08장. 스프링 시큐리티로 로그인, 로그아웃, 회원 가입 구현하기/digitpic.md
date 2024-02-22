
 
 ## 인증 (Authentication)

 

- 사용자의 신원을 확인하는 단계

 
 ## 인가 (Authrization)

 

- 사용자의 권한을 확인하는 단계

 
 ## 스프링 시큐리티

 

- 스프링 기반 애플리케이션의 보안을 담당하는 스프링 하위 프레임워크
- 필터 기반을 동작

> UsernamePasswordAuthenticationFilter
> 
- 아이디와 패스워드가 넘어오면 인증 요청을 위임하는 인증 관리자 역할

> FilterSecurityInterceptor
> 
- 권한 부여 처리를 위임해 접근 제어 결정을 하는 접근 결정 관리자 역할

> SecurityContextPersistenceFilter
> 
- 시작 필터

> FilterSecurityInterceptor
> 
- 마지막 필터
