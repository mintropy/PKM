---
type : knowledges
detail : Image Detection
content_type : note
---

[[AI]]
created : 2022-03-08 14:12
tags : #๐ฅ๏ธ #๐ฅ๏ธ/AI #๐ฅ๏ธ/AI/Note 

# Image Detection
- Image ์ ๊ฐ๋ณ ๊ฐ์ฒด๊ฐ ์๋ ๋ค์์ ๊ฐ์ฒด๋ฅผ ์ฐพ์๋ด๋ ๋ฌธ์ 
- ๋ฌผ์ฒด ๋ถ๋ฅ์ธ classification ๋ฌธ์ ์, ์์น๋ฅผ ์ฐพ๋ localization ๋ฌธ์ ๋ฅผ ๋์์ ํด์ผํ๋ ๋ถ์ผ

---
## 1-stage Detector vs 2-stage Detector
![1-stage Detector vs 2-stage Detector](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FbJgWZw%2Fbtqt1WwgYqC%2FtWhjSBbcm6wmtj9BAovgr0%2Fimg.png)

- ์๋๊ฐ 1-stage, ์๊ฐ 2-stage
- Localization, Classification ๋ ๋ฌธ์ ๋ฅผ ํด๊ฒฐํ๋๊ฒ Detection ์์์ ๊ณผ์ 
	- 1-stage๋ ๋ ๋ฌธ์ ๋ฅผ ๋์์ ์ํ
	- 2-stage๋ ๋ ๋ฌธ์ ๋ฅผ ์์ฐจ์ ์ผ๋ก ํ์
	- 1-stage๋ ๋น๊ต์  ๋น ๋ฅด๊ณ  ๋ฎ์ ์ ํ๋, 2-stage๋ ๋น๊ต์  ๋๋ฆฌ๊ณ  ๋์ ์ ํ๋
	- 1-stage์๋ ๋ํ์ ์ผ๋ก YOLO(You Only Look Once), SSD ๊ณ์ด
	- 2-stage์๋ R-CNN ๊ณ์ด

---
# ๋ผ๋ฌธ ๋ฆฌ๋ทฐ
- [[Review - YOLO]]
	- ๊ด๋ จ ์ฝ๋
		- https://github.com/wizyoung/YOLOv3_TensorFlow
		- https://github.com/zzh8829/yolov3-tf2
		- https://deepflowest.tistory.com/369
		- https://t-okk.tistory.com/2

---
# ์ฐธ์กฐ
- https://reniew.github.io/10/
- https://nuggy875.tistory.com/20
