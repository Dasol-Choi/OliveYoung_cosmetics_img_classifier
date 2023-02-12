# OliveYoung product classification
### 프로젝트 개요
 * 이미지를 통해 올리브영 화장품 정보를 제공하는 서비스 구현
### Dataset
 * 총 30종, 각각 600장의 올리브영 기초케어 화장품 이미지 (총 1,8000장)  
 * 10개의 서로 다른 올리브영 매장에서 직접 촬영한 이미지 60%, 웹사이트에서 크롤링한 이미지 40%로 구성
### Modeling
 * transfer learning model - 대표적인 CNN 모델 4가지를 기반으로 한 전이학습
   * resNet
   * mobileNet
   * VGG16
   * Xception
 * my model
   * mobileNet의 depthwise 층을 활용한 경량화 모델
   * image size 1/2로 축소
### 평가
 * mobileNet, VGG16, Xception 세 가지 모델에서 최대 0.98의 Accuracy 기록 
 * ResNet의 경우 상대적으로 저조한 0.56의 Accuracy 기록 
 * 경량화한 모델에서는 최대 0.95의 Accuracy 기록 -> 추후 성능 향상 시도 예정 
