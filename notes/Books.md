# Books
tags : #π₯οΈ/π 

```mermaid
graph LR
A[Books] --> B[κ°λ³ μ±] --> C[μ± μμΈ]
```

- κ°λ³ μ± νμΌ μ΄λ¦μ μ± μ΄λ¦μΌλ‘
	- λ²μ­μλΌλ νκΈμ± κΈ°μ€μΌλ‘ μμ±
	- λΆμ λͺ©μ ν¬ν¨νμ§ μκΈ°
	- μ λͺ©μ `κ°μ ν` λ±μ΄ λ€μ΄κ° κ²½μ°μλ μ μΈ
- μ± μμΈ νμΌμ΄ νμν κ²½μ°, `μ±μ΄λ¦ - μ±ν°`λ‘ νμ
	- κ° μ±ν°μ λ΄μ©μ΄ λλ¬΄ λ§μ μ§λ€λ©΄ μλ‘μ΄ λ¬Έμλ‘ κ΅¬λΆνκΈ°
	- μ±ν°μ κ²½μ° ν΄λΉ μ±ν°μ λ²νΈκΉμ§ κ°μ΄ μμ±

# λμ κΈ°λ‘

## μνλ³
```dataview
TABLE without id
	status as "μν",
	length(rows) as "μ± μ"
FROM #π₯οΈ/π 
WHERE !contains(file.name, "Book")
GROUP BY status
SORT status DESC
```

# μ± λͺ©λ‘
```dataview
TABLE without id
	status as "μν",
	file.link as "λμλͺ",
	dateformat(start_read_date, "DD") as "μμμΌ",
	dateformat(finish_read_date, "DD") as "μλ£μΌ",
	rate as "λ΄ νμ "
FROM #π₯οΈ/π 
WHERE !contains(file.name, "Book")
SORT start_read_date DESC
```