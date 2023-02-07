---
    layout: posts
    title: "코테준비"
    excerpt: "코테공부중 생각할 것 정리입니다."
    categories: coding
    tags: [coding, blog]
    toc_label: 목차
    toc: true
    toc_sticky: true
    last_modified_at: 2023-01-11
    classes: wide
---

- 이상이면 꼭 = 붙이기 (즉, 범위 확인 잘하기)
- 그 외 예외 생각하기(할인 문제일 경우, 할인이 없는 경우도 생각하기)


vector stl 경우  
- push_back 사용  
- vector stl 사용할 경우, size는 따로 저장해 놓은다음 for문 돌리기
(pop_back이나 push_back을 통해 for문 시, 사이즈 변경될 수도 있다.)
(프로그래머스:배열 뒤집기)
- reverse 함수 잊지 말기 => reverse(num_list.begin(),num_list.end()) 이런식으로


unorder map 자료구조  
- map 자료구조에 비해 key가 적은 경우 유리함.  
(프로그래머스:가장 가까운 같은 글자)  
글자별로 같은 글자가 전 위치 어디인지 확인해야함 -> 이를 map 자료구조에 저장  

