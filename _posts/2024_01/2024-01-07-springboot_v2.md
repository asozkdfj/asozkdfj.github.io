---
    layout: posts
    title: "스프링 프레임워크 2장 기초 지식"
    categories: log
    tags: [blog]
    toc_label: 목차
    toc: true
    toc_sticky: true
    last_modified_at: 2024-01-08 01:04
    classes: wide
    published: true
---

1. 인터페이스란 : 클래스에 메서드의 구제척인 내용을 작성하지 않고 상수와 메서드 타입만 정의  
 - 선언 방법 : interface 키워드 사용

 ```
 public interface Greet{
    public abstract void gretting();
 }
 ```
추상 클래스로 다른 클래스에서 구현하는 것을 전제로 한다.  
 - 구현 방법 : implements 키위드 사용  
 ```
 public class MonringGreet implements Greet{
    @Override
    public void greeting(){
        System.out.println("좋은 아침입니다.");
    }
 }
 ```
@Override : 메서드에 부여하는 것으로, 재정의 된 메서드라는 걸 알려준다.  

2. 리스트란 : List, Set, Map 등 컬렌션 프레임워크의 종류다.  
ArrayList는 배열로 유지, LinkedList는 전후 양방향의 링크로 참조하는 형식으로 되어있다.  
ex : List<Stirng> names = new ArrayList<>();  

3. 클라이언트와 서버  
 - 클라이언트 : 서비스를 요청하는 쪽 (User)  
 - 서버 : 서비스를 제공하는 쪽

 - 웹 서버란 : 웹 애플리케이션을 배포하는 서버. 항상 실행되며 클라이언트로부터 요청을 대기  
   - HTTP request와 HTTP responce를 통해 상호작용한다. 
 - GET 메서드와 POST 메서드 : HTTP request의 한 유형  
  - GET : URL뒤에 값을 더하여 보내는 형식. URL 뒤에 쿼리 스트링 특징을 이용한다.  
   - URL끝에 ?가 붙어 쿼리 스트링의 시작을 알림.  
   - 형식은 '이름 = 값  
   - 여러 값을 전달하려면 '&'로 연결  
 - POST : 쿼리 스트링은 많은 양의 값을 보내기 적합하지 않기 때문에, request body를 통해 값을 보내는 방법이다. (개인정보 등, 표시되지 않아야할 정보륻 담는 방법에도 사용됨.)  

 4. Lombok & Gradle  
  - Lombok : 라이브러리의 한 종류. 보통 setter, getter의 사용을 편리하게 해주는 역할을 한다.  
  - Gradle : 빌드 도구이다. 빌드 도구는 다음과 같은 역할을 한다. 
   - 필요 라이브러리 다운.  
   - 소스코드 컴파일  
   - 테스트 실행  
   - 클래스 파일의 아카이브 생성  
   - 아카이브 스테이징 환경 등에 배포  
  간략하게 빌드 과정에서 필요한 설정을 작성하는 것으로, 여러 작업을 자동화 해주는 도구다.  