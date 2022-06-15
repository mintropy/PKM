---
type : knowledges
detail : 
content_type :
---

[[AI]]
created : 2022-03-09 16:50
tags : #🖥️/AI/Review  

# Review - BERT
- Pre-training of Deep Bidirectional Transformers for Language Understanding

---
# Note

---
## [[paper - BERT#^2u26epoo7bn|Abstract]]
- pre-train → fine-tuned 으로 SOTA 달성

---
## [[paper - BERT#^gom72aonwvl|1 Introduction]]
- pre-trained 의 표현 방식으로 feature-based, fine-tuning 이 있음
- feature-based approach
	- ELMo
- fine-tuning approach
	- Generatice Pre-trained Transformer (OpenAI GPT)
- 기존 언어 모델은 단방향(unidirectional)
	- OpenAI GPT의 경우 왼쪽에서 오른쪽으로 보는 방식
	- 모든 토큰이 Transformer의  self-attention에서 이전 토큰에만 참여
- BERT를 적용 (Transformer의 양방향 Encoder 표현)
	- 단방향과 관련한 문제를 MLM(masked language model) pre-training 으로 접근
	- 임의로 입력의 토큰을을 mask하여 예측
	- 기존 왼쪽에서 오른쪽으로 바라보는 pre-trainging 언어 모델과 달리, MLM은 양방향 참조를 가능하게 함
	- 추가적으로 다음 문장 예측 작업을 함

---
## [[paper - BERT#^246loi456bu|2 Related Work]]
### 2.1 Unsupervised Feature-based Approaches

### 2.2 Unsupervised Fine-tuning Approaches

### 2.3 Transfer Learning from Supervised Data

---
## [[paper - BERT#^bdlxr4lwsym|3 BERT]]
- fine-tuning

---
# 참조 
