# Detecting Customer Emotion to Make Predictions.    
예측을 위한 고객 감정 감지     


#### Subjects     
- 센티먼트 분석을 위한 SST
- 긴 시퀀스에 대한 구성(compositionality) 정의   
- AllenNLP(RoBERTa)를 사용한 센티먼트 분석    
- 트랜스포머의 새로운 영역을 탐구하기 위해 복잡한 문장 실행  
- Hugging Face 센티먼트 분석 모델 사용    
- 센티먼트 분석을 위한 DistillBERT.   
- MiniLM-L12-H384-uncased로 실험    
- RoBERTa-large-mini 탐구    
- BERT 기반 다국어 모델 검토      


#### 11.1 시작하기: 센티먼트 분석 트랜스포머들   

SST 탐구, 그다음 AllenNLP사용해서 RoBERa-large 트랜스포머 실행    


#### 11.2 SST.    

- 센티먼트 분석은 문장에서 긍정적인 단어와 부정적인 단어를 세는 것으로     
  축소될 수 없음     
- 트랜스포머 모델 또는 모든 NLP 모델은 복잡한 문장의 성분들이 논리적인 형태 규칙과    
  어떻게 서로 어울리는지 이해하기 위해 PoC를 배울 수 있어야 함    
- 트랜스포머 모델은 복잡한 문장과 미묘함을 해석하기 위해 벡터 공간을 구축할 수 있어야 함   


##### 11.2.1 RoBERT-large를 사용한 센티먼트 분석    


***SentimentAnalysis.ipynb***


#### 11.3 센티먼트 분석에 의한 고객 행동 예측    


##### 11.3.1 DistillBERT를 사용한 센티먼트 분석    


***SentimentAnalysis.ipynb***




##### 11.3.2 Hugging Face 모델 목록을 이용한 센티먼트 분석     

Hugging Face 모델 목록중    
Tasks 항목들 중 Text Classification을 선택    


- A.SST에 대한 DistilBERT.  
  
  distilbert-bas-uncased-fintuned-sst-2-english 모델은   
  SST에 대해 미세 조정됨    

- B. MiniLM-L12-H384-uncased.  
  MiniLM-L12-H384-uncased는 더 나은 성능을 얻기 위해, BERT 모델의   
  다른 조정 중에서도 교사의 마지막 self-attention 레이어 크기를 최적화함   
  12개의 레이어, 12개의 헤드 및 33M 파라미터를 가지며 BERT 기반보다   
  2.7배 빠름    

- C. RoBERTa-large-mnli.  
  다 장르 자연어 추론(Mulit-Genre Natural Language Inference. 이하 MultiNLI) 작업    
  은 고객이 의미하는 바를 파악하려고 할 때 복잡한 문장의 해석을 해결하는 데 도움이 될 수 있음    
  추론 작업은 시퀀스가 다음 것을 수반하는지 여부를 결정해야함    

  우리는 입력 형식을 지정하고, 시퀀스 분할 토큰으로 시퀀스를 분할해야함     

- D. BERT 기반 다국어 모델     
  



#### 11.4 요약    
PoC는 직관적인 개념 x.    
PoC는 트랜스포머 모델이 전체 문장을 이해하기 위해서는 문자으이 모든 성분으로 이해해야 한다는 것을 의미    
여기서는 문장 세그먼트 간의 링크를 제공하는 논리 형태 규직이 포함    

센티먼트 분석을 이론적 어려움 때문에 많은 양의 트랜스포머 모델 훈련, 강력한 기계 및 인적 자원을 필요로 함   
