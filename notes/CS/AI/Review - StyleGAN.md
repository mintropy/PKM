---
type : knowledges
detail : 
content_type :
---

[[AI]]
created : 2022-04-29 14:35
tags : #🖥️note/AI/Review 

# Review - StyleGAN
- [[paper - StyleGAN]]
- A Style-Based Generator Architecture for Generative Adversarial Networks

---
# Note

---
## Abstract
- style transfer아이디어를 활용한 GAN 모델
- high-level attribute 분류를 도와주고, stochastic variation을 다양하게 적용할 수 있음
	- high-level attribute : 사람의 자세, 얼굴에 대한 정보
	- stochatic variation : 동일한 사람의 이미지여도, 구성 요소는 확률적으로 다양한 방식을 통해 달라질 수 있음
- interpolation quality와 disentanglement 수치를 확인할 수 인ㄴ는 2가지 방법
- 고해상도 사람 얼굴 이미지 데이터셋(FFHQ)

## 1. Introduction
- GAN으로 생성한 이미지는 품질이 향상되었지만, 현실적인 이미지 생성은 불완전해 보임
- generator의 블랙박스를 연구하는 노력이 있음
	- stochastic featrues 등
	- 하지만 아직 이해도가 부족한 것 같음
- style transfer에 영감을 받았고, 생성자 아키텍처를 디자인함

## 2. Style-based generator
- 

### 2.1 Quality of generated images

### 2.2 Prior art

## 3. Properties of the style-based generator

### 3.1 Style mixing

### 3.2 Stochastic variation

### 3.3 Separation of global effects from stochasticity

## 4. Disentanglement studies

### 4.1. perceptual path length

### 4.2. Linear separability

## 5. Conclusion


---
# 참조
- [GitHub](https://github.com/NVlabs/stylegan)
- 논문 리뷰
	- [리뷰1]https://velog.io/@ghgh5317/A-Style-Based-Generator-Architecture-for-Generative-Adversarial-Networks-review
		- [리뷰 1 해설](https://velog.io/@ghgh5317/StyleGAN-v1-%EA%B0%84%EB%8B%A8%ED%95%98%EA%B2%8C-%EC%A0%95%EB%A6%AC)
	- [리뷰2](https://blog.promedius.ai/stylegan_1/)
