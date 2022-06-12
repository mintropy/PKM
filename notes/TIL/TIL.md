# TIL
**tags** : #✏️TIL 

```dataview
Table without id
	file.name AS "날짜",
	summary AS "요약"
From #✏️TIL 
Where !contains(file.name, "TIL")
LIMIT 30
SORT file.name DESC
```
