---
type : knowledges
created : 2022-06-17 02:37
tags : 🖥️/⌨️
keywords : [Go, 변수, 자료형]
description : 
---

# Go - 변수와 자료형

## 변수, 상수

```go
var i int
const c str = "hello"
```

- 변수는 `var`, 상수는 `const`키워드를 통하여 생성 가능
	- 변수는 초기값을 지정하지 않을 경우 Zero Value로 지정

```go
var x int = 123
y := 456
```

- `:=` 를 사용하면 `var`를 명시하지 않고 변수 선언할 수 있음

- [[Go - new, make]]

## 자료형

- [[Go - string]]
- [[Go - big int]]
- [[Go - 타입 변환]]

---
# 참조
- [예제로 배우는 Go 프로그래밍 - 변수와 상수](http://golang.site/go/article/4-Go-%EB%B3%80%EC%88%98%EC%99%80-%EC%83%81%EC%88%98)
