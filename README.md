# user-segmentation-analysis



## 배경
![Google Merch Shop](https://www.googlemerchandiseshop.com/images/logo.png)

Google Merch Shop은 구글에서 운영하는 공식 온라인 기념품(굿즈) 판매 채널로, 옷, 가방, 액세서리, 학용품을 비롯하여 다양한 상품을 취급하는 곳이다. 하지만, 최근 들어 구글 굿즈 샵의 연간 매출 성장세가 둔화되며 마케팅 부서에서는 매출 확대와 안정을 위한 데이터 기반 전략이 필요하다는 판단을 내렸다. 이에 따라 2019년 1월 1일부터 2019년 12월 31일까지 쌓인 온라인 구글 굿즈 샵의 거래, 고객, 할인 데이터를 수집하여, 올해 서비스의 성장을 위한 신규 마케팅 전략 수립과 마케팅 성과 향상을 위한 고객군 세분화 작업을 진행하고자 했다.


## 목표

1. 2019년 굿즈샵 거래 데이터 종합 분석
- 매출 트렌드
- 상품 및 상품카테고리 성과
- 고객 유입 및 행동
- 할인 및 프로모션 효과

2. RFM 분석을 통한 고객 세분화 
- 이탈 위험 고객 대상 푸시 메시지 타깃군을 선별하기 위한 고객 세분화

## 활용 데이터

- 온라인 거래와 관련된 정보: Onlinesales_info.csv 
- 고객과 관련된 정보: Customer_info.csv
- 할인과 관련된 정보: Discount_info.csv

## 분석 결과

### 굿즈샵 거래 데이터 종합 분석

**1. 매출 트렌드**

![매출 트렌드](https://github.com/Venusgalaxy1022/user-segmentation-analysis/blob/main/sales_data_1.png?raw=true)

월별 매출액과 주문건수는 연중 변동성을 보이나, 연말로 갈수록 상승세를 나타낸다. 이는 고객의 구매 빈도가 연말에 집중된 결과로 해석할 수 있다. 


**2. 상품 및 카테고리 성과**

![상품 및 카테고리 성과](https://github.com/Venusgalaxy1022/user-segmentation-analysis/blob/main/monthly_orders_by_category.png?raw=true)

Nest 제품군(Nest-USA, Nest, Nest-Canada)의 주문건수와 매출액이 압도적으로 많은 비중을 차지한다. 해당 제품군의 총 주문수가 14K에 달하고, 전체 주문의 56%를 차지한다. 해당 카테고리는 단가 또한 평균 124~194달러로 높은 수준이기 때문에, 합산 매출 역시 전체 매출의 67% 이상을 기여한다. 온라인 샵의 매출 구조가 특정 고가 상품군에 극도로 편중된 형태다.  

**3. 구매 고객 특성**

![구매 고객 특성](https://github.com/Venusgalaxy1022/user-segmentation-analysis/blob/main/인구학적고객분류에따른판매동향.png?raw=true)

지역별 고객수, 매출액, 주문건수를 살펴보면 모두 Chicago, California, New York, New Jersey, Washington DC 순이다. 이는 Google Merch Shop이 대도시 중심의 고객 기반을 확보하고 있음을 시사한다. 모든 지역에서 남성에 비해 여성 고객이 많고, 구매력 또한 큰 것을 알 수 있다. 

**4. 할인 및 프로모션 효과**

![할인 및 프로모션 효과](https://github.com/Venusgalaxy1022/user-segmentation-analysis/blob/main/discount_relations.png?raw=true)

할인율이 커질수록 매출과 거래수가 선형적으로 증가하는 것이 아니다. 단순히 할인 폭을 확대한 프로모션은 객단가 하락 및 수익성 저하로 이어질 수 있으며, 고객의 구매 의사 결정에서 할인율이 주요한 요인이 아님을 시사한다.


### 고객 세분화

**1. 방법**

![RFM 분석 절차](https://github.com/Venusgalaxy1022/user-segmentation-analysis/blob/main/rfm_scoring_pipeline.jpg?raw=true)

- RFM 지표: Recency(최근 구매일로부터의 일수), Frequency(구매 빈도),Monetary(구매 금액)
- 정규화된 RFM 합산 점수의 5분위수 산출을 통해 고객을 5개 그룹으로 세분화함


**2. 세분화 결과**

![rfm_distribution](https://github.com/Venusgalaxy1022/user-segmentation-analysis/blob/main/rfm_distribution.png?raw=true)

정도의 차이는 있지만, 세 지표 모두 관측값이 왼쪽으로 집중된 것을 확인할 수 있다. 즉, 쇼핑몰 대다수의 고객과 달리, 매우 빈번하고 구매력이 큰 소수의 power 고객이 존재한다는 것을 알 수 있다.

![rfm_distribution](https://github.com/Venusgalaxy1022/user-segmentation-analysis/blob/main/rfm_summary.png?raw=true)

최우수 등급에 해당하는 고객이 1년 매출의 53% 이상을 차지하는 것을 확인할 수 있고, 다음 등급의 회원과 매출 비중에 있어 약 40%p 가량 차이가 나는 현상을 확인할 수 있다. 따라서, 이 핵심 고객층을 놓치지 않기 위한 지속적인 특별 혜택 제공 및 니즈를 충족시킬만한 상품 개발이 필요하다. 


## 마케팅 인사이트

1. 이탈 또는 이탈 위험 고객군 리마케팅

고객 등급 분류의 최하위에 속한 그룹의 경우, 이미 서비스를 이탈했거나 향후 이탈 가능성이 가장 큰 집단이다. 이들을 대상으로 “마지막 구매일이 6개월이 넘었네요! 새로운 굿즈를 한번 만나보세요!” 라는 푸시 메시지를 보내는 리마케팅을 제안한다. 마케팅 예산에 제약이 따른다면 쿠폰 사용률이 높은 고객들에 한해서 발송하는 방법을 추천한다. 

2. 배송료 할인 행사

Notebooks & Journals, Headwares, Google 브랜드 제품은 제품 단가보다 배송료가 높아 소량 주문 고객들에게는 배송료가 구매 저항 요인으로 작용할 수 있을 것으로 판단된다. 따라서, 신년이 다가온 만큼 판매를 촉진하기 위해 인기가 많은 상위 상품 Office, Drinkware, Lifestyle, Notebooks & Journals 등의 상품에 한해 0원 배송료 이벤트를 진행한다.

3. 무분별한 할인 행사 중단

1,4,7,10 / 2,5,8,11 / 3, 6, 9, 12 월에 모든 카테고리가 10, 20, 30% 할인행사를 진행한다. 그러나 할인율과 매출 및 거래수는 양의 상관을 보이지 않는다. 오히려, 고가제품을 구매하는 고객들의 경우 가격 할인에 크게 반응하지 않고, 고가의 제품을 구매하기 때문에 할인 행사가 회사의 순이익을 감소시킬 수 있다. 또한, 할인 행사가 자주 진행될 경우, 다음에 더 큰 할인 행사를 진행하겠지라는 기대심에 구매를 지연시킬 수 있다. 따라서, 할인행사의 빈도와 대상을 재조정할 필요가 있다. 다소 무분별한 할인 행사보다는 다음과 같은 대체전략을 생각해볼 수 있다.

- 전략1: 고가 제품군의 신제품, 기념판 중심 프로모션
 Nest 상품의 경우, 충성 고객군이 탄탄하게 구성되어 있고, 신규 구매 고객들이 진입할 때 주로 관심을 갖는 카테고리이기 때문에, 신제품 또는 새로운 버전의 Nest가 출시될 경우에 선별적으로 할인 행사를 진행한다. 

- 전략2: 신학기, 여름, 연말 프로모션
매달 할인 행사가 진행되는 것이 아니라, 연간 주문 횟수가 가장 많은 1월, 8월, 12월에 파격적인 프로모션을 진행할 경우에 거래 확대와 신규 고객들의 구매 전환율이 더 높을 것으로 예상된다.



