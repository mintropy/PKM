---
type : knowledges
detail : Image Detection
content_type : review
---

[[AI]]
created : 2022-03-08 15:36
tags : #๐ฅ๏ธ #๐ฅ๏ธ/AI #๐ฅ๏ธ/AI/Review 

# Review - YOLO
- You Only Look Once: Unified, Real-Time Object Detection

---
# Note

---
## [[Paper - YOLO#^hga47elcrm4|Abstract]]
- ๊ฐ์ฒด ๊ฒ์ถ(object detection)์ ์๋ก์ด ์ ๊ทผ ๋ฐฉ์ ์ ์ฉ
- ๊ธฐ์กด์๋ ํ๊ท(regression)์ผ๋ก ์ ๊ทผ
- ์ด๋ฏธ์ง ์ ์ฒด๋ฅผ ํ๋์ ์ ๊ฒฝ๋ง์ด ํ ๋ฒ์ ๊ณ์ฐ์ผ๋ก bounding box, class probability ์์ธก
- ๋งค์ฐ ๋น ๋ฆ (1์ด์ 45 ํ๋ ์)

---
## [[Paper - YOLO#^2myepg6djti|1. Introduction]]
- ์ฌ๋ ์๊ฐ์ ๋งค์ฐ ๋น ๋ฅด๊ณ  ์ ํ
	- ๋น ๋ฅด๊ณ  ์ ํํ ์๊ณ ๋ฆฌ์ฆ์ ๋ค์ํ ๋ฐฉ๋ฉด์ผ๋ก ์ ์ฉํ  ์ ์์
		- ์๋์ฐจ์ ์ถ๊ฐ์ ์ ์ผ์ ๋ฑ ์์ด ์ฌ์ฉํ  ์ ์์
		- ์ค์๊ฐ์ผ๋ก ๋์ํ  ์ ์์
- detection์ ์ํํ๊ธฐ ์ํด classifier๋ฅผ ๋ชฉ์ ์ ๋ง๊ฒ ์ ์ฉํด์ผํจ
	- ๋ฌผ์ฒด ํ์์ ์ํด ๊ฐ ์์น๋ณ๋ก ํ์ธ
	- ์ฌ๋ผ์ด๋ฉ ์๋์ฐ๋ฅผ ์ฌ์ฉํ๋ DPM(deformable parts models)
	- R-CNN ๋ฐฉ์์ด ๋ง์ด ์ฌ์ฉ


---
# ์ฐธ์กฐ
- https://bkshin.tistory.com/entry/%EB%85%BC%EB%AC%B8-%EB%A6%AC%EB%B7%B0-YOLOYou-Only-Look-Once
