---
type : knowledges
---

[[Python]]
created : 2022-03-07 10:58
tags : #๐ฅ๏ธ #๐ฅ๏ธ/Django 

# pytest-django
- https://jadehan.tistory.com/4
- pytest์ django ํ๋ฌ๊ทธ์ธ
	- Python ํ์ค ๋ผ์ด๋ธ๋ฌ๋ฆฌ unittest๋ณด๋ค ํจ์จ์ ์ผ๋ก ํ์คํธํ๊ธฐ ์ํด ๋ง๋ค์ด์ง
- ํ์คํธ๋ฅผ ์ํด ํ๋ก์ ํธ ๋ฃจํธ์ pytest.ini ํ์ผ ์์ฑ ํ์

```
[pytest]
DJANGO_SETTINGS_MODULE = project_name.settings
python_files = *tests.py
```

- ์ถ๊ฐ์  ํ์คํธ ์ค์  ์์ฑ ๊ฐ๋ฅ