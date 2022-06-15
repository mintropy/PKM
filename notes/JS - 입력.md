---
type : knowledges
detail : 
content_type :
---

[[JavaScript]]
created : 2022-06-11 11:11
tags : #🖥️/JS 

# JS - 입력
```javascript
var fs = require('fs');
var input = fs.readFileSync('/dev/stdin').toString().split(' ');
```

- 정확한 흐름은 한 번 확인해봐야 할 것 같지만,
	- `fs`를 불러오고, 지원하는 함수를 통해 입력받는 것 같다
- 정확한 줄별 입력이나, 입력 구분은 조금 햇갈리는 부분이 있고, 저 부분을 암기해서 사용하는건 조금 시간이 걸릴 수 있겠다는 생각도 들지만, 구조자체는 크게 복잡하지 않은 것 같다

## windows
- 윈도우 로컬에서는 `/dev/stdin`을 읽지 못한다고 한다
- 수동으로 입력해서 푸는 방법을 주로 사용하는 것 같다

# readline, fs
- readline 모듈도 있는 것 같은데, 속도가 느리다는 것 같다
	- Python의 `input()`과 `sys.stdin.readline()` 의 차이 같다

# windows에서 입력환경 구축
- 다양한 입력환경을 구축한 것을 확인했는데, 번거로운 부분이 많아 크게 신경쓰지 않았다.
- BOJ 풀이도중 [JS 코드](https://www.acmicpc.net/source/41827713)를 확인했고, 이 방식이면 충분히 편하게 구현할 수 있을 것 같다.
	- input 파일을 생성하고 지정하는게 조금 귀찮았던 부분이 있었는데, JS에서는 그나마 이게 젤 편한 것 같다.

```js
const fs = require("fs")
const filePath = process.platform === "linux" ? "/dev/stdin" : "./input.txt"
const input = fs.readFileSync(filePath).toString().trim().split("\n")
```

- fs를 통하여 입력 받는 구조를 설정하는 것 까지는 똑같지만
- filepath 변수를 통하여 input파일을 지정하거나, 기존에 사용한것처럼 /dev/stdin 을 활용하는 것 같다.
- 자세한 구조에 대한 이해는 조금 더 필요할 것 같지만, 충분히 좋은 방법 같다.

# 참조
- [Node.js입력을 Python처럼 쉽게 받는 법](https://degurii.tistory.com/108)
- [Node.js 입력 받기](https://velog.io/@exploit017/%EB%B0%B1%EC%A4%80Node.js-Node.js-%EC%9E%85%EB%A0%A5-%EB%B0%9B%EA%B8%B0)