---
type : knowledges
detail : 
content_type :
---

[[JavaScript]]
created : 2022-06-11 11:11
tags : #🖥️Note/JS 

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

# 참조
- [Node.js입력을 Python처럼 쉽게 받는 법](https://degurii.tistory.com/108)
- [Node.js 입력 받기](https://velog.io/@exploit017/%EB%B0%B1%EC%A4%80Node.js-Node.js-%EC%9E%85%EB%A0%A5-%EB%B0%9B%EA%B8%B0)