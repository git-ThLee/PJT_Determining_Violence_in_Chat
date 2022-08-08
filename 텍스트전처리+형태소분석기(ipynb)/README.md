# 텍스트전처리 ipynb 파일 설명

---


- 00.데이터생성_konlpy.ipynb
    1. 데이터 로드
    2. 결측치 제거
    3. 문제있는 레이블링(중복, 미레이블링) 제거
    4. 텍스트 전처리
        1. 한글, 띄어쓰기 외 제거
        2. #@#(개인정보) 포함한 행 제거
        3. 중복된 문자열 줄이기
            - soyNLP 사용해서 줄이기 : 잘 안됨 
            - 직접 코드 구현 
    5. 형태소분석기
        1. input을 형태소분석기로 분해
        2. 주요 품사만 추출
        3. join
    6. 파일 저장

- 01.데이터생성_mecab_khaiii_kiwi.ipynb
    1. 데이터 로드
    2. 결측치 제거
    3. 문제있는 레이블링(중복, 미레이블링) 제거
    4. 텍스트 전처리
        1. 한글, 띄어쓰기 외 제거
        2. #@#(개인정보) 포함한 행 제거
        3. 중복된 문자열 줄이기
            - soyNLP 사용해서 줄이기 : 잘 안됨 
            - 직접 코드 구현 
    5. 형태소분석기
        1. input을 형태소분석기로 분해
        2. 주요 품사만 추출
        3. join
    6. 파일 저장

- 02.성능비교(자동).ipynb
    1. 데이터 로드
        - train
            - train_test_split 해서 train, valid 분할
        - test 
    2. 모델 선택
        - bert
            - "bert-base-uncased"
        - kr-bert
            - "snunlp/KR-BERT-char16424"
    3. 옵티마이저 선택
        - AdamW
    4. dataset으로 변환
        - input : csv
        - output : dataset
    5. dataloader 생성
        - train
        - valid
        - test
    6. 모델 training
        - train, valid 데이터 사용
    7. 학습된 모델 저장
    8. test 데이터로 성능 예측 
    9. 예측된 성능 출력