---
type : knowledges
---

[[Python]]
created : 2022-03-07 10:53
tags : #๐ฅ๏ธ #๐ฅ๏ธ/Django 

# django static
- https://blog.hannal.com/2015/04/start_with_django_webframework_06/
- Django๋ ์ ์  ํ์ผ์ ์ ๊ณตํ๋ ์ญํ ์ด ์์
- settings.py ์์ STATICFILES_DIRS, STATIC_URL, STATIC_ROOT๋ฅผ ํ์ฉํ์ฌ ์ ๊ณต

## STATICFILES_DIRS
```python
STATICFILES_DIRS = (
	os.path.join(BASE_DIR, 'static')
)
```
- ๊ฒฝ๋ก๋ฅผ list ๋๋ tuple๋ก ์์ฑ
	- ๊ฐ ์์ ๋ง์ง๋ง์ ์ผํ๊ฐ ์์ผ๋ฉด ์๋จ