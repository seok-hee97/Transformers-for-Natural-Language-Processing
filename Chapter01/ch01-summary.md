#  CH01 : Getting Started with the Model Architeture of the Transformer

Topics covered in this chapter
- The background of the Transformer
- The architecture of the Transformer
- The Transformer's self-attention model
- The encoding and decoding stacks
- Input and output embedding
- Positional embedding
- Self-attention
- Multi-head attention
- Masked multi-attention
- Residual connections
- Normalization
- Feddforward network
- Output probabilites



- (1902) Markov Decision Processes(MDPs),    
  Markov Chains & Markov Processes

- (1950) Alan Turing Computing Machinery and Intelligence
  독일군 메시지를 해독한 Turing Machine 기반

- 1982 John Hopfield  RNNs(Recurrent Neural Networks)

- RNN이 진화해서 LSTM이 등장   

- CNN 텍스트 시퀀스에 적용(시퀀스 변환 및 모델리에도 널리 사용)
  CNN의 아키텍처는 효율적이기는 하지만, 매우 길고 복잡한 시퀀스에서    
  장기 종속성을 처리할 때 문제에 직면    



- Attention 개념 등장 시퀀스에서 단순히 마지막 토큰이 아니라, 다른 토큰을 들여다 보는것  
  (기존의 sequence-to-sequence 모델과 다른점 중 하나는 인코더의 마지막 은닉 상태   
   대신에 모든 은닉상태를 디코더에 전달하는 것. 디코더 단에서 출력 단얼을 예측하는   
   매 시점마다 인코더 전체 입력 문장을 다시 참고.      
   이 때 현 시점의 예측 대상 단어와 관계 가 있는 단어에      
   더 attention을 집중해서 참고)       


#### 트랜스포머의 부상
- 개발/NLP(Natural Language Processing)
[논문 리뷰] Attention Is All You Need, Transformer
https://simonezz.tistory.com/65


- Multi-head Attention.  
  - 시퀀스에 대한 보다 광범위하고 철저한 분석   
  - recurrence(순환) 배제에 따른 연산 축소   
  - 병렬화 구현에 따른 훈련 시간 축소   
  - 각 어텐션 메커니즘이 같은 입력 시퀀스에 대해 서로 다른 관점을 학습


트랜스포머 아키텍처 -> 놀라운 원거리 종속성(long-distance dependencies) 조사로 시작

트랜스포머 NLU(Natural Language Understanding) 새로운 방식으로  문서 및 구두 시퀀스에서 의미있는 표현으로 변환(transduction)을 수행