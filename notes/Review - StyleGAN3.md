---
type : knowledges
detail : 
content_type :
---

[[AI]]
created : 2022-05-09 16:21
tags : #🖥️Note/AI/Review  

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
- 이러한 정보 제거하는 방법?
- StyleGAN3 generator는 StyleGAN2의 FID와 같지만, 더 많은 연산을 함

## 2. Equivariance via continuous signal interpertation
- 네트워크를 따라 흐르는 시그널이 무엇인지 생각해봐야함
	- 각 픽셀에 저장된 값을 단순 계산할수는 없음
- nyquist-shannon sampling theorem에 따르면 2배 이상의 sampling frequency로 샘플링해야 복원할 때 원상태로 복원 가능
- whittaker-shannon interpolation formula에 따르면 ideal interpolation filter를 convolving해서 discrete에서 continuous로 복원 가능

### 2.1 Equivariant network layers
- $f$ 함수는 equivariant
	- $t \circ f = f \circ t$를 만족

#### convolution

#### Upsamapling and downsampling

#### Nonlinearity

## 3. Parctial application to generator network
- StyleGAN2의 generator를 translation and rotation equivariant 하게 변환, discriminator는 고정
- StyleGAN2 generator는 두 부분으로 이루어짐
	- mapping network : 초기 일반적인 distributed latent를 intermediate latent로 변환
	- synthesis network : 출력 이미지를 생성하기 위해 $4 \times 4 \times 512$ constant와 N개 레이어 순열을 사용
- Measure

$$
EQ-T = 10 \cdot log_{10} (I^2_{max} / \mathbb{E}_{w \sim \mathit{W}, x \sim \mathit{X^2}, p \sim \mathit{V}, c \sim \mathit{C}} [(g(t_x [z_0];w)_c (p) - t_x [g(z_0;w)]_c (p))^2])
$$

- translation equivariance를 위한 measuer가 필요
	- PSNR(peak signal-nosie ratio, 최대 신호 대 잡음비)를 약간 변형한 measuer 제안

### 3.1 Fourer features and baseline simplifications
- StyleGAN3은 StyleGAN2와 다르게 constant 가 아니라 fourier feature 사용
	- fourier feature는 implicit representation task에서 low dimensional input이 들어올 때 high frequency 정보를 학습할 수 있게 도와주는 방법이라 잘 맞는 거 같음
	- FID 증가하였고, 이러한 시작점은 equivariant와는 거리가 멀다
- per-pixel noise input을 제거
	- 자연스러운 계층적 전이와는 거리가 멀다
- simplify setup을 위해 mapping network 깊이를 감소시키고, mixing regularization & path length regularization을 하지 않도록 함
	- mapping network 깊이를 8에서 2로 줄임
	- mixing regularization(style mixing) 제거
		- 단순한 데이터셋에서는 효과가 있지만, 복잡하고 multi-model인 데이터셋에서 악효과
	- path length regularization 제거
		- 잠재공간의 변화에 패널티 부여하여 texture sticking 유발
	- skip connection 제거

### 3.2 Step-by-step redesign moticated by continuous interpertation

#### Boundaries and upsampling

#### Filtered nonlinearities

#### Non-critical sampling

#### Transformed Fourier features

#### Flexible layer specifications

#### Rotation equivariance

## 4. Results

## 5. Limitations, discussion, and future work

## 6. Acknowledgments

---
# 참조
- [GitHub](https://github.com/NVlabs/stylegan3)
- [Website](https://nvlabs.github.io/stylegan3/)
- [논문 리뷰](https://happy-jihye.github.io/gan/gan-33/)
- [논문 리뷰](https://deepseow.tistory.com/59)
- [리뷰](https://ostin.tistory.com/53)
