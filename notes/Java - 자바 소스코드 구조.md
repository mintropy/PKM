---
type : knowledges
detail : 
content_type :
---

[[Java]]
created : 2022-06-13 02:57
tags : #🖥️Note/Java 

# Java - 자바 소스코드 구조
```java
/* 클래스명.java */

/* 클래스 블록 */
public class 클래스명 {

    /* 메소드 블록 */
    [public|private|protected] [static] (리턴자료형|void) 메소드명1(입력자료형 매개변수, ...) {
        명령문(statement);
        ...
    }

    /* 메소드 블록 */
    [public|private|protected] [static] (리턴자료형|void) 메소드명2(입력자료형 매개변수, ...) {
        명령문(statement);
        ...
    }
    ...
}
```

- 자바 소스 코드의 기본적인 구조
- 가장 외부의 클래스 블록이 있고, 클래스 이름은 파일 이름과 동일해야함
- 메소드 블럭은 여러개로 이루어 질 수 있고, 
	- public, private, protected라는 접근제어자로 시작
	- static 키워드가 붙으면 static 메소드가 됨
	- 리턴 자료형은 void 또는 리턴 자료형이 있어야 함

## 접근제어자
- 메소드 블록을 private, default, protected, public으로 권한을 설정할 수 있고, 순서대로 더 많은 접근 허용
- private : 해당 클래스에서만 접근할 수 있음
- default : 접근 제어자를 별도로 설정하지 않는다면, 접근제어자가 없는 변수, 메소드는 default 접근 제어자가 되고, 패키지 내에서만 접근 가능
- protected : 클래스를 상속받은 다른 패키지의 클래스에서만 접근 가능
- public : 어떤 클래스에서도 접근 가능

# 참조
- [점프 투 자바 - 자바 소스코드의 구조](https://wikidocs.net/278)