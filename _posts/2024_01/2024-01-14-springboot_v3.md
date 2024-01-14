---
    layout: posts
    title: "스프링 프레임워크 3장 핵심 기능 알아보기"
    categories: log
    tags: [blog]
    toc_label: 목차
    toc: true
    toc_sticky: true
    last_modified_at: 2024-01-15 01:04
    classes: wide
    published: true
---

1. DI(Dependency Injection) : 의존하는 부분을 외부에서 주입  

2. AOP(Aspect Oriented Programming) : 중심적 관심사, 횡단적 관심사  
 - 중심적 관심사 : 실현해야 할 기능을 나타내는 프로그램  
 - 횡단적 관심사 : 본질적인 기능은 아니지만 유지포수 등 관점에서 반드시 필요한 기능을 나타내는 프로그램  

3. 의존성 : A클래스는 사용하는 객체, B클래스는 사용되는 객체, C클래스는 B클래스 대신 사용될 객체라고 하자.  
```
xxx(){
    B b = new B();
    b.methodX();
}
```
변경 후  
xxx(){
    C c = new C();
    c.methodX();
}
```
총 4개 곳의 코드를 수정했다. 이렇게 수정할 곳이 늘어나면 늘어날 수록 실수할 가능성을 높아진다.  

인터페이스 의존인 경우 클래스 의존 보다 더 적은 실수를 할 가능성이 있다. 다음과 같다.  
```
xxx(){
    I i = new B();
    i.methodX();
}
```
I 인터페이스를 통해 B 클래스의 methodX를 호출합니다.  
새롭게 작성된 C 클래스의 methodX를 호출은 다음과 같다.  
```
xxx(){
    I i = new C();
    i.methodX();
}
```
 - 인터페이스는 참조를 받는 유형으로 변수의 이름을 변경하지 않아도 된다.  
 - 클래스가 바뀌어도 메서드명을 변경하지 않아도 된다.  

 DI 컨테이너 5가지 규칙  
  - 인터페이스를 이용하여 의존성을 만든다.  
  - 인스턴스를 명시적으로 생성하지 않는다 : new 키워드를 사용하지 않는다라는 의미  
  - 어노테이션을 클래스에 부여한다.  
  - 스프링 프레임워크에서 인스턴스를 생성한다.  
  - 인스턴스를 이용하고 싶은 곳에 어노테이션을 부여한다.  

 @Controller : 인스턴스 생성 지시. 스프링 MVC를 이용할 때 컨트롤러에 부여  
 @Service : 인스턴스 생성 지시. 트랜잭션 경계가 되는 도메인 기능에 부여  
 @Repository : 인스턴스 생성 지시. 데이터베이스 엑세스 기능에 부여  
 @Component : 위 용도 이외의 클래스에 부여  

 1. AOP 고유 용어  
  - Advice : 횡단적 관심사의 구현. 로그 출력 및 트랜잭션 제어  
  - Aspect : Advice를 정리한 것  
  - JoinPoint : Advice를 중심적인 관심사에 적용하는 타이밍  
  - Pointcut : Advice를 삽입할 수 있는 위치  
  - Interceptor : 처리의 제어를 인터셉트하기 위한 구조 또는 프로그램  
  - Target : Advice가 도입되는 대상  
