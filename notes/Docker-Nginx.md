---
type : knowledges
detail : 
content_type :
---

[[Docker]]
created : 2022-03-23 13:17
tags : #๐ฅ๏ธ/Docker  

# Docker-Nginx
- nginx ์ด๋ฏธ์ง ํ์ฉํ์ฌ ๊ตฌํ ๊ฐ๋ฅ

```dockerfile
FROM nginx:latest

COPY default.conf /etc/nginx/conf.d/default.conf

CMD ["nginx", "-g", "daemon off;"]
```

- confํ์ผ์ ๋ณต์ฌํ์ฌ ํด๋น ๊ฒฝ๋ก์ ์ ์ฅํด์ผ ํจ
