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




그냥 get_dummies는 아예 못쓴다고 생각하시면 편할 것 같아요. get_dummies를 사용하면 어쩔 수 없이 test 데이터의 범주형 변수도 파악을 해야 한다는 전제가 깔려서 train과정에서 test데이터의 정보를 쓰기 때문에 그렇습니다. train data에 OneHotEncoder를 적용해서 사용하는건 괜찮습니다.  


예를 들어드리면 0,1,2,3,4,5를 갖는 범주형 데이터가 있는데 train data에 0,1,2,3,5의 경우만 존재해서 get_dummies()를 쓰면 4가 반영되지 않습니다. 그런데 만약 test data에는 0,1,2,3,4,5가 전부 존재한다면 input data shape이(데이터의 열 개수) train data의 경우와 test data의 경우가 다르게 됩니다
