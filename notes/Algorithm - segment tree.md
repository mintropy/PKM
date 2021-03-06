---
type : knowledges
detail : 
content_type :
---

created : 2022-06-14 06:46
tags : #๐ฅ๏ธ/algorithm 

# Algorithm - segment tree
- ์ธ๊ทธ๋จผํธ ํธ๋ฆฌ : ์ฌ๋ฌ ๊ฐ์ ๋ฐ์ดํฐ๊ฐ ์ฐ์์ ์ผ๋ก ์กด์ฌํ  ๋, ํน์  ๋ฒ์ ๋ฐ์ดํฐ์ ํฉ ๋ฑ์ ๊ตฌํ๋ ๋ฐฉ๋ฒ์์ ์ ์ฉํ ๊ตฌ์กฐ
- ์ธ๊ทธ๋จผํธ ํธ๋ฆฌ๋ฅผ ํ์ฉํ๋ฉด O(logN)์ผ๋ก ๊ฐ๋ฅ

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

- N = 10์ผ ๋, ๋ค์๊ณผ ๊ฐ์ ๊ทธ๋ํ๋ก ๊ตฌํํ  ์ ์๊ณ 
	- ๊ฐ ๋ฆฌํ๋ธ๋๋ฅผ ์์๋ก ๊ฐ๋ณ ๋ธ๋์ ๊ฐ์, ๊ทธ๋ฆฌ๊ณ  ๋๋จธ์ง ๋ธ๋๋ ์์ ๋ธ๋์ ํฉ์ผ๋ก ๋ํ๋ผ ์ ์์

## ์ด๊ธฐํ
```python
def init(arr, tree, node, start, end):
	if start == end:
		tree[node] = a[start]
	else:
		init(a, tree, node * 2, start, (start + end) // 2)
		init(a, tree, node * 2 + 1, (start + end) // 2 + 1, end)
		tree[node] = tree[node * 2] + tree[node * 2 + 1]
```

- start == end : ๋ฆฌํ ๋ธ๋์ด๋ฏ๋ก ๋ฐฐ์ด์ ํด๋น ์ธ๋ฑ์ค๋ฅผ ์ ์ฅ
- ์๋๋ผ๋ฉด, ์ผ์ชฝ ์์๊ณผ ์ค๋ฅธ์ชฝ ์์์ ๊ฐ๊ฐ ํ์ํ์ฌ ์ ์ฅ

## ๊ตฌ๊ฐํฉ ๊ตฌ๊ฐ๊ธฐ
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

- ๊ฐ ๋ธ๋๊ฐ ๊ฐ์ง ๊ฐ์ด ํน์  ๋ฒ์์ ํฉ์ด ๋๋ฏ๋ก, ์ด๋ฅผ ๊ตฌ๊ฐ๋ณ๋ก ํ์ํ๋ฉฐ ์ ๋ต์ ๊ตฌํ๋ ๊ณผ์ 

## ์ ๋ณ๊ฒฝํ๊ธฐ
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

- index๋ฒ์งธ ์๋ฅผ val๋ก ๋ณ๊ฒฝํ๋๊ฒฝ์ฐ, index ๋ธ๋์ ํฉ์ ์ ์ฅํ๋ ๊ฒฝ์ฐ๋ง ๋ณ๊ฒฝํ๋ฉด ๋จ

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

- ๋ฆฌํ๋ธ๋๊น์ง ๋ด๋ ค๊ฐ ๋ค ์ฌ๋ผ์ค๋ฉด์ ๋ธ๋์ ํฉ์ ๋ํ๋ ๋ฐฉ๋ฒ

# ์ฐธ์กฐ
- [๋๋๋น - ์ธ๊ทธ๋จผํธ ํธ๋ฆฌ](https://m.blog.naver.com/ndb796/221282210534)
- [๋ฐฑ์ค - ์ธ๊ทธ๋จผํธ ํธ๋ฆฌ](https://book.acmicpc.net/ds/segment-tree)