---
type : knowledges
detail : 
content_type :
---

[[Django]]
created : 2022-03-28 20:58
tags : #๐ฅ๏ธ/Django 

# N+1 Problem
- ํ๋์ ์ฟผ๋ฆฌ ์ดํ, ๊ฐ ๋ชจ๋ธ์ ๊ฐ์ด ํ์ํ  ๋, ๊ฐ ๋ชจ๋ธ์ ์๋ก์ด ์ฟผ๋ฆฌ๋ฅผ ์์ฑํ์ฌ N๋ฒ์ ์ถ๊ฐ ์ฟผ๋ฆฌ๊ฐ ๋ฐ์ํ๋ ๋ฌธ์ 
- Django ORM ์ Lazy-Loading ๋ฐฉ์
	- ORM ๋ช๋ น์ด๊ฐ ๋ฐ์ํ  ๋๊ฐ ์๋๋ผ, ์ค์  ์ฌ์ฉํ  ๋ ์ฟผ๋ฆฌ ๋ฐ์
- prefetch_related๋ฅผ ํตํ์ฌ ํด๊ฒฐํ  ์ ์์

## select_related vs prefetch_related
- select_related : JOIN์ ํตํ ๋ฐฉ๋ฒ
- prefetch_related : WHERE โฆ IN ๊ตฌ๋ฌธ ๋ฑ์ ํตํ์ฌ ์๋ก์ด ์ฟผ๋ฆฌ๋ก ํด๊ฒฐํ๋ ๋ฐฉ๋ฒ
