---
type : knowledges
detail : 
content_type :
---

[[Docker]]
created : 2022-03-23 13:17
tags : #🖥️/Docker  

# Docker-Nginx
- nginx 이미지 활용하여 구현 가능

```dockerfile
FROM nginx:latest

COPY default.conf /etc/nginx/conf.d/default.conf

CMD ["nginx", "-g", "daemon off;"]
```

- conf파일을 복사하여 해당 경로에 저장해야 함
