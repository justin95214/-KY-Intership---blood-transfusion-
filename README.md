# [KY-Intership] --blood-transfusion

### 1차 MIMIC 데이터(환자) 데이터 전처리

#### 1. 수혈정보 바탕으로 필터링하기
  - procedure_icd에서 수혈받은 환자
  - inputevents_cv 에서도 마찬가지
  - inputevents_mv에서도
  - procedureevents_mv에서도 

#### 2. 수술했는지 여부 따라 필터링 하기
  - CPTEVENT로 수술여부 필터링
  - 그외 수술환자가 누락 된게 있는지 찾아보기
