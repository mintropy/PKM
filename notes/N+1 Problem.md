---
type : knowledges
detail : 
content_type :
---

[[Django]]
created : 2022-03-28 20:58
tags : #🖥️/Django 

# N+1 Problem
- 하나의 쿼리 이후, 각 모델의 값이 필요할 때, 각 모델에 새로운 쿼리를 생성하여 N번의 추가 쿼리가 발생하는 문제
- Django ORM 은 Lazy-Loading 방식
	- ORM 명령어가 발생할 때가 아니라, 실제 사용할 때 쿼리 발생
- prefetch_related를 통하여 해결할 수 있음

## select_related vs prefetch_related
- select_related : JOIN을 통한 방법
- prefetch_related : WHERE … IN 구문 등을 통하여 새로운 쿼리로 해결하는 방법
