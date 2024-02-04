# Analyzing Fake News with Transformers.    
트랜스포머에 의한 가짜 뉴스 분석    


#### Subjects.    

- 인지적 불협화(cognitive dissonance).   
- 가짜 뉴스에 대한 감정적 반응   
- 가짜 뉴스의 행위 표현(behavioral representation).  
- 가짜 뉴스에 대한 합리적 접근
- 가짜 뉴스에 해결 로드맵
- 센티먼트 분석 트랜스포머 작업을 소셜 미디어에 적용
- NER 및 SRL을 사용한 총기 규제 인지 분석   
- 트랜스포머가 추출한 정보를 사용하여 신뢰할 수 있는 웹사이트 찾기   
- 교육 목적을 위한 결과를 생성하기 위해 트랜스포머 사용   
- 객관적이면서도 비판적인 시각으로 트럼프 전 대통령의 트윗 읽는 방법     

#### 12.1 가짜 뉴스에 대한 감정적 반응     


##### 12.1.1 인지 불협화가 감정적 반응을 촉발    


- A.대립적 트윗 분석    
  
  ***Fake_News.ipynb***


- B.가짜 뉴스의 행동 표현   
  
  가짜 뉴스에 대한 three Phase 감정적 반응 경로를 나타냄   

  - Phase 1 : 새로운 뉴스   
  각 정보 출처에는 편향된 의견이 들어 있음   

  - Phase 2 : 합의     
    동의하지 않는다면 Phase 3로 이동   

    동의한다면 진짜 뉴스로 받아들여짐   

  - Phase 3 : 대립(또는 갈등 또는 충돌)    



#### 12.2 가짜 뉴스에 대한 합리적인 접근 방법    


##### 12.2.1 가짜 뉴스 해결 로드맵 정의


1. Incoming News
2. Consenus(Yes/No)
3. No -> Challenged - yes Conflict.  
4. Yes(Sentiment Analysis,NamedEntity Recognition(NER),SRL(Sentimantic Role Labeling, Reference to reliable web sites))



##### 12.2.2 총기 규제


- A. 센티먼트 분석   
- B. NER
- C. SRL
- D. 참조 사이트


##### 12.2.3 COVID-19 트럼프 전 대통령 트윗    


- A.SRL

#### 12.3 나가기 전에   
존재하지 않는 은탄환 트랜스포머 모델을 찾는 것보다 문제에 트랜스포머를 적용하는데 초점    


##### 12.3.1 은탄환을 찾아서   

DeBERTa : Decoding-enhanced BERT with Disentangled Attention
DeBERTa에 구현된 두 가지 주요 아이디어   
- 두 벡터를 별도로 훈련시키기 위해 트랜스포머 모델의 내용과 위치를 분리(disentangle)
- 디코더에서 절대 위치를 사용하여 사전 훈련 과정에서 마스킹된 토큰을 예측   
  
https://github.com/microsoft/DeBERTa




##### 12.3.2 신뢰할 수 있는 훈련 방법을 찾아서    

PET와 같은 더 작은 모델로 신뢰할 수 있는 훈련 방법을 찾는 것도    
해결책이 될 수 잇음

SuperGLUE 리더보드에서 좋은 위치에 있다고 해서, 해당 모델이  시퀀스 예측에 대해  
의료,법률 및 기타 중요한 분야에서 고품질의 의사 결정을 제공할 것이라는 의미는 아님   


특정 주제에 대한 맞춤형 훈련 솔루션을 차즌ㄴ것이 더 생산적일 수도 있음    

