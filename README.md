# 🎭 카카오톡 채팅을 활용한 폭력성 확인 프로젝트

# 👪 팀원

|이름|담당|
|:---:|:---|
[정준녕](https://github.com/ezez-refer)|Bert모델 구현<br/>base라인 구현 <br/> Flask 구현|
[정새롬](https://github.com/jkat-yd)|ko-bert모델 구현<br/> 데이터 전처리 |
[이정훈](https://github.com/coronarita)|PM <br/> PPT 작업 <br/> 발표 <br/> wandB 구현 |
[이태훈(나)](https://github.com/git-ThLee)| 형태소분석기 성능비교 <br/> 데이터 전처리 <br/> Flask html 구현|

---

# 👓 프로젝트 설명

### 기획 의도

> 사이버 폭력을 탐지하기 위한 채팅 기록(데이터)을 활용하여 채팅방의 폭력성을 확인하기!
>> 카카오톡 채팅 기록을 통해 채팅 내용 속의 폭력성을 판단하여, 보호자(학부모)에게 폭력성을 알려주기! 

### 기대 효과

    1. 채팅 내용간 폭력성이 높게 나오면, 사이버 폭력을 의심할 수 있음  
    2. 사이버 폭력이 아니더라도, 자녀와 친구들 사이의 내용이 폭력성이 높음을 인지할 수 있음  

![image](https://user-images.githubusercontent.com/55564114/183452175-0d1486da-e217-4c94-8149-643929e29579.png)  

---

# 파일설명

---

# 👜 사용 프로그램

|사용 툴 | 목적 |
|:---:|:---|
|깃허브| 개발 코드 공유용 |
|구글드라이브(공유) | 기획서 및 PPT 등 파일 공유용 |
|슬랙| 소통 및 회의용 |
|코랩(무료,유료)| 딥러닝 모델 학습을 위한 개발 환경|

---

# 📼 데이터

1. 텍스트 윤리검증 
    - 출처 : [Ai-Hub 텍스트윤리검증](https://aihub.or.kr/aihubdata/data/view.do?currMenu=115&topMenu=100&aihubDataSe=realm&dataSetSn=558)  
    - 데이터 수 : 약 360,000 개
    - 용도 : 모델 학습용

2. 한국어 혐오표현 데이터셋
    - 출처 : [Smilegate(github)](https://github.com/smilegate-ai/korean_unsmile_dataset?fbclid=IwAR0xTlHYCWK0LtrghSL1bPm2su69-LbjisutmcvLlERlHzroMlVpHq3h71g)
    - 데이터 수 : 약 15,000 개
    - 용도 : 모델 학습용

3. DC 인사이드 댓글 크롤링
    - 용도 : 폭력성 높은 채팅 데이터 생성용(test용)

---

# 📆 스케줄

|일정| 날짜| 기간 |
|:---|:---:|:---:|
|프로젝트 기획 기간| 7/25(월) ~ 7/27(수) | 3일 |
|데이터 수집|7/27(수) ~ 7/28(목)|2일|
|Base Code 구현|7/27(수) ~ 7/31(일)|5일|
|Model 학습|8/1(월) ~ 8/3(수)|3일|
|Flask 구현|8/1(월) ~ 8/3(수)|3일|
|발표 준비|8/4(목) ~ 8/5(금) |2일|
|프로젝트 발표|8/5(금)|1일|


> 총 프로젝트 기간 : 2주

---

# 🎈 프로세스

![image](https://user-images.githubusercontent.com/55564114/183454042-cc1d2617-db0b-47f1-bd3a-4bb718774fee.png)
  
---

# 📺 구현 결과 화면(Flask)

![image](https://user-images.githubusercontent.com/55564114/183454288-37badb27-acb5-4976-9f94-e499fd9994a9.png)
  
---

# 아쉬운점

> 채팅 데이터의 양이 많을수록 시간이 오래 걸린다는 단점이 있다. 아무래도 단순하게 for문을 활용하여 채팅 데이터를 분석하는 과정에서 오래 걸린다

> 또한, 프로젝트 기간 자체가 짧은 것에 대한 아쉬움과 다양한 모델을 활용해보지 못한 것이 아쉽다.

---