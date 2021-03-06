---
type : knowledges
detail : 
content_type :
---

[[AI]]
created : 2022-04-29 14:35
tags : #๐ฅ๏ธ/AI/Review 

# Review - StyleGAN
- [[paper - StyleGAN]]
- A Style-Based Generator Architecture for Generative Adversarial Networks

---
# Note

---
## Abstract
- style transfer์์ด๋์ด๋ฅผ ํ์ฉํ GAN ๋ชจ๋ธ
	- descriminator, loss function์ ์์ ํ์ง ์๊ณ  generator๋ฅผ ๋ ํจ์จ์ ์ผ๋ก ๋ง๋ฌ
- high-level attribute ๋ถ๋ฅ๋ฅผ ๋์์ฃผ๊ณ , stochastic variation์ ๋ค์ํ๊ฒ ์ ์ฉํ  ์ ์์
	- high-level attribute : ์ฌ๋์ ์์ธ, ์ผ๊ตด์ ๋ํ ์ ๋ณด
	- stochatic variation : ๋์ผํ ์ฌ๋์ ์ด๋ฏธ์ง์ฌ๋, ๊ตฌ์ฑ ์์๋ ํ๋ฅ ์ ์ผ๋ก ๋ค์ํ ๋ฐฉ์์ ํตํด ๋ฌ๋ผ์ง ์ ์์
- interpolation quality์ disentanglement ์์น๋ฅผ ํ์ธํ  ์ ์๋ 2๊ฐ์ง ๋ฐฉ๋ฒ
	- perceptual path length, linear separability
- ๊ณ ํด์๋ ์ฌ๋ ์ผ๊ตด ์ด๋ฏธ์ง ๋ฐ์ดํฐ์(FFHQ)

## 1. Introduction
- GAN์ผ๋ก ์์ฑํ ์ด๋ฏธ์ง๋ ํ์ง์ด ํฅ์๋์์ง๋ง, ํ์ค์ ์ธ ์ด๋ฏธ์ง ์์ฑ์ ๋ถ์์ ํด ๋ณด์
- generator์ ๋ธ๋๋ฐ์ค๋ฅผ ์ฐ๊ตฌํ๋ ๋ธ๋ ฅ์ด ์์
	- stochastic featrues ๋ฑ
	- ํ์ง๋ง ์์ง ์ดํด๋๊ฐ ๋ถ์กฑํ ๊ฒ ๊ฐ์
- style transfer์ ์๊ฐ์ ๋ฐ์๊ณ , ์์ฑ์ ์ํคํ์ฒ๋ฅผ ๋์์ธํจ

## 2. Style-based generator
- ์ ํต์ ์ธ ๋ฐฉ์์, latent vector๊ฐ ์๋ ฅ๊ฐ์ผ๋ก ๋ค์ด๊ฐ๋ฉฐ ๋ค์ํ ์ด๋ฏธ์ง๊ฐ ์์ฑ๋๋๋ก ํจ
	- style-based generator๋ ๋ณ๋์ style์ ๋ณด๋ฅผ layer๋ฅผ ๊ฑฐ์น  ๋๋ง๋ค ๋ฃ์ด์ฃผ๊ธฐ ๋๋ฌธ์, latent vector๋ฅผ ์๋ ฅ์ผ๋ก ๋ฃ์ด์ฃผ์ง ์์๋ ๋จ
	- latent vector๋ฅผ non linear mapping์ ํตํ์ฌ 512์ฐจ์ ๋ฒกํฐ๋ก ๋ณํ, ์ค์  ์๋ ฅ๊ฐ์ด ๋จ
	- ์ฌ๋ ์ด๋ฏธ์ง์์ ์กฐ๊ธ์ฉ ๋ฐ๋ ์ ์๋ face, skin, hair (=stochastic variation)์ ์ฒ๋ฆฌํ  ์ ์๋ noise์ ๋ํ vector๋ ์ถ๊ฐ
- AdaIN ์ ํ์ฉํ style  transfer network
	- style transfer network์์ normalization์ ํจ๊ณผ์ ์ผ๋ก ์ฌ์ฉํ  ์ ์๋ ๋ฐฉ๋ฒ ์ค ํ๋
	- ํ๋์ feature์ ๋ํ ์ ๋ณด๋ฅผ scaling, bias๋ฅผ ์ ์ฉํ๋ฉฐ ์๋ ฅ๋ฐ์ ์คํ์ผ์ statistics๋ฅผ ์ด์ฉํ์ฌ, feature์ ๋ํ statistics๋ฅผ ๋ฐ๊ฟ ์ ์๋๋ก ํจ

### 2.1 Quality of generated images

### 2.2 Prior art
- ๋๋ถ๋ถ GAN์ด discriminator์ ์ง์ค
	- multiple discriminators, multiresolution discrimination, self-attention ๋ฑ
- generator์ ๊ด๋ จํด์๋ ์ ํํ distribution์ ๋ชฉํ๋ก ํจ

## 3. Properties of the style-based generator

### 3.1 Style mixing

### 3.2 Stochastic variation

### 3.3 Separation of global effects from stochasticity

## 4. Disentanglement studies

### 4.1. perceptual path length

### 4.2. Linear separability

## 5. Conclusion


---
# ์ฐธ์กฐ
- [GitHub](https://github.com/NVlabs/stylegan)
- ๋ผ๋ฌธ ๋ฆฌ๋ทฐ
	- [๋ผ๋ฌธ ๋ฆฌ๋ทฐ]https://velog.io/@ghgh5317/A-Style-Based-Generator-Architecture-for-Generative-Adversarial-Networks-review
		- [๋ฆฌ๋ทฐ ํด์ค](https://velog.io/@ghgh5317/StyleGAN-v1-%EA%B0%84%EB%8B%A8%ED%95%98%EA%B2%8C-%EC%A0%95%EB%A6%AC)
	- [๋ผ๋ฌธ ๋ฆฌ๋ทฐ](https://blog.promedius.ai/stylegan_1/)
