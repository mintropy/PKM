---
type : knowledges
detail : 
content_type :
---

[[Go]]
created : 2022-06-11 10:34
tags : #🖥️/Go 

# Go - big int
- big int : $2^53 -1 = 9007199254740989$보다 큰 정수
- 생각보다 큰 문제가 되는 부분인데, Python만 하다보니 신경을 안쓰고 있었다

```go
import (
	"fmt"
	"math/big"
)

func main() {
	var n, m big.Int
	fmt.Scanln(&n, &m)
	
	add := new(big.Int)
	add = add.Add(&n, &m)
	fmt.Println("Add : ", add)

	sub := new(big.Int)
	sub = sub.Sub(&n, &m)
	fmt.Println("Sub : ", sub)

	mul := new(big.Int)
	mul = mul.Mul(&n, &m)
	fmt.Println("Mul : ", mul)

	div := new(big.Int)
	div = div.Div(&n, &m)
	fmt.Println("Mul : ", div)

	mod := new(big.Int)
	mod = mod.Mod(&n, &m)
	fmt.Println("Mod : ", mod)
}
```

## 새로운 big int 만들기
- `new(big.Int)`를 통하여 생성하면 비어있는 값으로 생성됨
- 만약 특정 값을 기반으로 연산을 하거나 한다면 기준이 되는 수가 필요함
- 이 때 `num := big.NewInt(0)`와 같은 방식으로 초기화하여 생성할 수 있음

# 참조
- [MDN - BigInt](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/BigInt)
- [Go document - math/big](https://pkg.go.dev/math/big)
	- [Runebook.dev 한글 번역](https://runebook.dev/ko/docs/go/math/big/index)
- [golang big integer](https://clucle.tistory.com/entry/golang-big-integer)
- [Go 패키지 탐방 - math/big & bits](https://velog.io/@whdnjsdyd111/GO-3-8.-%ED%8C%A8%ED%82%A4%EC%A7%80-%ED%83%90%EB%B0%A9-mathbig-bits)
