---
type : knowledges
detail : 
content_type :
---

[[Network]]
created : 2022-05-30 17:58
tags : #🖥️note/Network 

# HTTP param, query, body
- 셋이 구분되는건 알았지만, FastAPI로 구현하며 기본적으로 query로 작동되는것을 뒤늦게 알아 수정하기가 조금 곤란했다.
- 그런데 왜 저렇게 나뉘어지는지 궁금했다.

## param
- 주소에 포함된 변수
- 리소스를 식별하는 경우 사용

## query
- 주소 이후 `?`와 함께 담는 변수
- 정렬이나 필터링의 경우 사용

## body
- XML, JSON, Multi Form 등의 데이터를 담음
- 일부 웹 서버에 URI 길이 제한이 있기도 하므로, body에 이진 데이터 등을 활용할 수 있음
