---
type : knowledges
created : 2022-06-13 08:53
tags : π₯οΈ/β¨οΈ 
detail : 
content_type :
---

# Python - abc
- μΆμν ν΄λμ€(abstract class)
- λ―Έκ΅¬ν μΆμλ©μλλ₯Ό ν κ° μ΄μ κ°μ§λ©°, μμ ν΄λμ€μμ μΆμ λ©μλλ₯Ό λ°λμ κ΅¬ννλλ‘ κ°μ 
	- μμλ°μ ν΄λμ€λ μΆμλ©μλλ₯Ό κ΅¬ννμ§ μμλ μλ¬κ° λ°μνμ§ μμΌλ, κ°μ²΄λ₯Ό μμ±ν  μ μλ¬ λ°©μ

```python
from abc import *
class μΆμν΄λμ€(metaclass=ABCMeta):
	@abstactmethod
	def μΆμλ©μλ(self):
		pass
```

- μΆμν΄λμ€λ₯Ό μΈν°νμ΄μ€λ‘ μκ°ν  λ, μΈν°νμ΄μ€λ₯Ό ν¬λ©§ μ€ν©μΌλ‘ λ³Ό μ μμ
	- νΉμ  κ΅¬νμλν΄ μΈν°νμ΄μ€κ² λ§κ² μ¬μ©νλμ§ κ°μ ν  μ μμ

# μ°Έμ‘°
- [Python document - abc](https://docs.python.org/ko/3/library/abc.html?highlight=abc#module-abc)
- [wikidocs - νμ΄μ¬ abc](https://wikidocs.net/16075)
- [python abc](https://thrillfighter.tistory.com/727)
- [YouTube - Protocol or ABC in Python](https://www.youtube.com/watch?v=xvb5hGLoK0A)
