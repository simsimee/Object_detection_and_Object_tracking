# Object_detection_and_Object_tracking


## 프로젝트 기획
- 테슬라의 FSD나 구글의 웨이모와 같은 무인택시의 자율주행을 처음봤을 때 "와 이게 된다고?" 하는 신기함으로 처음 관심을 가지게 되었고 어떤 방식으로 자율주행이 가능한 지 직접 구현해보고자 프로젝트를 기획
- 라이다를 이용한 자율주행도 있으나 비싼 라이다를 쓰지않고 카메라만을 이용하여 자율주행을 구현하기위한 기술을 구현

## 사용한 라이브러리, 툴
- Yolo
- darknet
- OpenCV

## 구현한 기술
- Object detection
- lane detection
- Object tracking

### Object detection & lane detection
- Yolov3 와 OpenCV를 이용하여 [Berkley-Deepdrive]('https://bdd-data.berkeley.edu')의 영상을 Object detection 및 lane detection 실행
- <img width="80%" src="https://user-images.githubusercontent.com/16822641/109461495-913fc480-7aa5-11eb-9d0e-aff762669f98.gif"/>
