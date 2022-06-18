---
type : knowledges
created : 2022-06-13 03:54
tags : 🖥️/⌨️ 
keywords : [Java, 자료형]
description : Java 자료형 
---

# Java - 변수와 자료형
- 변수는 `int a;`, `Sting b;`와 같은 형태로 선언
- 변수는 pascalCase
- 자료형은 int, long. double, boolean, char, String, StringBuffer, List, Map, Set 등이 있음

## 숫자

```java
int x = 10;
long y = 123456L;
float z = 1.23F;
double w = 1.23456;
```

- 정수형은 `int`, `long`, 실수형은 `float`, `double`
	- 정수형은 `int`, 실수형은 `double`가 기본 타입이므로 `long`일때는 변수 뒤에 `L`, `float`일때는 변수 뒤에`F`를 붙여줘야 함

## 문자 & 문자열
```java
char a1 = 'a'; // 문자
char a2 = 97; // 아스키코드
char a3 = '\u0061' // 유니코드
```

- 단일 문자에 대한 자료형

```java
String a = "Hello";
String a = new String("Hello")
```

- 문자열 : 여러개의 문자로 이루어진 자료형
	- new 키워드를 통하여 객체 생성할 수 있음

## array & list

```java
int[] odds {1, 3, 5, 7, 9};
```

- 배열 자료형은 `[]`를 사용하여 나타내고, 앞에서 포함하는 자료형을 표현

## map
- key, value값을 저장하는 자료형으로, 대표적으로 `HashMap`

## set
-  집합

---

# 참조
- [WikiDocs - 점프 투 자바](https://wikidocs.net/book/31)
