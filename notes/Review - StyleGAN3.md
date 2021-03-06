---
type : knowledges
detail : 
content_type :
---

[[AI]]
created : 2022-05-09 16:21
tags : #๐ฅ๏ธ/AI/Review  

# Review - StyleGAN3
- [[Paper - StyleGAN3]]

---
# Note

## Abstract
- ๊ณ์ธต์  convolutional ํน์ฑ์๋ ๋ถ๊ตฌํ๊ณ , GAN์ ์ํด ์งํ๋๋ ํตํฉ๊ณผ์ ์ ์ข์ง ์์ ๋ฐฉํฅ์ผ๋ก pixel ์์กด์ ์์ ๊ด์ฐฐํจ
	- ์ธ๋ถ์ ์ธ ๋ถ๋ถ์ด ํ์ ํ๋ฉด์ ๋ถ์ด ์๋ ๊ฒ ๊ฐ์ ๊ฒฐ๊ณผ๋ฅผ ๋ณด์
	- generator์ ์ํด ์์ฑ๋ ์จ๋ฆฌ์ด์ฑ์ ์ถ์ 
- FID๋ StyleGAN2์ ๊ฐ์ง๋ง, ๋น๋์ค, ์ ๋๋ฉ์ด์์ ๋ ์ ํฉํ ๋ชจ๋ธ ์์ฑ

## 1. Introduction
- GAN์ผ๋ก ์์ฑ๋ ์ด๋ฏธ์ง ํ์ง์ ํฅ์๋์๊ณ , ๋ค์ํ ๋ถ์ผ์์ ์ฌ์ฉ
	- ์ด๋ฏธ์ง ์์ , ๋๋ฉ์ธ ์ ์ด, ์์ ์์ฑ
- ํ์ค์์ ๊ณ์ธต์  scale ๋ฐ์
	- ๋จธ๋ฆฌ๊ฐ ์์ง์ด๋ฉด ์ฝ๊ฐ ์์ง์ด๊ณ , ๊ทธ์ ๋ฐ๋ผ ํผ๋ถ์ ๋๊ตฌ๋ฉ ๋ฑ๋ ๋ฐ๋ผ์ ์์ง์
	- ์ต๊ทผ GAN architecture์์ ์์ฐ์ ์ธ ๊ณ์ธต์  ์ด๋ฏธ์ง๋ฅผ ์ ํฉ์ฑํ์ง ๋ชปํจ
		- fine feature๋ฅผ ์ํ ์์น๋ฅผ ์กฐ์ ํ  ๋ฟ, ์ ํํ ์์น๋ฅผ ๋ํ๋ด์ง ์์
	- ๋ ์์ฐ์ค๋ฌ์ด ๊ณ์ธต์  ๋ณํ์ ๋ชฉํ
- ์ด์์ ์ธ ๊ณ์ธต์  ๊ตฌ์กฐ๋ฅผ ๋ถ๋ถ์ ์ผ๋ก ๊ฑด๋๋
	- image border, per-pixel noise inputs, positional encodings, aliaising ๋ฑ์ ๋ฌธ์ 
	- ๊ทธ ์ค, aliasing์ GAN์์ ์ง์ค๋ฐ๋ ๋ถ๋ถ ์ค ํ๋๋ก, ๊ทธ ์ด์ ๋ฅผ ๋๊ฐ์ง๋ก ๋ถ์
		- nearest, bilinear, strided convolution๊ณผ ๊ฐ์ ์ ์ ํ์ง ์์ upsamplicing ํํฐ๋  ์ํ pixel grid์ faint after-images
		- pointwise ์ ์ฉ๋๋ nonlinearities ์ฐ์ฐ (ReLU, swish)
	- ๋คํธ์ํฌ์์ aliaising์ ๊ฐํํ๋ ํจ๊ณผ๊ฐ ์๊ณ , ๋ฅ๋ฌ๋์ ๋ชจ๋  ํํฐ์ ์ ์ฉ๋จ
- ์ด๋ฌํ ์ ๋ณด ์ ๊ฑฐํ๋ ๋ฐฉ๋ฒ?
- StyleGAN3 generator๋ StyleGAN2์ FID์ ๊ฐ์ง๋ง, ๋ ๋ง์ ์ฐ์ฐ์ ํจ

## 2. Equivariance via continuous signal interpertation
- ๋คํธ์ํฌ๋ฅผ ๋ฐ๋ผ ํ๋ฅด๋ ์๊ทธ๋์ด ๋ฌด์์ธ์ง ์๊ฐํด๋ด์ผํจ
	- ๊ฐ ํฝ์์ ์ ์ฅ๋ ๊ฐ์ ๋จ์ ๊ณ์ฐํ ์๋ ์์
- nyquist-shannon sampling theorem์ ๋ฐ๋ฅด๋ฉด 2๋ฐฐ ์ด์์ sampling frequency๋ก ์ํ๋งํด์ผ ๋ณต์ํ  ๋ ์์ํ๋ก ๋ณต์ ๊ฐ๋ฅ
- whittaker-shannon interpolation formula์ ๋ฐ๋ฅด๋ฉด ideal interpolation filter๋ฅผ convolvingํด์ discrete์์ continuous๋ก ๋ณต์ ๊ฐ๋ฅ

### 2.1 Equivariant network layers
- $f$ ํจ์๋ equivariant
	- $t \circ f = f \circ t$๋ฅผ ๋ง์กฑ

#### convolution

#### Upsamapling and downsampling

#### Nonlinearity

## 3. Parctial application to generator network
- StyleGAN2์ generator๋ฅผ translation and rotation equivariant ํ๊ฒ ๋ณํ, discriminator๋ ๊ณ ์ 
- StyleGAN2 generator๋ ๋ ๋ถ๋ถ์ผ๋ก ์ด๋ฃจ์ด์ง
	- mapping network : ์ด๊ธฐ ์ผ๋ฐ์ ์ธ distributed latent๋ฅผ intermediate latent๋ก ๋ณํ
	- synthesis network : ์ถ๋ ฅ ์ด๋ฏธ์ง๋ฅผ ์์ฑํ๊ธฐ ์ํด $4 \times 4 \times 512$ constant์ N๊ฐ ๋ ์ด์ด ์์ด์ ์ฌ์ฉ
- Measure

$$
EQ-T = 10 \cdot log_{10} (I^2_{max} / \mathbb{E}_{w \sim \mathit{W}, x \sim \mathit{X^2}, p \sim \mathit{V}, c \sim \mathit{C}} [(g(t_x [z_0];w)_c (p) - t_x [g(z_0;w)]_c (p))^2])
$$

- translation equivariance๋ฅผ ์ํ measuer๊ฐ ํ์
	- PSNR(peak signal-nosie ratio, ์ต๋ ์ ํธ ๋ ์ก์๋น)๋ฅผ ์ฝ๊ฐ ๋ณํํ measuer ์ ์

### 3.1 Fourer features and baseline simplifications
- StyleGAN3์ StyleGAN2์ ๋ค๋ฅด๊ฒ constant ๊ฐ ์๋๋ผ fourier feature ์ฌ์ฉ
	- fourier feature๋ implicit representation task์์ low dimensional input์ด ๋ค์ด์ฌ ๋ high frequency ์ ๋ณด๋ฅผ ํ์ตํ  ์ ์๊ฒ ๋์์ฃผ๋ ๋ฐฉ๋ฒ์ด๋ผ ์ ๋ง๋ ๊ฑฐ ๊ฐ์
	- FID ์ฆ๊ฐํ์๊ณ , ์ด๋ฌํ ์์์ ์ equivariant์๋ ๊ฑฐ๋ฆฌ๊ฐ ๋ฉ๋ค
- per-pixel noise input์ ์ ๊ฑฐ
	- ์์ฐ์ค๋ฌ์ด ๊ณ์ธต์  ์ ์ด์๋ ๊ฑฐ๋ฆฌ๊ฐ ๋ฉ๋ค
- simplify setup์ ์ํด mapping network ๊น์ด๋ฅผ ๊ฐ์์ํค๊ณ , mixing regularization & path length regularization์ ํ์ง ์๋๋ก ํจ
	- mapping network ๊น์ด๋ฅผ 8์์ 2๋ก ์ค์
	- mixing regularization(style mixing) ์ ๊ฑฐ
		- ๋จ์ํ ๋ฐ์ดํฐ์์์๋ ํจ๊ณผ๊ฐ ์์ง๋ง, ๋ณต์กํ๊ณ  multi-model์ธ ๋ฐ์ดํฐ์์์ ์ํจ๊ณผ
	- path length regularization ์ ๊ฑฐ
		- ์ ์ฌ๊ณต๊ฐ์ ๋ณํ์ ํจ๋ํฐ ๋ถ์ฌํ์ฌ texture sticking ์ ๋ฐ
	- skip connection ์ ๊ฑฐ

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
# ์ฐธ์กฐ
- [GitHub](https://github.com/NVlabs/stylegan3)
- [Website](https://nvlabs.github.io/stylegan3/)
- [๋ผ๋ฌธ ๋ฆฌ๋ทฐ](https://happy-jihye.github.io/gan/gan-33/)
- [๋ผ๋ฌธ ๋ฆฌ๋ทฐ](https://deepseow.tistory.com/59)
- [๋ฆฌ๋ทฐ](https://ostin.tistory.com/53)
