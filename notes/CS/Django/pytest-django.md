---
type : knowledges
---

[[Python]]
created : 2022-03-07 10:58
tags : #🖥️note #🖥️note/Django 

# pytest-django
- https://jadehan.tistory.com/4
- pytest의 django 플러그인
	- Python 표준 라이브러리 unittest보다 효율적으로 테스트하기 위해 만들어짐
- 테스트를 위해 프로젝트 루트에 pytest.ini 파일 작성 필요

```
[pytest]
DJANGO_SETTINGS_MODULE = project_name.settings
python_files = *tests.py
```

- 추가적 테스트 설정 작성 가능