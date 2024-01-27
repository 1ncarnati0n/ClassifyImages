# 이미지 기반 제품 결함 탐지
"AI Connect 모의경진대회" 

제품 이미지에 결함이 존재하는지 여부를 판별하는 과제

**주최**: 중소벤처기업진흥공단

**주관**: 마인즈앤컴퍼니 (AI Connect)

<br>

## OverView

### 대회소개:
Texture surface에 존재하는 결함 여부를 탐지합니다. 결함/정상 여부를 분류하는 Binary Classification 문제입니다.

**제한사항**: 외부데이터 사용불가

**참여기간**: 2023.09.27 ~ 10.06

**참여방식**: 개인

<br>

## 데이터

### 데이터 구조
```
data
├ train
│  ├ defect_images
│  │  ├ defect_0000.png 
│  │  ├ defect_0001.png
│  │  └ ...
│  ├ defect_masks
│  │  ├ defect_0000.png 
│  │  ├ defect_0001.png
│  │  └ ...
│  └ normal_images
│     ├ normal_0000.png
│     ├ normal_0001.png
│     └ ...
│
└ test
   ├ images
   │  ├ test_0000.png 
   │  ├ test_0001.png
   │  └ ...
   └ sample_submission.csv
```

### 데이터 설명

**traing data**
- train / defect_images: 결함 제품 이미지 (30장) 
- train / defect_masks: 결함 부분 세그멘테이션 마스크 (30장) 
- train / normal_images: 정상 제품 이미지 (6,790장)

<br>

**test data**
- test / images: 결함/정상 포함 이미지(9,100장)

<p align='center'><img src="assets/src03.png" width="540"></p>

<br>

**sample_submission.csv** (9100 rows X 2 columns)
- test/images에 존재하는 테스트 이미지 9,100장에 대한 판별 결과 (정상 : 0, 결함 1)을 제출.
- 컬럼명 일치 필수 (ImageId, answer)
- shape 일치 필수 (9100, 2)

<br>

## 평가지표

- Macro F1 Scores: 각 클래스의 F1 Score의 단순 평균.

<br>

$$ F1 \ Score = \frac{2}{\frac{1}{Precison} + \frac{1}{Recall}} = 2 \ ⨉ \ \frac{Precision \ ⨉ \ Recall}{Precision \ + \ Recall} $$

<br>

<p align='center'><img src="assets/src01.png" width="540"></p>

- Considers both Precision and Recall, Precision과 Recall의 조화평균 평균 ( Best Score = 1.0 )

<br>

- 테스트 데이터 분할
<p align='center'><img src="assets/src02.png" width="420"></p>

<br>

## 탐색적 데이터분석 EDA

## 피쳐엔지니어링

## 모델선정 및 훈련

## 한계 점

## 결과
