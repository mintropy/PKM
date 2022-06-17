---
type : knowledges
detail : 
content_type :
---

[[Python]]
created : 2022-05-31 10:53
tags : #🖥️/⌨️ 

# FastAPI SQL
- [FastAPI SQL database](https://fastapi.tiangolo.com/ko/tutorial/sql-databases/)
- SQLAlchemy를 활용해서 SQLite뿐만 아니라, PostgreSQL, MySQL 등 연동할 수 있음
	- SQLAlchemy ORM을 활용할 수 있음 (low SQL도 사용할 수 있음)

## SQLAlchemy 추가
- database와 연동할 URL 추가
	- SQLite인 경우 `"sqlite:///./sql_app.db"`를 사용
- `sqlalchemy.create_engine`를 통하여 DB URL 연동
- `sqlalchemy.orm.sessionmaker`
	- DB 세션을 만들어줌
- `sqlalchemy.ext.declarative.declarative_base`
	- Base 클래스를 생성

## database model 생성
- sqlalchmey로 생성한 Base 클래스를 상속받아 database에 적용할 테이블 생성

## Pydantic model 생성
- database에서 사용하는게 아니라 백엔드에서 사용할 Pydantic 모델 생성
	- FastAPI > Pydantic > SQLAlchemy > DB 흐름으로 진행되는 것으로 보임

## CRUD utils
- 실제로 CRUD를 진행할 함수 생성

## main app 수정
- 실제 동작하는 CRUD utils을 활용, request-response 과정에서 이루어 질 수 있도록 수정

## migration이 필요한 경우
- Alembic을 활용해 migration진행 후 사용할 수 있음