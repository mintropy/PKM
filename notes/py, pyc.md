---
type : knowledges
detail : 
content_type :
---

[[Python]]
created : 2022-04-23 13:28
tags : #🖥️/Python 

# py, pyc
- python파일의 확장자는 `.py`, `.pyc`, `.pyo` 등이 있음

## py
- 일반적으로 Python은 CPython을 의미
	- 이는 언어를 실제로 구현하는 결과 중 하나로, PyPy, Jython 등의 구현이 존재
- py는 Python 소스 코드
- py파일을 실행시킬 때, 내부적으로 다음 단계 실행
	- PVM(Python Virtual Machine)이 이해할 수 있는 Byte code형태로 컴파일
	- 컴파일된 Byte code를 PVM이 단계별 실행

## pyc
- pyc파일은 파일은 import 할 때 생성
- pyc를 활용하여, 원본 py 파일 없이도 더 빠르게 실행할 수 있도록 함

## pyo
- 최적화된(optimized) 컴파일된 바이너리 파일

# 참조
- https://jins-sw.tistory.com/25
