# 2022-Public-Data-Analysis

### 주제 : 서울시 모아어린이집 확대를 위한 최적 입지 선정 분석
- 목적 : 서울시 빅데이터 기반 서울형 모아어린이집의 최적 입지선정을 통한 효율적 행정 실현
- 팀원 : 이수현 이승현 이하늘 임소연 전지우 최지원
- 기간 : 2022.07.27~2022.08.19
- 분석도구 : Python, R, Q-gis
- 분석기법 : K-means, Score-Model, Scaling


### 분석 개요 
- 서울형 모아어린이집의 정책 상황을 반영하여 우선적으로 필요한 자치구 선정
- 환경지수, 위험지수,접근지수를 고려해 자치구 내 최적 입지 선정


### 분석 데이터
- 2022년 모아어린이집 참여 어린이집 정보
- 서울시 어린이집 정보
- 서울시 강서구 어린이집 정보
- 서울시 보육시설 이용 아동 비율 통계 
- etc.

### 분석 프로세스

#### Step 1 데이터 추출 과정
![image](https://user-images.githubusercontent.com/64217874/197401898-be71480f-0c8b-44cb-90da-6e1274803393.png)
![image](https://user-images.githubusercontent.com/64217874/197401901-0b1fcf15-90ae-4525-bbd5-9683567dd1ce.png)
![image](https://user-images.githubusercontent.com/64217874/197401912-c6cf85b2-eeb6-494b-9aa4-9152338791f9.png)
![image](https://user-images.githubusercontent.com/64217874/197401915-940ae040-b1d2-4826-944e-9c27f7a209da.png)

1) 자치구 선정 데이터셋과 최적 입지선정 데이터셋을 수집한다.
2) 관련 논문을 참고하여 자치구 선정 예측 변수와 최적 입지선정 예측변수를 산정한다.

#### Step 2 보육환경점수 산출
![image](https://user-images.githubusercontent.com/64217874/197401597-0c0ae78d-8665-4710-8bd4-7e7774954b03.png)
1) 선정된 예측 변수를 Min-Max Scailing 하여 보육환경점수를 산출한다.

#### Step 3 자치구 선정
![image](https://user-images.githubusercontent.com/64217874/197401613-c336d5a2-485f-4c4d-b242-ab1a010f5b6e.png)
1) AHP를 통한 변수의 가중치를 추정하고 점수가 가장 높은 강서구를 우선 입지선정 자치구로 선정한다.

#### Step 4 입지우선필요도 산출 
![image](https://user-images.githubusercontent.com/64217874/197401952-6156db14-a2de-49be-ac31-90cbcfec1eb0.png)
![image](https://user-images.githubusercontent.com/64217874/197402494-4545946a-6d83-4db3-988f-cde8ed859cbc.png)
![image](https://user-images.githubusercontent.com/64217874/197401961-e9219fe0-3928-4bc6-b834-54db08b16e9d.png)
1) 기존 연구 자료들을 참고하여 어린이집별 환경지수, 위험지수, 접근지수를 산출한다.

#### Step 5 최적 입지선정 
![image](https://user-images.githubusercontent.com/64217874/197401674-86ee8863-3ac7-4617-b034-1debd1f9f1e5.png)
1) 강서구 내 조건에 맞는 어린이집에 대해 K-means 클러스터링을 진행하여 공동체를 할당한다.
* 기존 모아어린이집, 어린이집 평가등급 C등급 이하 제외
2) 각 공동체별 점수를 산출하여 입지우선필요도를 도출한다.
3) 기존 모아 어린이집과 신규 선정된 모아어린이집의 입지우선필요도를 진행한다.
