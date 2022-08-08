# PJT_Determining_Violence_in_Chat

# 참여자

|이름|깃허브|성과|
|:---:|:---:|:---:|
|정준녕|[깃허브](https://github.com/ezez-refer)|bert모델 base라인 구현 \n flask 구현|
|정새롬|[깃허브](https://github.com/jkat-yd)|ko-bert모델 추가 \n 텍스트전처리 |
|이정훈|[깃허브](https://github.com/coronarita)|PM \n PPT, 발표 \n wandB 연동 |
|이태훈(나)|[깃허브](https://github.com/git-ThLee)| 형태소분석기 성능비교 \n 텍스트전처리 |

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

# 형태소 분석기 성능 비교 

## Konlpy간 성능 비교(okt, kkma, komoran, hannanum, mecab)

![image](https://user-images.githubusercontent.com/55564114/183454839-df714642-e2a9-4703-bdbd-a60d6fcde344.png)    

- 성능 순위 : mecab > komoran > kkma > hannanum > okt  
- 속도 순위 : mecab >>> kkma > okt > hannanum > komoran  
(komoran이 속도가 유독 느린 이유 : "요시요시요시" 같은 반복되는 문장을 분석하는데 긴 시간이 소요된다. 가끔 메모리가 터지기도 한다)  
- 최종 결과 : mecab 
    - 이유 : 성능도 준수하며, 속도 측면에서 큰 장점을 갖는다.(web에서 형태소분석하는데 오래걸리면 안되서 속도가 큰 장점으로 생각한다)  

## mecab 사용 품사간 성능 비교 

![image](https://user-images.githubusercontent.com/55564114/183455656-bbc3df6a-1ce3-45d8-9b52-2549694f6332.png)  
  
- 사용 품사 3분류
    - 체언, 용언
    - 체언, 용언, 관형사, 부사
    - 체언, 용언, 관형사, 부사, 조사
- 결과
    - 품사가 많을수록 학습성능이 향상됨을 알 수 있다
    - 감탄사, 영어, 숫자 등은 텍스트전치리 과정에서 제거됨에 따라 품사를 제외함

## mecab vs khaiii(카이) vs kiwi간 성능 비교 

![image](https://user-images.githubusercontent.com/55564114/183456269-4a298c71-000c-456f-afc9-803681957c02.png)  
  
- 간단 설명
    - khaiii(카이) : 카카오에서 만든 형태소분석기 
    - kiwi : 지능형 한국어 형태소 분석기 , 빠른 속도와 범용적인 성능을 갖는다
- 결과
    - 속도 : mecab > khaiii > kiwi
    - 성능 : 큰 차이가 없음. 속도가 중요한 판단요소가 된다

## BERT vs KR-BERT 모델 성능 비교

![image](https://user-images.githubusercontent.com/55564114/183457276-2dab5557-72a6-407a-a3dc-78e176926cfa.png)  

- 형태소분석기
    - mecab
    - khaiii
    - kiwi
- bert vs kr-bert 성능 비교
    - 성능 : kr-bert > bert
    - 속도 : 테스트 실패함
        - 실패 이유 : web(flask)에서 두 모델의 속도를 비교할 계획이였지만, bert모델은 문제 없지만, kr-bert모델이 문제가 발생함
    
---

# 텍스트전처리 