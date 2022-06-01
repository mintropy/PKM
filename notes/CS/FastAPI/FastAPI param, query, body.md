---
type : knowledges
detail : 
content_type :
---

[[Python]]
created : 2022-05-31 09:48
tags : #🖥️note/python 

# FastAPI param, query, body
- [[HTTP param, query, body]]
	- 이전 프로젝트를 거치며 고민했던 부분을 정리
	- FastAPI에서 사용되는 방식 기준으로 다시 정리

# parameter
- [FastAPI - path params](https://fastapi.tiangolo.com/ko/tutorial/path-params/)
- 경로 변수는 파이썬 문자열 형식으로 지정할 수 있음

```python
@app.get("item/{item_id}")
async def read_item(item_id):
	return {"item_id": item_id}
```

- 매개변수는 파이썬 어노테이션에 따라 타입을 지정 할 수 있음

# query
- [FastAPI - query params](https://fastapi.tiangolo.com/ko/tutorial/query-params/)
- 함수 내부에서 경로 변수가 아닌 매개 변수가 잇으면 query로 자동해석
	- 자동적으로 query로 적용되는것을 생각하지 못해, 모든 변수를 query로 처리해버렸음

# body
- [FastAPI - body](https://fastapi.tiangolo.com/ko/tutorial/body/)
- pydantic 모델 등을 활용하여 선언

```python
from typing import Union

from fastapi import FastAPI
from pydantic import BaseModel


class Item(BaseModel):
    name: str
    description: Union[str, None] = None
    price: float
    tax: Union[float, None] = None


app = FastAPI()


@app.post("/items/")
async def create_item(item: Item):
    return item
```