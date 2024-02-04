---
    layout: posts
    title: "스프링 프레임워크 6장 템블릿 엔진 알아보기"
    categories: log
    tags: [blog]
    toc_label: 목차
    toc: true
    toc_sticky: true
    last_modified_at: 2024-02-05 01:37
    classes: wide
    published: true
---

1. 템플릿 모델이란 : 데이터를 미리 정의된 템플릿에 바인딩해서 뷰의 표시를 도와주는 역할  
2. 타임리프란 :
 - HTML 기반의 템플릿 엔진으로, 정해진 문법으로 작성하면 페이지를 동적으로 조립해줌  
 - HTML을 기반으로 해, 최종 출력을 생각하면서 뷰를 만들 수 있다. 타임리프를 사용하면 디자이너와 쉽게 분업할 수 있음  

3. Model 인터페이스란 : 
 - 처리한 데이터를 뷰에 표시하고 싶을 경우, 데이터를 전달하는 역할  
 - 스프링 MVC에 의해 관리되며, 수동 또는 자동으로 객체를 저장하고 관리하는 기능을 제공  
 - Model을 이요하고 싶은 경우 요청 핸들러 메서드의 인수에 Model 타입을 전달. 스프링 MVC가 자동으로 Model 타입 인스턴스를 설정  

4. 중요한 메서드 :
 - addAttribute : 특정 이름에 대해 값을 설정. 저장하고 싶은 값에 별명을 붙인다. 뷰에서 별명에 사용한 이름을 이용 (ex : Model addAttribute(String name, Object value))  

5. 타임리프 특징 : 
 - 스프링 부트에서 추천하는 템플릿 엔진  
 - HTML로 템플릿을 작성하기 때문에 웹 브라우저로 파일의 내용을 표시하고 확인하면서 뷰를 만들 수 있음  
 - 스프링 부트의 기본 설정으로 src/main/resources/templates 폴더 아래에 '요청 핸들러 메서드의 반환값 + .html' 파일이 참조됨  