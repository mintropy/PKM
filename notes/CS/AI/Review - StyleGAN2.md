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
	- droplet이 명확하지 않더라도 생성자 feature mapㅇ에서 표현됨
	- $64 \times 64$ 크기부터 나타나기 시작, 더 강해짐
- AdaIN 연산에 집중
	- 각 feature map을 normalize mean and variance
	- feature를 붕괴할 가능성 있음
	- droplet이 generator에 의한 결과라고 가설을 세움
		- 특정 부위에 통계적으로 큰 값을 부여함으로 전체 결과를 조정하기 쉬워짐
		- 정규화 단계를 삭제하자 현상이 사라짐

### 2.1. Generator architecture revisited
- revise normalization
	- AdaIN에서 평균을 제거, 표준편차만을 사용

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