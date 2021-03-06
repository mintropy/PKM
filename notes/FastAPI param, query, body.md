---
type : knowledges
detail : 
content_type :
---

[[Python]]
created : 2022-05-31 09:48
tags : #๐ฅ๏ธ/โจ๏ธ 

# FastAPI param, query, body
- [[HTTP param, query, body]]
	- ์ด์  ํ๋ก์ ํธ๋ฅผ ๊ฑฐ์น๋ฉฐ ๊ณ ๋ฏผํ๋ ๋ถ๋ถ์ ์ ๋ฆฌ
	- FastAPI์์ ์ฌ์ฉ๋๋ ๋ฐฉ์ ๊ธฐ์ค์ผ๋ก ๋ค์ ์ ๋ฆฌ

# parameter
- [FastAPI - path params](https://fastapi.tiangolo.com/ko/tutorial/path-params/)
- ๊ฒฝ๋ก ๋ณ์๋ ํ์ด์ฌ ๋ฌธ์์ด ํ์์ผ๋ก ์ง์ ํ  ์ ์์

```python
@app.get("item/{item_id}")
async def read_item(item_id):
	return {"item_id": item_id}
```

- ๋งค๊ฐ๋ณ์๋ ํ์ด์ฌ ์ด๋ธํ์ด์์ ๋ฐ๋ผ ํ์์ ์ง์  ํ  ์ ์์

# query
- [FastAPI - query params](https://fastapi.tiangolo.com/ko/tutorial/query-params/)
- ํจ์ ๋ด๋ถ์์ ๊ฒฝ๋ก ๋ณ์๊ฐ ์๋ ๋งค๊ฐ ๋ณ์๊ฐ ์์ผ๋ฉด query๋ก ์๋ํด์
	- ์๋์ ์ผ๋ก query๋ก ์ ์ฉ๋๋๊ฒ์ ์๊ฐํ์ง ๋ชปํด, ๋ชจ๋  ๋ณ์๋ฅผ query๋ก ์ฒ๋ฆฌํด๋ฒ๋ ธ์

# body
- [FastAPI - body](https://fastapi.tiangolo.com/ko/tutorial/body/)
- pydantic ๋ชจ๋ธ ๋ฑ์ ํ์ฉํ์ฌ ์ ์ธ

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