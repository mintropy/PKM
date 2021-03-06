---
type : knowledges
detail : 
content_type :
---

[[Docker-Compose]]
created : 2022-03-23 13:53
tags : #๐ฅ๏ธ/Docker  

# Docker-Compose-Django&gunicorn&nginx

- Django๊ฐ HTTP ํต์ ์ ํ๊ธฐ ์ํด gunicorn์ ํ์ฉํด์ผ ํจ
- gunicorn์ ๋ํ ํต์ ์ nginx๊ฐ ๋ฐ์์, ๋ฆฌ๋ฒ์ค ํ๋ก์ ์ค์ ์ ํจ

```yaml
# docker-compose.yml

version: "3"

services:
  backend:
    container_name: service_django
    build:
      context: .
      dockerfile: ./docker/backend/Dockerfile
    ports:
      - 8000:8000
    command: gunicorn back.wsgi:application --bind 0.0.0.0:8000
    volumes:
      - static_volume:/app/backend/staticfiles
      - media_volume:/app/backend/media
  nginx:
    container_name: service_nginx
    build:
      context: .
      dockerfile: ./docker/nginx/Dockerfile
    ports:
      - 80:80
      - 443:443
    depends_on:
       - backend
    volumes:
      - static_volume:/data/staticfiles
      - media_volume:/data/media

volumes:
  static_volume:
  media_volume:
```

- Django ์ด๋ฏธ์ง ์ดํ Nginx ์ด๋ฏธ์ง ๋น๋
	- MySQL์ ์ง์ํด์ ๋น๋ํ ํ์๊ฐ ์์ด ์ ๊ฑฐ
	- [[Docker-Compose-MySQL&Django]] : Django + MySQL
- Django๋ `gunicorn` ์ค์น ํ ๊ฐ๋จํ๊ฒ gunicorn์ผ๋ก ์คํํ  ์ ์์
	- volumes๋ฅผ ํตํ์ฌ ๊ณต์ ํ๋ ์์ ์ค์ 
- nginx๋ HTTP, HTTPS ํต์ ์ ์ํ 80, 442 ํฌํธ๋ฅผ ๊ฐ๋ฐฉํ๊ณ , Django์ ์์ ์ฌ์ฉ์ ์ํ volumes ์ค์ 

## volumes
- docker-compose์ named volumes๋ฅผ ์ฌ์ฉ
	- volumes์์ volume ์ด๋ฆ:์์น ํ์์ผ๋ก ์ง์ ํ  ์ ์์
- django์์ ๊ณต์ ๋๋ ์์์ ์์น๋ docker ์ปจํ์ด๋ ๋ด๋ถ์ ์์น๋ฅผ ์ง์ ํด์ผ ํ๋๋ฐ, ์ปจํ์ด๋๋ฅผ ์คํํ์ฌ CLIํ๊ฒฝ์์ `pwd` ๋ช๋ น์ด๋ฅผ ํตํ์ฌ ๋๋ ํ ๋ฆฌ๋ฅผ ์ฐพ์์์๋ ฅํ  ์ ์์
- nginx๋ ๋ฐ์์ ์ฌ์ฉํด์์ธ์ง, volumes ์์น๋ฅผ ์ฌ์ฉํ๊ณ ์ ํ๋ ์์น๋ก ์ค์ ํ๋ฉด ๋๋๊ฒ์ผ๋ก ๋ณด์
