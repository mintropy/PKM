---
type : knowledges
detail : 
content_type :
---

[[Docker-Compose]]
created : 2022-03-23 13:53
tags : #🖥️/Docker  

# Docker-Compose-Django&gunicorn&nginx

- Django가 HTTP 통신을 하기 위해 gunicorn을 활용해야 함
- gunicorn에 대한 통신을 nginx가 받아서, 리버스 프록시 설정을 함

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

- Django 이미지 이후 Nginx 이미지 빌드
	- MySQL은 지속해서 빌드할필요가 없어 제거
	- [[Docker-Compose-MySQL&Django]] : Django + MySQL
- Django는 `gunicorn` 설치 후 간단하게 gunicorn으로 실행할 수 있음
	- volumes를 통하여 공유하는 자원 설정
- nginx는 HTTP, HTTPS 통신을 위한 80, 442 포트를 개방하고, Django의 자원 사용을 위한 volumes 설정

## volumes
- docker-compose의 named volumes를 사용
	- volumes에서 volume 이름:위치 형식으로 지정할 수 있음
- django에서 공유되는 자원의 위치는 docker 컨테이너 내부의 위치를 지정해야 하는데, 컨테이너를 실행하여 CLI환경에서 `pwd` 명령어를 통하여 디렉토리를 찾아서입력할 수 있음
- nginx는 받아서 사용해서인지, volumes 위치를 사용하고자 하는 위치로 설정하면 되는것으로 보임
