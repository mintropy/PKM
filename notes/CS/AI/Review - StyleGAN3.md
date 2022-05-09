---
type : knowledges
detail : 
content_type :
---

[[AI]]
created : 2022-05-09 16:21
tags : #🖥️note/AI/Review  

# Review - StyleGAN3
- [[Paper - StyleGAN3]]

---
# Note

## Abstract
- 계층적 convolutional 특성에도 불구하고, GAN에 의해 진행되는 통합과정은 좋지 않은 방향으로 pixel 의존적임을 관찰함
	- 세부적인 부분이 형상 표면에 붙어 있는 것 같은 결과를 보임
	- generator에 의해 생성된 앨리어싱을 추적
- FID는 StyleGAN2와 같지만, 비디오, 애니메이션에 더 적합한 모델 생성

## 1. Introduction
- GAN으로 생성된 이미지 품질은 향상되었고, 다양한 분야에서 사용
	- 이미지 수정, 도메인 전이, 영상 생성
- 현실에서 계층적 scale 발생
	- 머리가 움직이면 코가 움직이고, 그에 따라 피부의 땀구멍 등도 따라서 움직임
	- 최근 GAN architecture에서 자연적인 계층적 이미지를 잘 합성하지 못함
		- fine feature를 위한 위치를 조정할 뿐, 정확한 위치를 나타내지 않음
	- 더 자연스러운 계층적 변환을 목표
- 이상적인 계층적 구조를 부분적으로 건너뜀
	- image border, per-pixel noise inputs, positional encodings, aliaising 등의 문제
	- 그 중, aliasing은 GAN에서 집중받는 부분 중 하나로, 그 이유를 두가지로 분석
		- nearest, bilinear, strided convolution과 같은 적절하지 않은 upsamplicing 필터레 의한 pixel grid의 faint after-images
		- pointwise 적용되는 nonlinearities 연산 (ReLU, swish)
	- 네트워크에서 aliaising을 강화하는 효과가 있고, 딥러닝의 모든 필터에 적용됨

## 2. Equivariance via continuous signal interpertation

### 2.1 Equivariant network layers

## 3. Parctial application to generator network

### 3.1 Fourer features and baseline simplifications

### 3.2 Step-by-step redesign moticated by continuous interpertation

## 4. Results

## 5. Limitations, discussion, and future work

## 6. Acknowledgments

---
# 참조
- [GitHub](https://github.com/NVlabs/stylegan3)
- [Website](https://nvlabs.github.io/stylegan3/)
- 
