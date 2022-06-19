---
type : knowledges
created : 2022-06-13 08:53
tags : 🖥️/⌨️ 
detail : 
content_type :
---


# Python - abc
- 추상화 클래스(abstract class)
- 미구현 추상메소드를 한 개 이상 가지며, 자식 클래스에서 추상 메소드를 반드시 구현하도록 강제
	- 상속받은 클래스는 추상메소드를 구현하지 않아도 에러가 발생하지 않으나, 객체를 생성할 시 에러 방생

```python
from abc import *
class 추상클래스(metaclass=ABCMeta):
	@abstactmethod
	def 추상메소드(self):
		pass
```

- 추상클래스를 인터페이스로 생각할 때, 인터페이스를 포멧 스팩으로 볼 수 있음
	- 특정 구현에대해 인터페이스게 맞게 사용하는지 강제할 수 있음

# 참조
- [Python document - abc](https://docs.python.org/ko/3/library/abc.html?highlight=abc#module-abc)
- [wikidocs - 파이썬 abc](https://wikidocs.net/16075)
- [python abc](https://thrillfighter.tistory.com/727)
- [YouTube - Protocol or ABC in Python](https://www.youtube.com/watch?v=xvb5hGLoK0A)
