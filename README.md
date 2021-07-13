# [KY-Intership] --blood-transfusion

### 1차 MIMIC 데이터(환자) 데이터 전처리
  - CITI program 교육 이수를 해야함
  https://github.com/justin95214/-KY-Intership---blood-transfusion-/blob/main/citiCompletionReport10271106.pdf

#### 1. 수혈정보 바탕으로 필터링하기
  - procedure_icd에서 수혈받은 환자
  - inputevents_cv 에서도 마찬가지
  - inputevents_mv에서도
  - procedureevents_mv에서도 

#### 2. 수술했는지 여부 따라 필터링 하기
  - 수혈을 받은 집합과 수술을 받은 집합으로 총 4개로 라벨링하기로 진행
  - CPTEVENT로 수술여부 필터링
  - 그외 수술환자가 누락 된게 있는지 찾아보기

#### 3. MIMIC 데이터 CITI program 이수하기

#### 4. 새로운 Time Series를 부여하기로 결정 & 정형 데이터 Feature Selection 방향성 조정
  - 수술에 대한 집합을 제외 시키기로 했음
  >> 환자 ICU입원 ID를 key로 수술을 받은 chart time이 없음

  - 새로운 Time Series로 수혈을 받은 Start time과 End Time이 중요하며, 환자에 따른 수혈뿐만 아니라 진료시간, 약물 투여시간 등 데이터 csv별로 Sequential 기준이 다 다르기 때문에, 입원인 Admission time을 기준으로 차이만큼 나타냄으로써, 각 환자들의 Time Series를 하나로 통합할 수 있음
  
  - 환자에 관련된 MIMIC 데이터를 가지고, 환자의 HADM ID기준으로 CPT, InputEvent_CV, LabEvents, Prescription데이터를 통해 진단, 검사, 약물 투여 관련된 데이터를 input 데이터로 설정하여, 첫번째로 수혈의 필요 판단 유무에 대한 이진분류를 하자고 결정함 차후에 수혈의 양까지 넣을 예정

