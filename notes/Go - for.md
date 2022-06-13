---
type : knowledges
detail : 
content_type :
---

[[Go]]
created : 2022-06-12 09:26
tags : #🖥️Note/Go 

# Go - for
- Go에서 반복문은 for하나만 존재

## 기본적인 for문
```go
func main() {
	sum := 0
	for i := 1; i <= 100; i++ {
		sum += i
	}
	println(sum)
}
```

## 무한 루프
```go
func main() {
	for {
		println("Infinite loop")
	}
}
```

## for - range
```go
countries := []string{"korea", "usa", "france"}

for index, name := range names {
	println(index, name)
}
```

- range 문을 사용하면, 인덱스, 요소값이 매칭

## break, continue, goto
- for 문에서 빠져나올 때 break
- for 문에서 특정 루프를 건너뛰고 다음 루프 시작으로 갈 때 continue
- 임의의 문장으로 이동할 때 goto

```go
func main() {
	var a = 1
	for a < 15 {
		 if a == 5{
			a += a
			continue
		 }
		 a++
		 if a > 10 {
			 break
		 }
	}
	if a == 11 {
		goto END
	}
	println(a)

END:
	print(ln)
}
```

# 참조
- [go - 반복문](http://golang.site/go/article/8-Go-%EB%B0%98%EB%B3%B5%EB%AC%B8)