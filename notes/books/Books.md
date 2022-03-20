# 독서 기록

## 상태별
```dataview
TABLE without id
	status as "상태",
	length(rows) as "책 수"
FROM #📔Book  
WHERE !contains(file.path, "templates")
GROUP BY status
SORT status DESC
```

# 책 목록
```dataview
TABLE without id
	status as "상태",
	file.link as "도서명",
	dateformat(start_read_date, "DD") as "시작일",
	dateformat(finish_read_date, "DD") as "완료일",
	rate as "내 평점"
FROM #📔Book  
WHERE !contains(file.path, "templates")
```