---
type : knowledges
detail : 
content_type :
---

[[Python]]
created : 2022-05-31 10:53
tags : #๐ฅ๏ธ/โจ๏ธ 

# FastAPI SQL
- [FastAPI SQL database](https://fastapi.tiangolo.com/ko/tutorial/sql-databases/)
- SQLAlchemy๋ฅผ ํ์ฉํด์ SQLite๋ฟ๋ง ์๋๋ผ, PostgreSQL, MySQL ๋ฑ ์ฐ๋ํ  ์ ์์
	- SQLAlchemy ORM์ ํ์ฉํ  ์ ์์ (low SQL๋ ์ฌ์ฉํ  ์ ์์)

## SQLAlchemy ์ถ๊ฐ
- database์ ์ฐ๋ํ  URL ์ถ๊ฐ
	- SQLite์ธ ๊ฒฝ์ฐ `"sqlite:///./sql_app.db"`๋ฅผ ์ฌ์ฉ
- `sqlalchemy.create_engine`๋ฅผ ํตํ์ฌ DB URL ์ฐ๋
- `sqlalchemy.orm.sessionmaker`
	- DB ์ธ์์ ๋ง๋ค์ด์ค
- `sqlalchemy.ext.declarative.declarative_base`
	- Base ํด๋์ค๋ฅผ ์์ฑ

## database model ์์ฑ
- sqlalchmey๋ก ์์ฑํ Base ํด๋์ค๋ฅผ ์์๋ฐ์ database์ ์ ์ฉํ  ํ์ด๋ธ ์์ฑ

## Pydantic model ์์ฑ
- database์์ ์ฌ์ฉํ๋๊ฒ ์๋๋ผ ๋ฐฑ์๋์์ ์ฌ์ฉํ  Pydantic ๋ชจ๋ธ ์์ฑ
	- FastAPI > Pydantic > SQLAlchemy > DB ํ๋ฆ์ผ๋ก ์งํ๋๋ ๊ฒ์ผ๋ก ๋ณด์

## CRUD utils
- ์ค์ ๋ก CRUD๋ฅผ ์งํํ  ํจ์ ์์ฑ

## main app ์์ 
- ์ค์  ๋์ํ๋ CRUD utils์ ํ์ฉ, request-response ๊ณผ์ ์์ ์ด๋ฃจ์ด ์ง ์ ์๋๋ก ์์ 

## migration์ด ํ์ํ ๊ฒฝ์ฐ
- Alembic์ ํ์ฉํด migration์งํ ํ ์ฌ์ฉํ  ์ ์์