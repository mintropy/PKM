---
type : knowledges
created : 2022-06-11 10:34
tags : ๐ฅ๏ธ/โจ๏ธ
keywords : [Go, ์๋ฃํ]
description : 
---

# Go - big int
- big int : $2^53 -1 = 9007199254740989$๋ณด๋ค ํฐ ์ ์
- ์๊ฐ๋ณด๋ค ํฐ ๋ฌธ์ ๊ฐ ๋๋ ๋ถ๋ถ์ธ๋ฐ, Python๋ง ํ๋ค๋ณด๋ ์ ๊ฒฝ์ ์์ฐ๊ณ  ์์๋ค

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

## ์๋ก์ด big int ๋ง๋ค๊ธฐ
- `new(big.Int)`๋ฅผ ํตํ์ฌ ์์ฑํ๋ฉด ๋น์ด์๋ ๊ฐ์ผ๋ก ์์ฑ๋จ
- ๋ง์ฝ ํน์  ๊ฐ์ ๊ธฐ๋ฐ์ผ๋ก ์ฐ์ฐ์ ํ๊ฑฐ๋ ํ๋ค๋ฉด ๊ธฐ์ค์ด ๋๋ ์๊ฐ ํ์ํจ
- ์ด ๋ `num := big.NewInt(0)`์ ๊ฐ์ ๋ฐฉ์์ผ๋ก ์ด๊ธฐํํ์ฌ ์์ฑํ  ์ ์์

---

# ์ฐธ์กฐ
- [MDN - BigInt](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/BigInt)
- [Go document - math/big](https://pkg.go.dev/math/big)
	- [Runebook.dev ํ๊ธ ๋ฒ์ญ](https://runebook.dev/ko/docs/go/math/big/index)
- [golang big integer](https://clucle.tistory.com/entry/golang-big-integer)
- [Go ํจํค์ง ํ๋ฐฉ - math/big & bits](https://velog.io/@whdnjsdyd111/GO-3-8.-%ED%8C%A8%ED%82%A4%EC%A7%80-%ED%83%90%EB%B0%A9-mathbig-bits)
