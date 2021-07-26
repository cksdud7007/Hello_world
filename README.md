# NHQV_text_classification  
- NH투자증권_텍스트 분류 (예선진출)

### 프로젝트명
NH투자증권 주관, 진짜뉴스 & 가짜뉴스 판별하는 알고리즘 개발  

### 배경
진짜, 가짜뉴스 판별 알고리즘 개발  

### 목적
자연어처리를 통한 거짓 인터넷 뉴스 판별 알고리즘 개발  
 
### 수행기간
2020.11.23 ~ 2021.01.08 (약 6주)  

### 팀 구성
3인 1개팀 (윤승후, 이서희, 이찬영)  

### 사용 언어 및 도구
* Python
* Jupyter Notebook

### 주요 활용 데이터
NH투자증권에서 제공한 인터넷 기사 웹크롤링 데이터
  
### 주요 분석 기법
#### -  자연어 처리
* 토큰화
* Soynlp
* LRNounExtractor_v2
* 사용자 정의사전
* Mecab
* fastText

### 분석 방법
1. news_train set을 train set과 validation set으로 split  
(이하 news train set의 train set을 tts, news train set의 validation set을 tvs로 생략)
2. tts의 content를 대상으로 Soynlp로 사전학습
3. 사전학습과 전처리작업으로 도출한 핵심 키워드들을 Mecab 사용자 정의사전에 추가 
4. Mecab으로 tts의 content 내용을 토큰화
5. 토큰화된 content와 tts의 info(진짜, 가짜 여부)를 바탕으로 fastText 모델 학습
6. fastText 모델의 하이퍼 파라미터 튜닝을 통한 성능(정확도) 개선
7. 개선한 모델의 tvs 예측 정확도는 98.85%
8. news_test_pub set을 토큰화하고 학습된 fastText 모델로 결과 예측
9. 공모전 종료 후, 주최측 평가 결과로 news_test_pub set 예측 정확도는 97%

### 활용 및 기대효과
모델을 사용하여 인터넷 경제 기사의 진위 판단 가능
