---
type : knowledges
detail : 
content_type :
---

[[Python]]
created : 2022-03-26 17:22
tags : #π₯οΈ/β¨οΈ  

# Docstringκ³Ό μ΄λΈνμ΄μ
- μ½λλ₯Ό λ¬Έμν νκΈ° μν΄ μ£Όμ λμ  docstringμ μ§ν₯ν΄μΌ ν¨
- λμ  νμμ΄λ―λ‘, docstring λλ μ΄λΈνμ΄μ λ±μ ν΅νμ¬ λ³μμ νμ λ± λͺμν΄μΌ ν¨
	- [[type hint]]λ₯Ό ν΅νμ¬ νμμ λͺμμ  νμ©ν  μ μμ

## Docstring
- μμ€ μ½λμ ν¬ν¨λ λ¬Έμ
	-  λ¬Έμμ΄λ―λ‘, μ½λμ λν μ΄μ λ³΄λ€λ μ€λͺμ ν¬ν¨
- μ£Όμμ μ§μν΄μΌ νλ μ΄μ ?
	- μ½λλ‘ μΆ©λΆν νννμ§ λͺ»νμμ μλ―Έ
	- μ½λμ μ£Όμ μ μ²΄λ₯Ό νμΈ νλ κ³Όμ μΌλ‘ μ€ν΄μ μμ§κ° μμ
	- μ€λ₯κ° μλ€λ©΄ λͺμμ μΌλ‘ μ£Όμμ ν΅νμ¬ μμ±νλκ² μ’μ μ μμ
- docstringμ μ₯μ ?
	- `dict.update??` μ κ°μ λ°©μμΌλ‘ docstringμ μ½μ μ μμ
	- λλ `.__doc__` κ³Ό κ°μ λ°©μμΌλ‘ λΆλ¬λΌ μ μμ

## μ΄λΈνμ΄μ
- PEP 3107
	- ν¨μ μΈμμ λν ννΈ
- ν¨μμ `__annotation__`μΌλ‘ μ μ₯λ¨
	- ν¨μμ μΈμ λ° λ°ν κ°μ λνμ¬ λͺμμ μΌλ‘ μμ±λ¨
	- λ³μ μλλ₯Ό μ€λͺνλ λ¬Έμμ΄, μ½λ°±μ΄λ μ ν¨μ± κ²μ¬λ₯Ό μν¨ callable λ± κ°λ₯
- νμ΄μ¬ 3.6
	- λ³μμ μ§μ  μ£Όμμ λ¬μ νμ© κ°λ₯

# Docstringκ³Ό μ΄λΈνμ΄μ λΉκ΅
- μ΄λΈνμ΄μμ΄ λμλκΈ° μ λΆν° docstring νμ©
	- κ° νλΌλ―Έν°μ νμ, μ€λͺ, λ°ν, λ°μ κ°λ₯ν μμΈ λ± λͺ¨λ  λ΄μ©μ docstringμΌλ‘ μμ±νλ μ»¨λ²€μλ μμ
- docstringκ³Ό μ΄λΈνμ΄μμ μλ‘ λ³΄μμ  κ°λ
	- docstirngμ μΌλΆ λ΄μ©μ μ΄λΈνμ΄μμΌλ‘ λκ²¨ νμ©ν  μ μμ
	- νμ§λ§, μμΈ λ± νΉμ  μν©μ λν μ€λͺμ νλ κ³΅κ°μ λ¨κ²¨ λμ΄μΌ ν¨

# κ΄λ ¨ λΌμ΄λΈλ¬λ¦¬
- mypy
- pylint