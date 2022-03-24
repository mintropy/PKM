---
type : knowledges
detail : 
content_type :
---

[[Network]]
created : 2022-03-23 13:13
tags : #🖥️note/Network  

# Nginx
-   Nginx는 웹 서버 소프트웨어, 리버시 프록시 기능을 가짐

## Docker & Docker-Compose
- [[Docker-Nginx]]

# conf
- Nginx의 설정 및 리버스 프록시 설정
- 크게 upstream, server 등 옵션 구소를 가짐

## upstream
- upstream은 하나의 백엔드를 가질 때는 큰 의미가 없음
- 유저 입장에서 서버는 Upstream, 서버로부터 흘러나오는 게이터를 받는 것은 Downstream

## server
- 가상 서버에 대한 정의
- listen을 통하여 외부로 부터 듣는 포트 설정
	- 80을 설정하여 HTTP읽기
- location을 통하여 리버스 프록시 설정
	- 위치는 정규식 패턴으로 지정 가능

## 참조
- https://developer88.tistory.com/299
