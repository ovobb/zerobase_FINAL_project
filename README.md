# E-COMMERCE 경영전략제시
<p align="center"><img width="574" alt="스크린샷 2023-06-02 오후 7 19 29" src="https://github.com/ovobb/zerobase_FINAL_project/assets/123061697/8dbfc3af-cd1d-4cb3-bff3-9427319eb0de" width="200" height="300"></p>

----

## INDEX

1. [프로젝트 소개](#1-프로젝트-소개)
2. [EDA](#2-eda)
3. [매출예측 모델](#3-매출예측-모델)
4. [RFM 및 고객세분화](#4-rfm-및-고객세분화)
5. [가치제공](#5-가치제공)


----

## 1. 프로젝트 소개
### 1-1. 프로젝트 기간
2023.05.03 ~ 2023.05.26

### 1-2. 주제선정 이유 및 목표
![스크린샷 2023-06-02 오후 7 29 11](https://github.com/ovobb/zerobase_FINAL_project/assets/123061697/1fbfbda1-6ae4-43ec-b391-c4a3e52fb2ae)

한국의 전자상거래 시장 규모는 전 세계 5위이며, 전 세계에서 모바일 쇼핑이 가장 빠르게 성장하는 국가입니다.(2020년 기준) 
전자상거래(E-Commerce) 시장은 단순한 거래처에서 여러 기기(컴퓨터, 스마트폰, 태블릿 등)와 상점 개념을 포함하는 쇼핑 생태계로 발전해 왔습니다.
국내 전자상거래 시장은 꾸준한 성장세를 보여왔지만 코로나19 확산을 계기로 더욱 급격히 성장했고 향후 온라인을 통한 거래가 국내 소매유통에서 차지하는 비중은 더욱 커질 것으로 전망됩니다.
기업간 경쟁은 더욱 심화되고 있고 따라서 E-COMMERCE 데이터를 통해 매출을 예상하고 고객 세분화를 통해 고객 타겟팅이 가능하도록 하는것이 프로젝트의 목표입니다. 

----

## 2. EDA
- 7개의 주제(고객, 상품, 주문, 금액, 판매, 리뷰, 배송)로 나누어 EDA를 진행
### 2-1. 데이터 소개
- 출처 : Brazilian E-Commerce Public Dataset by Olist (kaggle)
- 총 8개의 데이터셋(고객, 지역, 주문, 배송, 결제, 리뷰, 상품, 판매)
- 2016년 ~ 2018년 사이의 약 10만건의 주문 데이터

<img width="949" alt="스크린샷 2023-06-03 오후 3 21 31" src="https://github.com/ovobb/zerobase_FINAL_project/assets/123061697/6dbe87b2-4b52-4f9f-92f5-8145c489a3d8">

### 2-2. EDA(고객)

- state별 고객 분포도 

![스크린샷 2023-06-03 오후 3 33 26](https://github.com/ovobb/zerobase_FINAL_project/assets/123061697/d0f3906b-e960-4831-9eb8-e6661d70566b)

- city별 고객 분포도

![스크린샷 2023-06-03 오후 3 34 20](https://github.com/ovobb/zerobase_FINAL_project/assets/123061697/aada8c96-d195-460b-883b-abf5eacfccdf)

```
40%가 넘는 고객들이 SP주에 분포되어 있고 그 다음으로 RJ, MG 순인것을 알 수 있다. 그중 특히 Sao paulo에 많은 고객층이 형성되어 있다
```

### 2-3. EDA(상품)

- feature 상관관계

![스크린샷 2023-06-03 오후 9 52 42](https://github.com/ovobb/zerobase_FINAL_project/assets/123061697/0b6f4733-3faa-43e4-8bcd-f5071b37c191)


- 카테고리별 주문 Top10

![스크린샷 2023-06-03 오후 9 49 39](https://github.com/ovobb/zerobase_FINAL_project/assets/123061697/e8818fb6-cdac-478a-8572-a4b884ee2c42)

```
무게, 길이, 높이처럼 부피와 관련된 feature들이 price와 높은 상관관계를 보였다. 
또한 카테고리별 주문 Top10에는 침대테이블목욕, 헬스뷰티, 스포츠레저 등의 순으로 많이 팔린것을 알 수 있다
```
### 2-4. EDA(주문)

- 주문상태

![스크린샷 2023-06-03 오후 9 58 30](https://github.com/ovobb/zerobase_FINAL_project/assets/123061697/9c8d18a7-53f1-4ba5-92bf-644f27c18533)

- 주문상태 '취소'인 지역별 주문건수

![스크린샷 2023-06-03 오후 10 00 34](https://github.com/ovobb/zerobase_FINAL_project/assets/123061697/804d8ee5-d249-4056-b495-c5a282a14a6b)

```
주문상태는 역시나 배달이 가장 많았고 취소 주문건수는 0.63%이다
전체 주문건수가 많은 지역이 취소 주문건수도 많은지, 아니면 전체 주문건수와 상관없이 취소 주문건수가 많은 지역이 있을지 추가적으로 살펴보았고
위의 고객 EDA에서 상위에 있었던 SP, RJ, MG 등의 state가 취소 주문건수도 많은것을 알 수 있었다
```

- 지역별 전체 주문량

![스크린샷 2023-06-03 오후 10 17 40](https://github.com/ovobb/zerobase_FINAL_project/assets/123061697/098457b0-ff8d-4e8b-9523-27183cfa02be)

- 년도 + 월별 주문건수

![스크린샷 2023-06-03 오후 10 18 40](https://github.com/ovobb/zerobase_FINAL_project/assets/123061697/ce195e4c-e7b3-4163-aabc-9cc8fa3cce19)

- 요일별 주문건수

![스크린샷 2023-06-03 오후 10 18 31](https://github.com/ovobb/zerobase_FINAL_project/assets/123061697/c7dee462-bf20-4fb3-995f-0d776d1ccfc2)

```
전체적인 주문량은 남동지역에 고르게 분포되어있고 특히 상파울루가 높은 주문량을 보였다
2017년 11월 ~ 2018년 8월까지 주문량이 증가하는 추세이고 이후 급락하는 형태이다
주말의 주문량이 많을거라는 예상과는 달리 평일의 주문량이 더 많았다
```

### 2-5. EDA(금액)

- 결제수단

![스크린샷 2023-06-03 오후 10 43 11](https://github.com/ovobb/zerobase_FINAL_project/assets/123061697/1c258461-0b42-42ab-92ab-162352e12f3b)

- 주별 매출 

![스크린샷 2023-06-03 오후 10 43 47](https://github.com/ovobb/zerobase_FINAL_project/assets/123061697/493fea12-53a6-4e36-a6d9-d60e22ddab23)

```
모든 판매건의 결제수단 중 credit card가 73% 이상으로 가장 많았으며 다음으로 boleto, voucher등이 사용됐다
```

### 2-6. EDA(판매)

- state별 판매자 분포도

![스크린샷 2023-06-03 오후 10 48 55](https://github.com/ovobb/zerobase_FINAL_project/assets/123061697/dde009d1-0d33-4632-8157-3a434d201e30)

- 판매자 top4까지 판매 카테고리

![스크린샷 2023-06-03 오후 10 50 32](https://github.com/ovobb/zerobase_FINAL_project/assets/123061697/e536cddf-af30-4d61-b523-739d96aa875c)

```
판매자 역시 SP에 가장 많이 몰려있는 것을 확인할 수 있다
top4까지를 살펴보면 1~2가지 카테고리가 높은 비중을 차지하는 경향이 있다
```

### 2-7. EDA(리뷰)

- 평점 분포 및 리뷰를 쓴 비율

![스크린샷 2023-06-03 오후 10 56 49](https://github.com/ovobb/zerobase_FINAL_project/assets/123061697/c5ea9426-ecff-4245-b56a-35ab6c30deed)

```
평점 분포는 5점이 가장 많았고 2점이 가장 적었다
4점을 준 고객이 리뷰를 많이 썼다는 것을 알 수 있었다
```

- 리뷰 n-gram 분석

![스크린샷 2023-06-03 오후 10 58 54](https://github.com/ovobb/zerobase_FINAL_project/assets/123061697/03d52640-b972-4156-8e75-5fcb412535a2)

```
3점 미만은 부정, 3점 이상을 긍정으로 분류하였다
1-gram부터 4-gram까지 늘려가며 확인해본 결과 4-gram부터 의미있는 문장이 생성되었다
- o produto foi entrgue : 제품이 배송되었습니다 / o produto chegou antes : 전에 도착한 제품 / produto chegou antes prazo : 마감일 전에 도착한 제품
- nao recebi o produto : 상품을 받지 못했다. / ainda ano recebi o : 나는 여전히 / o produto nao foi : 제품은 아니었다.
```

### 2-8. EDA(배송)

- 배송 많은 top10 city

![스크린샷 2023-06-03 오후 11 17 16](https://github.com/ovobb/zerobase_FINAL_project/assets/123061697/a79c1d5e-4a0c-4210-8128-5708978f67a7)

- 배송완료 일자

![스크린샷 2023-06-03 오후 11 14 57](https://github.com/ovobb/zerobase_FINAL_project/assets/123061697/b3766f50-8928-46c0-a428-6fff1b78950a)

```
배송이 많은 city는 역시나 상파울루였다
주문수가 가장 많았던 2017년 11월에 오히려 배송완료 상태가 많지 않았고 그 다음달인 12월부터 배송완료 상태가 증가하였다
```
#### EDA를 통해 확인해본 결과 판매자, 구매자 모두 SP주에 밀집되어 있었고 매출이 잘 나오는 지역에 대한 타겟팅이 필요하다고 생각하여 이후 진행되는 모델링은 SP주만 추출하여 진행하였다

----

## 3. 매출예측 모델

- 주별로 집계한 후 8주간의 데이터를 통해 그 다음주의 매출을 예측하는 형태이다
- Train : 2016년 10월 ~ 2018년 3월
- Test : 2018년 3월 ~ 2018년 9월
- 단일 모델
  - 종류 : XGBRegressor(n_estimators=110), LSTM
  - feature : price
- 다중 모델 
  - 종류 : XGBRegressor(n_estimators=100), LSTM
  - feature : price, delivery_score, review_score
    - delivery_score : 실제 배송일, 배송 예정일의 차이를 통해 0~5점까지 점수를 부여
    - review_score : review에 대한 점수를 부여

|   | rmse |
|---|----|
| 단일 XGBRegressor | 22335 |
| 다중 XGBRegrossor | 21446 |
| 단일 LSTM | 14825 |
| 다중 LSTM | 10086 |

```
XGBRegressor보다는 LSTM의 RMSE가 더 낮았고 단일보다 배송과 리뷰 관련 feature를 추가한 다중의 RMSE가 더 낮은 것을 알 수 있었다
성능이 가장 좋았던 다중 LSTM을 통해 마지막 데이터의 다음주를 예측해본 결과 261.54$ 산출
````

----

## 4. RFM 및 고객세분화

### 4-1. Segmentation 방법 1
- R(recency), F(frequency), M(monetary)에 가중치를 부여하지 않고 score 생성 후 Segmentation 진행
- 등급화 참조 : https://documentation.bloomreach.com/engagement/docs/rfm-segmentation 

![스크린샷 2023-06-05 오전 12 31 55](https://github.com/ovobb/zerobase_FINAL_project/assets/123061697/943aaa37-de18-4ee6-ac5a-d48d4f9b9e45)

### 4-2. Segmentation 방법 2
- RFM score = a * R(Recency) + b * F(Frequency) + c * M(Monetary)
  - a,b,c 최적의 가중치를 직접 구해서 RFM_SCORE 생성
1) Normalization 된 R,F,M 데이터들을 가지고 군집화 모델링
      - k-means 사용
      - clustering 나누는 기준 KELbowVIsualizer 통해 확인(6집단으로 확인)

![스크린샷 2023-06-05 오전 12 36 05](https://github.com/ovobb/zerobase_FINAL_project/assets/123061697/84c0939a-85c4-4f0f-aa87-e2ae18bde5f5)

2) 각 집단별로 CV를 최소로 하는 가중치를 구하여 RFM_SCORE 생성
3) RFM_SCORE로 등급화
  - 6등급 : Bronze, Silver, Gold, Royal, Vip, VVip

![스크린샷 2023-06-05 오후 5 25 18](https://github.com/ovobb/zerobase_FINAL_project/assets/123061697/966d8b41-ab40-4ed1-bf5a-e2dc3849a9a2)

----

## 5. 가치제공

- 매출 예상을 통해 매출전략 수립이 가능하게 한다
- RFM으로 고객을 Segmentation 함으로써 고객 타겟팅이 가능하게 한다

---
#### TEAM
- 고지현
- 김정빈
- 박건우
- 윤정옥
- 정기중
- 황지우


