# PJT_Determining_Violence_in_Chat

# 참여자

|이름|깃허브|성과|
|:---:|:---:|:---:|
|정준녕|[깃허브](https://github.com/ezez-refer)|bert모델 base라인 구현 <br/> flask 구현|
|정새롬|[깃허브](https://github.com/jkat-yd)|ko-bert모델 추가 <br/> 텍스트전처리 |
|이정훈|[깃허브](https://github.com/coronarita)|PM <br/> PPT, 발표 <br/> wandB 연동 |
|이태훈(나)|[깃허브](https://github.com/git-ThLee)| 형태소분석기 성능비교 <br/> 텍스트전처리 |

---

# 기획

1. 학교에서 사이버 폭력이 증가하는 속도에 비해 처벌 및 사이버 폭력 파악이 어려움  
2. 카카오톡 채팅 기록을 통해 채팅 내용 속의 폭력성을 판단하여, 보호자(학부모)에게 폭력성을 알려줌  
    1. 채팅 내용간 폭력성이 높게 나오면, 사이버 폭력을 의심할 수 있음  
    2. 사이버 폭력이 아니더라도, 자녀와 친구들 사이의 내용이 폭력성이 높음을 인지할 수 있음  

![image](https://user-images.githubusercontent.com/55564114/183452175-0d1486da-e217-4c94-8149-643929e29579.png)  

---

# 사용 툴

|사용 툴 | 목적 |
|:---:|:---|
|깃허브| 개발 코드 공유용 |
|구글드라이브(공유) | 기획서 및 PPT 등 파일 공유용 |
|슬랙| 소통 및 회의용 |
|코랩(무료,유료)| 딥러닝 모델 학습을 위한 개발 환경|

---

# 사용 데이터

1. 텍스트 윤리검증 
    - 출처 : AI-Hub  
    - 사이트 : [텍스트윤리검증](https://aihub.or.kr/aihubdata/data/view.do?currMenu=115&topMenu=100&aihubDataSe=realm&dataSetSn=558)  
    - 파일 형식 : json
    - 데이터 수 : 약 36만개
    - 용도 : 모델 학습용

2. 한국어 혐오표현 데이터셋
    - 출처 : Smilegate(github)
    - 사이트 : [Smilegate](https://github.com/smilegate-ai/korean_unsmile_dataset?fbclid=IwAR0xTlHYCWK0LtrghSL1bPm2su69-LbjisutmcvLlERlHzroMlVpHq3h71g)
    - 파일 형식 : tsv
    - 데이터 수 : 약 1만 5천개
    - 용도 : 모델 학습용

3. DC 인사이드 댓글 크롤링
    - 파일 형식 : txt
    - 용도 : 폭력성 높은 채팅 데이터 생성용(test용)

---

# 기간

- 7월 25일(월) ~ 8월 5일(금) 
- 2주

---

# 프로세스

![image](https://user-images.githubusercontent.com/55564114/183454042-cc1d2617-db0b-47f1-bd3a-4bb718774fee.png)
  
---

# 구현 결과 예시 화면(Flask)

![image](https://user-images.githubusercontent.com/55564114/183454288-37badb27-acb5-4976-9f94-e499fd9994a9.png)
  
---
