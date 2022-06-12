---
type : knowledges
detail : 
content_type :
---

[[algorithm]]
created : 2022-03-25 21:41
tags : #🖥️Note/algorithm 

# CCW
- CCW(Counter Clockwise)
- 평면위의 세 점의 방향관계를 구하는 알고리즘
- 세 점, A, B, C 를 순서로 생각했을 때, 반시계 방향이면 양수, 시계 방향이면 음수, 평행하면 0
- $\vec{a}$ = $\vec{AB}$, $\vec{b}$ = $\vec{BC}$ 라 두고 계산

## 외적
- $\times$ 기호를 사용하여 계산, 두 벡터와 동시에 수직인 벡터를 구할 수 있음
	- 이 수직 벡터를 활용하여 세 점의 방향 관계 판단할 수 있음
- $\vec{n}$ 을 $\vec{a}$ , $\vec{b}$ 에 수직인 벡터라 하고, $\theta$를 사이 각이라 하면
$$\vec{a}\times\vec{b} = (\vert\vec{a}\vert\vert\vec{b}\vert \sin \theta)\vec{n}, (0 \leq \theta \leq \pi) $$
- 이 때, $\theta=0$ 또는 $\theta=\pi$이면 외적의 결과는 0이므로 세 점이 하나의 직선 위에 있음
- 그 외의 경우 ?
	- $x_1y_2 - x_2y_1$ 가 양수이면 반시계 방향, 음수이면 시계 방향

# 선분 교차 판별
- 두 선분 $L_1, L_2$, 각 점을 $A, B, C, D$라고 했을 때, $A, B, C$의 CCW 값과 $A, B, D$의 CCW값을 곱하여 생각할 수 있음
- 세 점의 좌표를 $(x_1, y_1), (x_2, y_2), (x_3, y_3)$ 이라고 하면, $$CCW = (x_2 - x_1)(y_3 - y_1) - (y_2 - y_1)(x_3 - x_1)$$
- 두 값이 모두 0이 되면 두 선분은 하나의 직선 위에 있음
	- 이 때, 두 선분이 교차하는지는 검증해야 함
- 두 값의 곱이 양수이면 교차하지 않고, 음수이면 교차할 가능성이 있음

## 관련 문제
- 백준 선분교차
	- [백준 선분교차 3](https://www.acmicpc.net/problem/20149)
