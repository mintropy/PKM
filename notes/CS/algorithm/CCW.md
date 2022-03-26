---
type : knowledges
detail : 
content_type :
---

[[algorithm]]
created : 2022-03-25 21:41
tags : #🖥️note/algorithm 

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