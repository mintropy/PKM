---
type : knowledges
detail : 
content_type :
---

[[Network]]
created : 2022-06-01 11:08
tags : #π₯οΈ/Network 

# HTTP status code
- μν μ½λλ ν¬κ² λ€μ―κ°μ§λ‘ κ΅¬λΆ
	- μμκΈ° κΈ°μ€ 1 ~ 5λ‘ κ΅¬λΆ

## 100 : μ λ³΄μ± μν μ½λ
- HTTP/1.1 μμ λμ
- 100 Continue
- 101 Switching Protocol
- 102 Processing
- 103 Early Hints

## 200 : μ±κ³΅ μν μ½λ
- 200 OK
	- μμ²­μ΄ μ±κ³΅μ μ΄κ³ , λ³Έλ¬Έμ μμ²­λ λ¦¬μμ€ ν¬ν¨
	- PUT, DELETEμ κ²½μ° 200μ΄ μλλΌ 201, 204λ‘ ννλκΈ°λ ν¨
- 201 Created
	- μμ²­μ΄ μ±κ³΅μ μ΄κ³ , μμμ΄ μμ±λμμ
	- μΌλ°μ μΌλ‘ POSTμμ²­μμ μ¬μ©
- 202 Accepted
	- μμ²­μ΄ μ μλμμΌλ, λμμ μννμ§ μμ
	- μμ²­μ΄ μ€ν¨ν  μ μμ
- 203 Non-Authoritative Information
- 204 No Content
	- μμ²­μ μ±κ³΅νμΌλ, ν΄λΌμ΄μΈνΈκ° νμ¬ νμ΄μ§μμ λ²μ΄λμ§ μμλ λ¨
	- PUTμμ²­μμ νμ΄μ§λ₯Ό λ°κΎΈμ§ μμλ λλ κ²½μ° μ¬μ©
		- μλ‘ μμ±ν κ²½μ° 201, μλ‘­κ² μλ°μ΄νΈ ν΄μΌν  κ²½μ° 200 μ¬μ©
- 205 Reset Content
	- formμ λ΄μ©μ μ§μ°κ±°λ μ¬μ€μ 
- 206 Parial Content
	- λΆλΆμ , λ²μμ  μμ²­μ μ±κ³΅
- 207 Multi-Status
- 208 Multi-status
- 226 IM Used

## 300 : λ¦¬λ€μ΄λ μ μν μ½λ
- ν΄λΌμ΄μΈνΈκ° κ΄μ¬μμ΄ νλ λ¦¬μμ€μ λν΄ λ€λ₯Έ μμΉλ₯Ό μ¬μ©νλΌκ³  λ§ν΄μ£Όκ±°λ, λ€λ₯Έ λμ μλ΅ μ μ
- 300 Multiple Choice
- 301 Moved Permanetly
- 302 Found
- 303 See Other
- 304 Not Modified
- 305 Use Proxy
- 306 unused
- 307 Temporary Redirect
- 308 Permanent Redirect

## 400 : ν΄λΌμ΄μΈνΈ μλ¬ μν μ½λ
- μλ²κ° μ²λ¦¬ν  μ μλ λ¬΄μΈκ°λ₯Ό λ³΄λμ κ²½μ°
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

## 500 : μλ² μλ¬ μν μ½λ
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

# μ°Έμ‘°
- [MDN status code](https://developer.mozilla.org/ko/docs/Web/HTTP/Status)
