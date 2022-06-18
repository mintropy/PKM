---
type : knowledges
created : 2022-06-17 11:23
tags : 🖥️
keywords : [Java, 제어문]
description : Java 제어문
---

# Java - 제어문

## if 
```java
if (조건문) {
	// 코드
} else if (조건문) {
	// 코드
} else if (조건문) {
	// 코드
} else {
	// 코드
}
```

- 조건 판단에서 and(&&), or(||), not(!)을 사용

## switch/case
- if문과 유사하지만 정형화된 조건 판단문

## while

```java
while (조건문) {
	// 코드
}
```

- 반복문을 무한으로 수행할 때

## for & for each

```java
String[] numbers = {"one", "two", "three"}
for (int i=0; i<numbers.length; i++) {
	System.out.println(numbers[i]);
}
```

- 전형적인 for문 구조
- for each 구조로 변경하면 다음과 같음
`
```java
for (String number: numbers) {
	System.out.println(number);
}
```

---

# 참조
- [WikiDocs - 점프 투 자바](https://wikidocs.net/book/31)
