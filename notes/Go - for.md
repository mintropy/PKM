---
type : knowledges
detail : 
content_type :
---

[[Go]]
created : 2022-06-12 09:26
tags : #๐ฅ๏ธ/Go 

# Go - for
- Go์์ ๋ฐ๋ณต๋ฌธ์ forํ๋๋ง ์กด์ฌ

## ๊ธฐ๋ณธ์ ์ธ for๋ฌธ
```go
func main() {
	sum := 0
	for i := 1; i <= 100; i++ {
		sum += i
	}
	println(sum)
}
```

## ๋ฌดํ ๋ฃจํ
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

- range ๋ฌธ์ ์ฌ์ฉํ๋ฉด, ์ธ๋ฑ์ค, ์์๊ฐ์ด ๋งค์นญ

## break, continue, goto
- for ๋ฌธ์์ ๋น ์ ธ๋์ฌ ๋ break
- for ๋ฌธ์์ ํน์  ๋ฃจํ๋ฅผ ๊ฑด๋๋ฐ๊ณ  ๋ค์ ๋ฃจํ ์์์ผ๋ก ๊ฐ ๋ continue
- ์์์ ๋ฌธ์ฅ์ผ๋ก ์ด๋ํ  ๋ goto

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

# ์ฐธ์กฐ
- [go - ๋ฐ๋ณต๋ฌธ](http://golang.site/go/article/8-Go-%EB%B0%98%EB%B3%B5%EB%AC%B8)