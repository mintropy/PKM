---
type : knowledges
created : 2022-06-12 09:55
tags : 🖥️/⌨️
keywords : [Go, 입출력]
description : 
---

# Go - 입출력

## fmt
- Go에서 기본적으로 제공하는 fmt를 활용하여 입출력 가능
- 표준 출력은 Print(), Println(), Printf(), 표준 입력은 Scan(), Scanf(), Scanln()
	- Print(), Scan() : 표준 입출력, 줄바꿈 없음
	- Println(), Scanln() : 줄바꿈 기준으로 한 줄 입출력
	- Printf(), Scanf() : 포멧에 맞게 입출력
- Printf() 와 함께 사용하는 포멧
	- %d : 정수
	- %t : bool 값을 true/false로 출력
	- %s : 문자열 출력
- Scan()으로 입력 받을 때, &를 활용하여 메모리 주소값을 전달

## bufio
- fmt 패키지는 매우 느린 경향이 있음

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

- 프로그램 종료 전 `out.Flush()` 를 꼭 실행해야 함

### bufio 활용
- tags : #✅/🟩 #😄/🟢

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

- init함수에서 sc, wr을 바로 생성하면 오류 발생, init함수에서는 새로운 변수 지정이 안되는 것인지 확인할 필요 있음
- 각 세부 함수들을 조금 더 공부할 필요가 있을 듯 함

---

# 참조
- [golang fmt 패키지를 이용한 표준 입출력](https://dev-yakuza.posstree.com/ko/golang/fmt/)