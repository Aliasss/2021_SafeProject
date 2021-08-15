# 2021년 토이 프로젝트
## 전시 상황에 어디로 대피해야 할까?
#### 결과: https://datastudio.google.com/reporting/47cb74aa-9d06-4f20-88d0-e8a94cb514ac

### 데이터 소스 : 공공데이터 포털
### 활용 언어 및 패키지 : Selenium, Python, Pandas, Matplotlib, Google Bigquery
### 인터랙티브 시각화 도구 : Google Data Studio


### 진행 과정

(1) 공공데이터 포털의 191개 데이터 파일 크롤링하여 데이터 다운로드 (셀레니움 활용)

(2) 191개 전국 민방위대피시설 데이터 -> 하나의 파일로 Load

(3) 데이터 전처리

- 데이터 전반적인 상황 파악

- 대피가능인원수: object 타입을 float 타입으로 변환

- 개방여부 데이터 대소문자 통일 (Y or N)

- 시 단위로 보기 위해 region 컬럼 생성

  * 소재지도로명주소를 기준으로 하되 해당 컬럼값이 '-'이거나 null이면 소재지지번주소에서 문자 split해서 넣음. 이후 지역명 통일(ex.전라남도 -> 전남)

- 서울의 구별 현황을 파악하기 위해 region이 서울특별시인 데이터의 region2 컬럼 생성

  * 소재지도로명주소를 기준으로 하되 해당 컬럼값이 '-'이거나 null이면 소재지지번주소에서 문자 split해서 넣음.

- Google Bigquery에 테이블 업로드하기 위해 컬럼명 영어로 통일

(4) 데이터 인터랙티브 시각화 
- Google Data Studio를 활용해 데이터 시각화
