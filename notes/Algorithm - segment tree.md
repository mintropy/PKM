---
type : knowledges
detail : 
content_type :
---

created : 2022-06-14 06:46
tags : #🖥️/algorithm 

# Algorithm - segment tree
- 세그먼트 트리 : 여러 개의 데이터가 연속적으로 존재할 때, 특정 범위 데이터의 합 등을 구하는 방법에서 유용한 구조
- 세그먼트 트리를 활용하면 O(logN)으로 가능

``` mermaid
graph TD
1((1)) --- 2((2))
1((1)) --- 3((3))
2((2)) --- 4((4))
2((2)) --- 5((5))
3((3)) --- 6((6))
3((3)) --- 7((7))
4((4)) --- 8((8))
4((4)) --- 9((9))
5((5)) --- 10((10))
5((5)) --- 11((11))
6((6)) --- 12((12))
6((6)) --- 13((13))
7((7)) --- 14((14))
7((7)) --- 15((15))
8((8)) --- 16((16))
8((8)) --- 17((17))
12((12)) --- 24((24))
12((12)) --- 25((25))
```

- N = 10일 때, 다음과 같은 그래프로 구현할 수 있고
	- 각 리프노드를 순서로 개별 노드의 값을, 그리고 나머지 노드는 자식 노드의 합으로 나타낼 수 있음

## 초기화
```python
def init(arr, tree, node, start, end):
	if start == end:
		tree[node] = a[start]
	else:
		init(a, tree, node * 2, start, (start + end) // 2)
		init(a, tree, node * 2 + 1, (start + end) // 2 + 1, end)
		tree[node] = tree[node * 2] + tree[node * 2 + 1]
```

- start == end : 리프 노드이므로 배열의 해당 인덱스를 저장
- 아니라면, 왼쪽 자식과 오른쪽 자식을 각각 탐색하여 저장

## 구간합 구가기
```python
def query(treee, node, start, end, left, right):
	if left > end or right < start:
		return 0
	if left <= start and end <= right:
		return tree[node]
	lsum = query(tree, node * 2, start, (start + end) // 2, left, right)
	rsum = query(tree, node * 2 + 1, (start + end) // 2 + 1, end, left, right)
	return lsum + rsum
```

- 각 노드가 가진 값이 특정 범위의 합이 되므로, 이를 구간별로 탐색하며 정답을 구하는 과정

## 수 변경하기
```python
def update_tree(tree, node, start, endl, index, diff):
	if index < start or index > end:
		return
	tree[node] = tree[node] + diff
	if start != end:
		update(tree, node * 2, start, (start + end) // 2, index, diff)
		update(tree, node * 2 + 1, (start + end) // 2 + 1, end, index, diff)

def update(a, tree, n, index, val):
	diff = val - [index]
	a[index] = val
	update_tree(tree, 1, 0, n - 1, index, diff)
```

- index번째 수를 val로 변경하는경우, index 노드의 합을 저장하는 경우만 변경하면 됨

```python
def update(a, tree, node, start, end, index, val):
	if index < start or index > end:
		return
	if start == end:
		a[index] = val
		tree[node] = val
		retrun
	update(a, tree, node * 2, start, (start + end) // 2, index, val)
	update(a, tree, node * 2 + 1, (start + end) // 2 + 1, index, val)
	tree[node] = tree[node * 2] + tree[node * 2 + 1]
```

- 리프노드까지 내려간 뒤 올라오면서 노드의 합을 더하는 방법

# 참조
- [나동빈 - 세그먼트 트리](https://m.blog.naver.com/ndb796/221282210534)
- [백준 - 세그먼트 트리](https://book.acmicpc.net/ds/segment-tree)