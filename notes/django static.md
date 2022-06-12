---
type : knowledges
---

[[Python]]
created : 2022-03-07 10:53
tags : #🖥️Note #🖥️Note/Django 

# django static
- https://blog.hannal.com/2015/04/start_with_django_webframework_06/
- Django는 정적 파일을 제공하는 역할이 없음
- settings.py 에서 STATICFILES_DIRS, STATIC_URL, STATIC_ROOT를 활용하여 제공

## STATICFILES_DIRS
```python
STATICFILES_DIRS = (
	os.path.join(BASE_DIR, 'static')
)
```
- 경로를 list 또는 tuple로 생성
	- 각 요소 마지막의 쉼표가 있으면 안됨