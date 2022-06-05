# aib12project4

https://www.kaggle.com/datasets/divyansh22/dummy-astronomy-data

별-은하 이미지를 ResNet50을 이용해서 분류 하기

p4.ipynb 초기 진행 과정  
p4-es.ipynb early-stopping  
p4-nones.ipynb none-early-stopping  
Cutout Files 이미지 데이터  
requirments.txt pip 설치파일 ( 실제로는 코랩에서 돌려서 프로그램 설치가 필요치 않음 ) 


# 은하 별 이중 분류 모델링 - ResNet50을 이용한 딥러닝

## 주제선정  
관측 자료의 종류 구분  

## 데이터
캐글 (ps://www.kaggle.com/datasets/divyansh22/dummy-astronomy-data)  
인도에 있는 1.3m 천체망원경으로 관측한 2k*2k 이미지를 64*64 컷아웃한 자료  
은하와 별로 구분 된 4천여개의 이미지  

## 전처리  
라벨링  
훈련 검증 테스트 데이터 분할

## Resnet50 모델링  
MaxPooling Dropout BatchNormalization 옵션 추가  
AUC를 비롯한 다양한 성능 측정  
Learning rate, Early-Stopping 적용  

## 결론 및 한계
AUC ~ 0.88 성능이 좋아보이나 문제가 존재함  
과적합이 예상되어짐.  
a. 이미지에 천체가 여러개 존재하는 것이 있는데, 피팅 과정에서 이미지 중심에 큰 가중치를 넣어야했음
b. 실제 천문자료는 다양한 파장영역의 데이터를 가지고 있는데, 해당자료는 RGB만 표현함.
c. 모델링을 이미지 중심에 가중치를 주고, Fits Format 자료를 이용하면 좀더 좋은 결과를 내놓을것이라 여겨짐
