---
type : knowledges
detail : 
content_type :
---

[[JavaScript]]
created : 2022-06-11 11:11
tags : #๐ฅ๏ธ/JS 

# JS - ์๋ ฅ
```javascript
var fs = require('fs');
var input = fs.readFileSync('/dev/stdin').toString().split(' ');
```

- ์ ํํ ํ๋ฆ์ ํ ๋ฒ ํ์ธํด๋ด์ผ ํ  ๊ฒ ๊ฐ์ง๋ง,
	- `fs`๋ฅผ ๋ถ๋ฌ์ค๊ณ , ์ง์ํ๋ ํจ์๋ฅผ ํตํด ์๋ ฅ๋ฐ๋ ๊ฒ ๊ฐ๋ค
- ์ ํํ ์ค๋ณ ์๋ ฅ์ด๋, ์๋ ฅ ๊ตฌ๋ถ์ ์กฐ๊ธ ํ๊ฐ๋ฆฌ๋ ๋ถ๋ถ์ด ์๊ณ , ์  ๋ถ๋ถ์ ์๊ธฐํด์ ์ฌ์ฉํ๋๊ฑด ์กฐ๊ธ ์๊ฐ์ด ๊ฑธ๋ฆด ์ ์๊ฒ ๋ค๋ ์๊ฐ๋ ๋ค์ง๋ง, ๊ตฌ์กฐ์์ฒด๋ ํฌ๊ฒ ๋ณต์กํ์ง ์์ ๊ฒ ๊ฐ๋ค

## windows
- ์๋์ฐ ๋ก์ปฌ์์๋ `/dev/stdin`์ ์ฝ์ง ๋ชปํ๋ค๊ณ  ํ๋ค
- ์๋์ผ๋ก ์๋ ฅํด์ ํธ๋ ๋ฐฉ๋ฒ์ ์ฃผ๋ก ์ฌ์ฉํ๋ ๊ฒ ๊ฐ๋ค

# readline, fs
- readline ๋ชจ๋๋ ์๋ ๊ฒ ๊ฐ์๋ฐ, ์๋๊ฐ ๋๋ฆฌ๋ค๋ ๊ฒ ๊ฐ๋ค
	- Python์ `input()`๊ณผ `sys.stdin.readline()` ์ ์ฐจ์ด ๊ฐ๋ค

# windows์์ ์๋ ฅํ๊ฒฝ ๊ตฌ์ถ
- ๋ค์ํ ์๋ ฅํ๊ฒฝ์ ๊ตฌ์ถํ ๊ฒ์ ํ์ธํ๋๋ฐ, ๋ฒ๊ฑฐ๋ก์ด ๋ถ๋ถ์ด ๋ง์ ํฌ๊ฒ ์ ๊ฒฝ์ฐ์ง ์์๋ค.
- BOJ ํ์ด๋์ค [JS ์ฝ๋](https://www.acmicpc.net/source/41827713)๋ฅผ ํ์ธํ๊ณ , ์ด ๋ฐฉ์์ด๋ฉด ์ถฉ๋ถํ ํธํ๊ฒ ๊ตฌํํ  ์ ์์ ๊ฒ ๊ฐ๋ค.
	- input ํ์ผ์ ์์ฑํ๊ณ  ์ง์ ํ๋๊ฒ ์กฐ๊ธ ๊ท์ฐฎ์๋ ๋ถ๋ถ์ด ์์๋๋ฐ, JS์์๋ ๊ทธ๋๋ง ์ด๊ฒ ์ ค ํธํ ๊ฒ ๊ฐ๋ค.

```js
const fs = require("fs")
const filePath = process.platform === "linux" ? "/dev/stdin" : "./input.txt"
const input = fs.readFileSync(filePath).toString().trim().split("\n")
```

- fs๋ฅผ ํตํ์ฌ ์๋ ฅ ๋ฐ๋ ๊ตฌ์กฐ๋ฅผ ์ค์ ํ๋ ๊ฒ ๊น์ง๋ ๋๊ฐ์ง๋ง
- filepath ๋ณ์๋ฅผ ํตํ์ฌ inputํ์ผ์ ์ง์ ํ๊ฑฐ๋, ๊ธฐ์กด์ ์ฌ์ฉํ๊ฒ์ฒ๋ผ /dev/stdin ์ ํ์ฉํ๋ ๊ฒ ๊ฐ๋ค.
- ์์ธํ ๊ตฌ์กฐ์ ๋ํ ์ดํด๋ ์กฐ๊ธ ๋ ํ์ํ  ๊ฒ ๊ฐ์ง๋ง, ์ถฉ๋ถํ ์ข์ ๋ฐฉ๋ฒ ๊ฐ๋ค.

# ์ฐธ์กฐ
- [Node.js์๋ ฅ์ Python์ฒ๋ผ ์ฝ๊ฒ ๋ฐ๋ ๋ฒ](https://degurii.tistory.com/108)
- [Node.js ์๋ ฅ ๋ฐ๊ธฐ](https://velog.io/@exploit017/%EB%B0%B1%EC%A4%80Node.js-Node.js-%EC%9E%85%EB%A0%A5-%EB%B0%9B%EA%B8%B0)