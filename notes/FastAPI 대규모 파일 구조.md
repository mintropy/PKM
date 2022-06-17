---
type : knowledges
detail : 
content_type :
---

[[Python]]
created : 2022-05-31 11:50
tags : #🖥️/⌨️ 

# FastAPI 대규모 파일 구조
- Flask나 FastAPI를 시작할 때 두려웠던 부분이 내가 스스로 파일 구조를 제작하고 구성해야한다는 것이였다.
- FastAPI에서는 이러한 구조에 대한 기본적인 규칙은 제공한다
	- [FastAPI Bigger Applications](https://fastapi.tiangolo.com/ko/tutorial/bigger-applications/)
	- 물론 유연하게 구성할 수 있지만, 좋은 기준이 될 수 있을 것 같다.

```
├── app
│   ├── __init__.py
│   ├── main.py
│   ├── dependencies.py
│   └── routers
│   │   ├── __init__.py
│   │   ├── items.py
│   │   └── users.py
│   └── internal
│       ├── __init__.py
│       └── admin.py
```

- 기본적으로 다음과 같은 구조를 제안
- app 디렉터리에서 모든 파일 포함
	- `main.py`를 포함하고, 모듈화 하기 위한 `__init__.py`
	- dependency를 담기 위한 `dependencies.py`
- app/router 디렉터리에서 라우터 생성
	- 모듈화를 위한 `__init__.py`
- app/internal과 같은 또다른 모듈 생성

## APIRouter
- `fastapi.APIRouter` 사용

## Dependencies
- 의존성 주입을 위한 함수 & 클래스 
