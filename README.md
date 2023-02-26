# OliveYoung product classifier
### :small_blue_diamond: Overview
 * 올리브영 화장품 30종의 이미지를 분류하는 모델 설계 
 * 추후에 이미지로 화장품을 검색하는 어플리케이션 개발
### :small_blue_diamond: Dataset
 * 총 1,8000장의 올리브영 기초케어 화장품 이미지 (총 30종, 각 class 당 600장)
 * 10개의 서로 다른 올리브영 매장에서 직접 촬영한 이미지 60% + 웹사이트에서 크롤링한 이미지 40%로 구성
### :small_blue_diamond: Modeling
 * transfer learning model - 대표적인 CNN 모델 4가지를 기반으로 한 전이학습
   * ResNet
   * MobileNet
   * VGG16
   * Xception
 * my model
   * mobileNet의 depthwise separable convolution을 활용한 경량화 모델
   * image size 1/2로 축소 (150, 200, 3) -> (75, 100, 3)
   * mobileNet보다 total parameters 1/2 이상 감소
   * mobileNet보다 예측 시간 1/2 이상 감소
### :small_blue_diamond: Evaluation
 * transfer learning model
   * MobileNet, VGG16, Xception 세 가지 모델에서 0.978 ~ 0.99의 Test Accuracy 기록 
   * ResNet의 경우 상대적으로 저조한 0.48의 Test Accuracy 기록 
   <br><br>
   <img src="https://github.com/Dasol-Choi/OliveYoung_product_img_classifier/blob/main/transfer_learning_model/metric/comparision_of_models.png?raw=true" width=55% height=55%/>
 * my model
   * 경량화한 my model에서는 최대 0.985의 Test Accuracy 기록 
   * Augmentation으로 train image를 늘려 학습을 진행해 보았지만, 정확도에 유의미한 개선은 없었음 (accuracy 0.01 정도의 개선)
   <br><br>
   <img src="https://github.com/Dasol-Choi/OliveYoung_product_img_classifier/blob/main/my_model/metric/comparision_of_models.png?raw=true" width=90% height=90%/>
