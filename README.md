Lending Club 대출 상태 불량 예측모형 개발

 
활용 데이터셋: accepted_2007_to_2018Q4.csv (reject 파일은 활용 X)

분석 주제는 2015 ~ 2016 대출이 실행된 대상자에 대해서, 정상(0) / 불량(1)을 예측하는 이진분류모형(Binary classifiaction model) 개발입니다.

데이터 출처: https://www.kaggle.com/datasets/wordsforthewise/lending-club?select=accepted_2007_to_2018Q4.csv.gz

대상자 선정

         - issue_d(대출실행년월)가 2015~2016년인 대상자
         
         - loan_status 항목값이 Current / Fully Paid / Charged Off / Default / Late (16~30 days) / Late (31-120 days)에 해당하는 대상자 (그 외 값을 갖는 대상 제외)
         
         - application_type 항목값이 individual인 대상자
        
         
         
타겟 정의: loan_status 항목 중

         - 정상(0): Current / Fully Paid
         
         - 불량(1): Charged Off / Default / Late (16~30 days) / Late (31-120 days)에 해당





최종 예측모델로 MLP모델을 선정했고 정확도 약 0.83이 나왔습니다.
