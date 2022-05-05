---
type : knowledges
detail : 
content_type :
---

[[AI]]
created : 2022-04-25 20:50
tags : #🖥️note/AI

# CNN
- 합성곱 신경망(Convolutional neural network)
- 일반적인 [[신경망]]과는 다르게 풀링 계층(pooling layer) 사용
- 인접하는 계층의 모든 뉴런과 결합되어 있는 완전연결 fully-connected 계층
	- Affine 계층이라고 부름
- 일반적으로 Affine + ReLU 등 활성화 함수의 쌍으로 이루어지는데,
	- 활성화 함수 뒤 풀링 계층을 붙여 CNN 구성

# 합성곱 계층

## 완전 연결 계층의 문제점
- 데이터의 형상이 무시됨
- 이미지는 가로, 세로, 색상 3차원의 데이터를 1차원으로 평탄화 하는 과정 발생
	- 색상, 형태 등 정보가 무시되는 현상 발생

## CNN에서 해결 방법
- 입출력 데이터를 특징 맵(feature map)이라고 함

## 합성곱 & 풀링
- [[합성곱 연산]]
- [[풀링]]
