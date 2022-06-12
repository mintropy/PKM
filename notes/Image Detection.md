---
type : knowledges
detail : Image Detection
content_type : note
---

[[AI]]
created : 2022-03-08 14:12
tags : #🖥️Note #🖥️Note/AI #🖥️Note/AI/Note 

# Image Detection
- Image 의 개별 객체가 아닌 다수의 객체를 찾아내는 문제
- 물체 분류인 classification 문제와, 위치를 찾는 localization 문제를 동시에 해야하는 분야

---
## 1-stage Detector vs 2-stage Detector
![1-stage Detector vs 2-stage Detector](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FbJgWZw%2Fbtqt1WwgYqC%2FtWhjSBbcm6wmtj9BAovgr0%2Fimg.png)

- 아래가 1-stage, 위가 2-stage
- Localization, Classification 두 문제를 해결하는게 Detection 에서의 과제
	- 1-stage는 두 문제를 동시에 수행
	- 2-stage는 두 문제를 순차적으로 탐색
	- 1-stage는 비교적 빠르고 낮은 정확도, 2-stage는 비교적 느리고 높은 정확도
	- 1-stage에는 대표적으로 YOLO(You Only Look Once), SSD 계열
	- 2-stage에는 R-CNN 계열

---
# 논문 리뷰
- [[Review - YOLO]]
	- 관련 코드
		- https://github.com/wizyoung/YOLOv3_TensorFlow
		- https://github.com/zzh8829/yolov3-tf2
		- https://deepflowest.tistory.com/369
		- https://t-okk.tistory.com/2

---
# 참조
- https://reniew.github.io/10/
- https://nuggy875.tistory.com/20
