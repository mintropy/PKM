---
type : knowledges
detail : Image Detection
content_type : review
---

[[AI]]
created : 2022-03-08 15:36
tags : #🖥️note #🖥️note/AI #🖥️note/AI/Review 

# Review - YOLO
- You Only Look Once: Unified, Real-Time Object Detection

---
# Note

---
## [[Paper - YOLO#^hga47elcrm4|Abstract]]
- 객체 검출(object detection)에 새로운 접근 방식 적용
- 기존에는 회귀(regression)으로 접근
- 이미지 전체를 하나의 신경망이 한 번의 계산으로 bounding box, class probability 예측
- 매우 빠름 (1초에 45 프레임)

---
## [[Paper - YOLO#^2myepg6djti|1. Introduction]]
- 사람 시각은 매우 빠르고 정확
	- 빠르고 정확한 알고리즘은 다양한 방면으로 유용할 수 있음
		- 자동차에 추가적엔 센서 등 없이 사용할 수 있음
		- 실시간으로 동작할 수 있음
- detection을 수행하기 위해 classifier를 목적에 맞게 적용해야함
	- 물체 탐색을 위해 각 위치별로 확인
	- 슬라이딩 윈도우를 사용하는 DPM(deformable parts models)
	- R-CNN 방식이 많이 사용


---
# 참조
- https://bkshin.tistory.com/entry/%EB%85%BC%EB%AC%B8-%EB%A6%AC%EB%B7%B0-YOLOYou-Only-Look-Once
