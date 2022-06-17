---
type : knowledges
created : 2022-06-16 03:02
tags : 🖥️/⌨️
keywords : [LCS]
description : 
---

# Algorithm - LCS
- Longest Common Subsequence
	- 최장 공통 부분수열

## LCS 찾기
- 점화식

```python
if i == 0 or j == 0:
	LCS[i][j] = 0
elif s1[i] == s2[j]:
	LCS[i][j] = LCS[i - 1][j - 1] + 1
else:
	LCS[i][j] = 0
```

- 문자열을 하나씩 비교하며, 공통부분이 있다면, 그 부분이 앞부분과 이어지도록 설정

## LCS 길이 구하기
- 만약 위의 방법처럼 진행한다면, 길이를 구하기 위해 모든 배열을 순회해야함

```python
if i == 0 or j == 0:
	LCS[i][j] = 0
elif s1[i] == s2[j]:
	LCS[i][j] = LCS[i - 1][j - 1] + 1
else:
	LCS[i][j] = max(LCS[i - 1][j], LCS[i][j - 1])
```

- LCS가 발견되지 않는다면 최댓값을 갱신하며, 배열의 마지막 값을 기준으로 LCS 길이를 구할 수 있도록 함

## LCS 찾기
- 배열의 마지막 위치에서 시작하여 `LCS[i - 1][j]`, `LCS[i][j - 1]`중 현재 값과 같은 값을 찾음
	- 같은 값이 있다면 해당 값으로 이동
	- 같은 값이 없다면, 정답애 해당 문자를 넣고, `LCS[i - 1][j - 1]`로 이동
	- 반복하며 값이 0이 되면 종료, 저장된 배열 값의 역순을 출력

# 참조
- [그림으로 알아보는 LCS 알고리즘](https://velog.io/@emplam27/%EC%95%8C%EA%B3%A0%EB%A6%AC%EC%A6%98-%EA%B7%B8%EB%A6%BC%EC%9C%BC%EB%A1%9C-%EC%95%8C%EC%95%84%EB%B3%B4%EB%8A%94-LCS-%EC%95%8C%EA%B3%A0%EB%A6%AC%EC%A6%98-Longest-Common-Substring%EC%99%80-Longest-Common-Subsequence)
