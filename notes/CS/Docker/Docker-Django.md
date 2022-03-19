---
type : knowledges
detail : 
content_type :
---

[[Docker]]
created : 2022-03-19 11:32
tags : #🖥️note/Docker 

# Docker-Django
- 기본 구조
```docker
FROM python

WORKDIR /app/backend

RUN python -m pip install --upgrade pip

COPY ./backend/requirements.txt .
RUN pip install -r requirements.txt

COPY ./backend .
```

- 프로젝트 루트 위치에 있다면 WORKDIR을 `/app`으로 사용
- pip 설치 후 upgrade, requirements 설치의 큰 구조

## MySQL
- MySQL을 활용할 때, Django에서 mysqlclient를 활용해야 함
- 이 때, mysqlclient설치과정에서 문제 발생
- Docker 이미지는 alpine, slim 등의 종류가 있음
	- alpine 이미지를 사용 할 때, c라이브러리 의존성 문제가 있을 수 있음
	- mysqlclient도 그러한 이유로 안된다고 생각이 되고, slim 이미지를 활용하여 해결할 수 있음

```docker
FROM python:3.7-slim

RUN apt-get update
RUN apt-get install -y gcc
RUN apt-get install -y default-libmysqlclient-dev
ENV PYTHONBUFFERED 1
```
