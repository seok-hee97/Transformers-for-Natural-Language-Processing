#### [ch04-Downstream NLP Tasks with Transformers]



트랜스포머는 사전 훈련된 모델을 활용해서 다운스트림 NLU(Natural Language Understanding)작업을 수행할때 
잠재력이 높음


SuperGLUE 는 Google DeppMind, Faceboiok, AI, 뉴욕대학교, 워싱턴 대학교가 협력하여 
NLP 서능을 측정하기 위한 휼률한 예


이 장에서 다루는 주제    

- 변환 및 귀납을 위한 기계 대 인간 지능
- NLP 변환 및 귀납 과정
- 트랜스포머 성능 대 인간 베이스라인 측정
- 측정 방법(정확도, F1 점수, MCC)
- 밴치마크 작업과 데이터셋
- SuperGLUE 다운스트림 작업
- CoLA의 언어적 수용도
- SST-2를 사용한 감정 분석
- Winograd 스키마
  




#### 4.1 트랜스포머의 변환 및 귀납 상속    
트랜스포머는 배우지 않은 작업에 자신의 지식을 적용하는 독특한 능력 가지고있음

ex]
BERT 트랜스포머는 시퀀스 대 시퀀스 및 마스킹된 언어 모델링을 통해 언어를 획득

BERT 트랜스포머는 처음 상태에서부터 학습하지 않은 다운스트림 작업을 수행하도록 미세 조정 가능



##### 4.1.1 인간 지능 스택
점차적으로 출력은 알아듣기 어려운(burbling)언어가 되고, 그런 다음 구조화된 언어가 됨




#### 4.1.2 기계 지능 스택    
컴퓨터 비전은 이미지를 식별하지만 언어의 문법적 구조를 포함 x.    
음성 인식은 소리를 단어로 변환하여 우리를 문자 언어(written languager)로 리턴



#### 4.2 트랜스포머 성능 대 인간 베이스라인    



##### 4.2.1 메트릭에 의한 모델 평가

this section  GLUE와 SuperGLUE에서 사용하는 세가지 측량 채점 방법 분석


###### A.정확도 점수   
어떤 변형을 사용하든 정확도 점수는 실용적인 평가.    
점수 함수는 각 결과에 대해 간단한 참 또는 거짓 값을 계산



##### B.F1 점수.   
(주로 이진 분류(classification)).    
F1 점수는 클래스 분포가 고르지 않은 데이터셋에 대해 유연한 접근 방식 도입    
F1 점수는 가중된 정밀도(precision)와 재현율(recall)을 사용    
정밀도와 재현율 값의 가중 평균


F1-score = 2*(precision*recall)/(precision + recall)


[reference]   
[F1 score와 머신러닝 - 정의, 원리 , 계산법, 한계, 대응방안   
https://www.thedatahunt.com/trend-insight/f1-scoree    


##### C.MCC(Matthews Correlation Coefficient, 메튜스 상관 계수)    
MCC는 2장 BERT altp whwjddml Matthews 상관 계수를 사용한 평가 섹션에서 설명 및 구현되었음.   
MCC cka





자연어 처리 성능 평가 지표 - Matthews Correlation Coefficient.   
https://choice-life.tistory.com/82



#### 4.2.2 벤치마크 작업과 데이터셋

트랜스포머 성능 증명 3가지 조건
- 모델
- 데이터셋 기반 작업
- 이 장의 메트릭에 의한 모델 평가 섹션에 설명된 메트릭





GLUE(Gener alLanguageUnderstandingEvaluation. 일반언어이해평가)





#### 4.2.3 SuperGLUE 벤치마크 작업 정의

##### A. BoolQ
BoolQ는 부울 예 또는 아니오 응답작업



##### B. CB(Commitment Bank)
어려운 수반(entailment) 작업


ex].  
중립(neutial), 수반(antalment), 모순(contredlicion)으로 레이블링 



##### C. MultiRC(Multi-Sentence Reading Comprehension, 다문장 독해력)



##### D. ReCoRD(Rendering Comprehension with Commonsense Reasoning Dataset)

뉴스 데이터에서 상식적인 추론을 사용



##### E. RTE(Recognizing Textual Entailment 텍스트 함의 인식)
트랜스포머 모델이 전제를 읽고, 가설을 검토, 수반 가설 상태(entailment hypothesis status) 레이블 예측



##### F.WiC(Words in Context 문맥 단어)
모호한 단어를 처리하는 모델의 능력을 테스트

##### G.WSC(The Winograd Schema Challange)
명획화(disambiguation problem)에 초점





#### 4.3.3 MRPC(Microsoft Research Paraphrase Corpus)
웹의 새로운 소스에서 추출한 문장 쌍들이 있음

각 쌍의 밀접하게 관련된 속성을 기반으로 문장이 동등(equivalent)한지 ㅣ여부를 나타내기 위해 사람이 주석 담

- 같은 의미(parapharse equivalent)
- 의미론적 등가(STS-B 관련 다음 섹션 참고)
  



#### 4.3.4 Winograd 스키마
WSC(The Wingard Schema Challenge) 섹션에서 Winograd 스키마 설명

