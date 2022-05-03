---
type : knowledges
detail : 
content_type :
---

[[AI]]
created : 2022-05-02 11:04
tags : #🖥️note/AI/Review 

# Review - StyleGAN2
- [[Paper - StyleGAN2]]

---
# Note
## Abstract
- StyleGAN은 data-driven, unconditional 이미지 생성 모델로 SOTA달성
	- 몇가지 특징을 노출, 분석하여 훈련방법은 제안
	- generator normalization을 다시 디자인하여, 잠재적인 부분은 이미지로 옮김

## 1. Introduction
- GAN을 활용한 생성 방식은 빠르게 발전
	- StyleGAN을 통하여 고해상도 이미지 생성에서 SOTA 달성
	- StyleGAN에서 input latent code를 사용한 대신 mapping network f를 도입
		- intermediate latent code w를 위해
	- Affine transform을 사용하여 style응 생성, AdaIN을 통하여 synthesis network g를 조정
	- stochastic variation이 임의의 noise를 synthesis network로 변환
- 기존 StyleGAN 두가지 문제 발견
	- blob-like artifacts
	- progressive prowing과 관련하여 분석
- method
	- FID(Frechet inception distance)
	- P&R(Precision and Recall)
	- PPL(perceptual path length)

## 2. Removing normalization artifacts
- StyleGAN로 생성된 이미지의 가장 큰 문제는 blob-shaped artifact

### 2.1. Generator architecture revisited

### 2.2. Instance normalization revisited

## 3. Image quality and generator smoothness

### 3.1. Lazy regularization

### 3.2. Path length regularization

## 4. Progressive growing revisited

### 4.1. Alternative network architectures

### 4.2. Resolution usage

## 5. Projection of images to latent space

### 5.1. Attribution of generated images

## 6. Conclusions and future work

---
# 참조
- [GitHub](https://github.com/NVlabs/stylegan2)
- [논문 리뷰](https://aruie.github.io/2020/02/23/styleganv2.html)
- [논문 리뷰](https://iamseungjun.tistory.com/6)
- [논문 리뷰](https://happy-jihye.github.io/gan/gan-7/)