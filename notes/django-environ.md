---
type : knowledges
---

[[Python]]
created : 2022-03-06 22:18
tags : #๐ฅ๏ธ #๐ฅ๏ธ/Django  

# django-environ
- https://django-environ.readthedocs.io/en/latest/
- Django์ ํ๊ฒฝ ๋ณ์๋ฅผ ๊ด๋ฆฌํด์ฃผ๋ ๋ผ์ด๋ธ๋ฌ๋ฆฌ
---
- https://raccoonyy.github.io/django-environ/
- https://velog.io/@kyleee/TIL56-django-environ%EC%9D%84-%EC%9D%B4%EC%9A%A9%ED%95%9C-%ED%99%98%EA%B2%BD%EB%B3%80%EC%88%98-%EA%B4%80%EB%A6%AC
- Docker ๋ฑ ํ๊ฒฝ์ ์ฌ์ฉํ๋ฉด, ํ๊ฒฝ ๋ณ์ ๊ด๋ฆฌ๊ฐ ๋์ฑ ์ค์ํจ
- settings.py์ ํ๊ฒฝ๋ณ์๋ฅผ .envํ์ผ์ ์ ์ฅ
	- .env๋ ํ๋ก์ ํธ ๋ฃจํธ์ ์์น (manage.py ์์น)
	- ๋ณ์์ ๊ฐ ์ฌ์ด ๊ณต๋ฐฑ์ ์์ด์ผ ํจ
```
DEBUG=TRUE
SECRET_KEY='secret-key'
```

---
- https://daeenchoi.medium.com/how-to-set-environment-variables-in-django-project-using-django-environ-local-production-34545338d0f5
- env ๋ชจ๋  ๋ณ์๋ฅผ `environ.Env()` ๋ก ๊ธฐ๋ณธ ๊ฐ์ ์ค์ ํ์ฌ ๋๋ฉด ๋จ