---
type : knowledges
created : 2022-06-12 09:55
tags : ๐ฅ๏ธ/โจ๏ธ
keywords : [Go, ์์ถ๋ ฅ]
description : 
---

# Go - ์์ถ๋ ฅ

## fmt
- Go์์ ๊ธฐ๋ณธ์ ์ผ๋ก ์ ๊ณตํ๋ fmt๋ฅผ ํ์ฉํ์ฌ ์์ถ๋ ฅ ๊ฐ๋ฅ
- ํ์ค ์ถ๋ ฅ์ Print(), Println(), Printf(), ํ์ค ์๋ ฅ์ Scan(), Scanf(), Scanln()
	- Print(), Scan() : ํ์ค ์์ถ๋ ฅ, ์ค๋ฐ๊ฟ ์์
	- Println(), Scanln() : ์ค๋ฐ๊ฟ ๊ธฐ์ค์ผ๋ก ํ ์ค ์์ถ๋ ฅ
	- Printf(), Scanf() : ํฌ๋ฉง์ ๋ง๊ฒ ์์ถ๋ ฅ
- Printf() ์ ํจ๊ป ์ฌ์ฉํ๋ ํฌ๋ฉง
	- %d : ์ ์
	- %t : bool ๊ฐ์ true/false๋ก ์ถ๋ ฅ
	- %s : ๋ฌธ์์ด ์ถ๋ ฅ
- Scan()์ผ๋ก ์๋ ฅ ๋ฐ์ ๋, &๋ฅผ ํ์ฉํ์ฌ ๋ฉ๋ชจ๋ฆฌ ์ฃผ์๊ฐ์ ์ ๋ฌ

## bufio
- fmt ํจํค์ง๋ ๋งค์ฐ ๋๋ฆฐ ๊ฒฝํฅ์ด ์์

```go
import (
	"fmt"
	"bufio"
	"os"
)

func main() {
	var x int
	reader := bufio.NewReader(os.stdin)
	writer := bufio.NewWriter(os.stdout)
	defer writer.Fulsh()

	fmt.Fscanln(reader, &x)
	fmt.Fprintln(writer, x)
}
```

- ํ๋ก๊ทธ๋จ ์ข๋ฃ ์  `out.Flush()` ๋ฅผ ๊ผญ ์คํํด์ผ ํจ

### bufio ํ์ฉ
- tags : #โ/๐ฉ #๐/๐ข

```go
var (
	sc *bufio.Scanner
	wr *bufio.Writer
)

func init() {
	sc = bufio.NewScanner(os.Stdin)
	sc.Split(bufio.ScanWords)

	wr = bufio.NewWriter(os.Stdout)
}

func nextInt() int {
	sc.Scan()
	ret, _ := strconv.Atoi(sc.Text())
	return ret
}

func nextWord() string {
	sc.Scan()
	return sc.Text()
}

func main() {
	defer wr.Flush()
	x := scanInt()
	wr.WriteString(strconv.Itoa(x))
}
```

- initํจ์์์ sc, wr์ ๋ฐ๋ก ์์ฑํ๋ฉด ์ค๋ฅ ๋ฐ์, initํจ์์์๋ ์๋ก์ด ๋ณ์ ์ง์ ์ด ์๋๋ ๊ฒ์ธ์ง ํ์ธํ  ํ์ ์์
- ๊ฐ ์ธ๋ถ ํจ์๋ค์ ์กฐ๊ธ ๋ ๊ณต๋ถํ  ํ์๊ฐ ์์ ๋ฏ ํจ

---

# ์ฐธ์กฐ
- [golang fmt ํจํค์ง๋ฅผ ์ด์ฉํ ํ์ค ์์ถ๋ ฅ](https://dev-yakuza.posstree.com/ko/golang/fmt/)