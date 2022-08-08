# 텍스트전처리 ipynb 파일 설명

---

- 00.스마일게이트_csv파일변환_컬럼정리.ipynb
    - input : excel
    - output : csv 
    - 목적 :
        - excel to csv
        - 컬럼 통합 및 불필요(관련없는) 컬럼 제거
        - 컬럼 재조정(정해진 컬럼 양식으로 변환)

- 01.윤리데이터_csv파일변환.ipynb
    - input : json 
    - output : csv 
    - 목적 : 
        - json to csv 
        - 불필요(관련없는) 컬럼 제거 

- 02.윤리데이터_컬럼정리_샘플링.ipynb
    - 목적 :
        - 분할된 csv 파일 5개 통합
        - 불필요 컬럼 제거
        - 컬럼 재조정(정해진 컬럼 양식으로 변환)
        - 데이터 샘플링
            - input data : 약 36만개
            - output data : 약 1만 2천개

- 03.데이터통합_샘플링.ipynb
    - 목적 :
        - 윤리데이터 + 스마일게이트 데이터 통합(merge)하기
        - 데이터 섞기