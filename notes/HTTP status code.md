---
type : knowledges
detail : 
content_type :
---

[[Network]]
created : 2022-06-01 11:08
tags : #🖥️/Network 

# HTTP status code
- 상태 코드는 크게 다섯가지로 구분
	- 앞자기 기준 1 ~ 5로 구분

## 100 : 정보성 상태 코드
- HTTP/1.1 에서 도입
- 100 Continue
- 101 Switching Protocol
- 102 Processing
- 103 Early Hints

## 200 : 성공 상태 코드
- 200 OK
	- 요청이 성공적이고, 본문에 요청된 리소스 포함
	- PUT, DELETE의 경우 200이 아니라 201, 204로 표현되기도 함
- 201 Created
	- 요청이 성공적이고, 자원이 생성되었음
	- 일반적으로 POST요청에서 사용
- 202 Accepted
	- 요청이 접수되었으나, 동작을 수행하지 않음
	- 요청이 실패할 수 있음
- 203 Non-Authoritative Information
- 204 No Content
	- 요청은 성공했으나, 클라이언트가 현재 페이지에서 벗어나지 않아도 됨
	- PUT요청에서 페이지를 바꾸지 않아도 되는 경우 사용
		- 새로 생성한 경우 201, 새롭게 업데이트 해야할 경우 200 사용
- 205 Reset Content
	- form의 내용을 지우거나 재설정
- 206 Parial Content
	- 부분적, 범위적 요청의 성공
- 207 Multi-Status
- 208 Multi-status
- 226 IM Used

## 300 : 리다이렌션 상태 코드
- 클라이언트가 관심있어 하는 리소스에 대해 다른 위치를 사용하라고 말해주거나, 다른 대안 응답 제안
- 300 Multiple Choice
- 301 Moved Permanetly
- 302 Found
- 303 See Other
- 304 Not Modified
- 305 Use Proxy
- 306 unused
- 307 Temporary Redirect
- 308 Permanent Redirect

## 400 : 클라이언트 에러 상태 코드
- 서버가 처리할 수 없는 무언가를 보냈을 경우
- 400 Bad Request
- 401 Unauthorized
- 402 Payment Required
- 403 Forbidden
- 404 Not Fount
- 405 Method Not Allowed
- 406 Not Acceptable
- 407 Proxy Auchentication Required
- 408 Request Timeout
- 409 Conflict
- 410 Gone
- 411 Length Required
- 412 Precondition Failed
- 413 Request Entity too Large
- 414 Request URI Too Long
- 415 Unsupported Media Type
- 416 Requested Range Not Satisfiable
- 417 Expectation Failed
- 418 Im a teapot
- 421 Misdirected Request
- 422 Unprocessable Entity
- 423 Locked
- 424 Failed Dependency
- 426 Upgrade Required
- 428 Precondition Required
- 429 Too Many Request
- 431 Request Header Fields Too Large
- 451 Unavailable For Legal Reasons

## 500 : 서버 에러 상태 코드
- 500 Internal Server Error
- 501 Not Implemented
- 502 Bad Gateway
- 503 Service Unavailable
- 504 Gateway Timeout
- 505 HTTP version Not Suported
- 506 Variant Also Negotiates
- 507 Insufficient Storage
- 508 Loop Detected
- 510 Not Extended
- 511 Network Authentication Required

# 참조
- [MDN status code](https://developer.mozilla.org/ko/docs/Web/HTTP/Status)
