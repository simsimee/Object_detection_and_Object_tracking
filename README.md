# Object_detection_and_Object_tracking


## 프로젝트 기획
- 테슬라의 FSD나 구글의 웨이모와 같은 무인택시의 자율주행을 처음봤을 때 "와 이게 된다고?" 하는 신기함으로 처음 관심을 가지게 되었고 어떤 방식으로 자율주행이 가능한 지 직접 구현해보고자 프로젝트를 기획
- 라이다를 이용한 자율주행도 있으나 비싼 라이다를 쓰지않고 카메라만을 이용하여 자율주행을 구현하기위한 기술을 구현

## 사용한 라이브러리, 툴
- Yolo
- Darknet
- OpenCV

## 구현한 기술
- Object detection
- lane detection
- Object tracking

## Object detection & lane detection
- Yolov3 와 OpenCV를 이용하여 [Berkley-Deepdrive]('https://bdd-data.berkeley.edu')의 영상을 Object detection 및 lane detection 진행
![무제](https://user-images.githubusercontent.com/75903850/138563909-15400aad-c3a6-4808-8af2-42cc770fc5c4.gif)

### lane detection 방법
1. 원본 영상 읽어오기
2. 원본 영상에 Grayscale 적용
3. Gaussian Blur를 이용하여 노이즈 제거
4. Canny Edge Detection으로 이미지의 Edge들을 추출
5. 원하는 범위의 엣지만 얻어내기 위해 ROI(Region Of Interest) 관심영역 지정
6. Hough 변환을 이용하여 검출된 영상에서 직선 성분을 추출하여 Lane Detection

## Object tracking
![스크린샷 2021-10-24 오전 1 51 01](https://user-images.githubusercontent.com/75903850/138564923-0cef1a84-2cd9-4b60-87d1-4c1d47cd2904.png)

앞에 있는 차를 tracking 하고 임의의 박스 2개를 만들어 물체를 tracking하며 detection 하고있는 박스와 임의 박스의 넒이 차를 이용해 차간거리를 측정하여
Speed up, Slow down, Be Careful 세 가지의 경우로 문구가 뜨도록 구현하였습니다.

![화면 기록 2021-10-24 오후 2 35 46](https://user-images.githubusercontent.com/75903850/138582296-7a6f03d0-6994-436c-9dd1-dd98a5a5d480.gif)

### 차후 개선 방향
- 영상이 아닌 라즈베리파이의 카메라 모듈을 이용한 실시간 영상에 대해 Object Detection, Tracking을 진행해보기
- Yolov3가 아닌 최신 Yolo 모델을 이용해보기
- lane detection, Object detection, Object tracking을 하나의 영상에서 적용시키기
