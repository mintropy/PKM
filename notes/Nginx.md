---
type : knowledges
detail : 
content_type :
---

[[Network]]
created : 2022-03-23 13:13
tags : #๐ฅ๏ธ/Network  

# Nginx
-   Nginx๋ ์น ์๋ฒ ์ํํธ์จ์ด, ๋ฆฌ๋ฒ์ ํ๋ก์ ๊ธฐ๋ฅ์ ๊ฐ์ง

## Docker & Docker-Compose
- [[Docker-Nginx]]

# conf
- Nginx์ ์ค์  ๋ฐ ๋ฆฌ๋ฒ์ค ํ๋ก์ ์ค์ 
- ํฌ๊ฒ upstream, server ๋ฑ ์ต์ ๊ตฌ์๋ฅผ ๊ฐ์ง

## upstream
- upstream์ ํ๋์ ๋ฐฑ์๋๋ฅผ ๊ฐ์ง ๋๋ ํฐ ์๋ฏธ๊ฐ ์์
- ์ ์  ์์ฅ์์ ์๋ฒ๋ Upstream, ์๋ฒ๋ก๋ถํฐ ํ๋ฌ๋์ค๋ ๊ฒ์ดํฐ๋ฅผ ๋ฐ๋ ๊ฒ์ Downstream

## server
- ๊ฐ์ ์๋ฒ์ ๋ํ ์ ์
- listen์ ํตํ์ฌ ์ธ๋ถ๋ก ๋ถํฐ ๋ฃ๋ ํฌํธ ์ค์ 
	- 80์ ์ค์ ํ์ฌ HTTP์ฝ๊ธฐ
- location์ ํตํ์ฌ ๋ฆฌ๋ฒ์ค ํ๋ก์ ์ค์ 
	- ์์น๋ ์ ๊ท์ ํจํด์ผ๋ก ์ง์  ๊ฐ๋ฅ

## ์ฐธ์กฐ
- https://developer88.tistory.com/299
