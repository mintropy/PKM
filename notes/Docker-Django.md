---
type : knowledges
detail : 
content_type :
---

[[Docker]]
created : 2022-03-19 11:32
tags : #๐ฅ๏ธ/Docker 

# Docker-Django
- ๊ธฐ๋ณธ ๊ตฌ์กฐ
```docker
FROM python

WORKDIR /app/backend

RUN python -m pip install --upgrade pip

COPY ./backend/requirements.txt .
RUN pip install -r requirements.txt

COPY ./backend .
```

- ํ๋ก์ ํธ ๋ฃจํธ ์์น์ ์๋ค๋ฉด WORKDIR์ `/app`์ผ๋ก ์ฌ์ฉ
- pip ์ค์น ํ upgrade, requirements ์ค์น์ ํฐ ๊ตฌ์กฐ

## MySQL
- MySQL์ ํ์ฉํ  ๋, Django์์ mysqlclient๋ฅผ ํ์ฉํด์ผ ํจ
- ์ด ๋, mysqlclient์ค์น๊ณผ์ ์์ ๋ฌธ์  ๋ฐ์
- Docker ์ด๋ฏธ์ง๋ alpine, slim ๋ฑ์ ์ข๋ฅ๊ฐ ์์
	- alpine ์ด๋ฏธ์ง๋ฅผ ์ฌ์ฉ ํ  ๋, c๋ผ์ด๋ธ๋ฌ๋ฆฌ ์์กด์ฑ ๋ฌธ์ ๊ฐ ์์ ์ ์์
	- mysqlclient๋ ๊ทธ๋ฌํ ์ด์ ๋ก ์๋๋ค๊ณ  ์๊ฐ์ด ๋๊ณ , slim ์ด๋ฏธ์ง๋ฅผ ํ์ฉํ์ฌ ํด๊ฒฐํ  ์ ์์

```docker
FROM python:3.7-slim

RUN apt-get update
RUN apt-get install -y gcc
RUN apt-get install -y default-libmysqlclient-dev
ENV PYTHONBUFFERED 1
```

- MySQl์ ์์ฑํ๊ณ  ๋ฐ๋ก ์ ๊ทผํ๊ฒ ๋๋ฉด DB์์ฑ์ด ์๋ฃ๋์ง ์์ ์ ๊ทผ์ด ์๋๋ ๋ฌธ์  ๋ฐ์
- ๋ชจ๋  ์ปจํ์ด๋๊ฐ ์์ฑ๋ ์ดํ, migrate ๋ฑ ์์์ผ๋ก ํด๊ฒฐํ  ์ ์์

```bash
docker-compose run backend python manage.py migrate
```

- docker-compose์์ ์์ ๋ช๋ น์ด๋ฅผ ์คํํ๋๋ก ํจ
	- backend๋ docker-compose์์ Django ์ปจํ์ด๋ ์ด๋ฆ
	- `python manage.py maigrate` ์คํ
