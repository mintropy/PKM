---
type : knowledges
---

[[Python]]
created : 2022-03-06 22:18
tags : #🖥️ #🖥️/Django  

# django-environ
- https://django-environ.readthedocs.io/en/latest/
- Django의 환경 변수를 관리해주는 라이브러리
---
- https://raccoonyy.github.io/django-environ/
- https://velog.io/@kyleee/TIL56-django-environ%EC%9D%84-%EC%9D%B4%EC%9A%A9%ED%95%9C-%ED%99%98%EA%B2%BD%EB%B3%80%EC%88%98-%EA%B4%80%EB%A6%AC
- Docker 등 환경을 사용하면, 환경 변수 관리가 더욱 중요함
- settings.py의 환경변수를 .env파일에 저장
	- .env는 프로젝트 루트에 위치 (manage.py 위치)
	- 변수와 값 사이 공백은 없어야 함
```
DEBUG=TRUE
SECRET_KEY='secret-key'
```

---
- https://daeenchoi.medium.com/how-to-set-environment-variables-in-django-project-using-django-environ-local-production-34545338d0f5
- env 모든 변수를 `environ.Env()` 로 기본 값을 설정하여 두면 됨