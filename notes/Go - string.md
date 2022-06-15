---
type : knowledges
detail : 
content_type :
---

[[Go]]
created : 2022-06-14 01:18
tags : #🖥️/Go 

# Go - string
- 문자열 선언은 큰 따옴표, 백스쿼트 사용

```go
s1 := "string"
s2 := `string`
```

- 이스케이프 문자열
	- `\\` : `\`
	- `\"` : `"`
	- `\n` : 줄바꿈

## 문자열 연산
- 문자열 더하기
	- `+` 로 합치는게 가능하지만, `strings.Join`을 사용하는 방식을 권장
- 문자열 길이
	- `len`을 사용하면 바이트수 반환
	- `unicode/utf8/RuneCountInString`을 활용하거나 배열로 바꾸어 구해야함

# 참조
- [go 문자열 다루기](https://leo-bb.tistory.com/60)
- [go by example - 문자열 함수](https://mingrammer.com/gobyexample/string-functions/)
