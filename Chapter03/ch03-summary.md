# [CH03 백지 상태에서 RoBERTa 모델 사전훈련시키기]
Pretraining a RoBERTa Model from Scratch

- RoBERTa 및 DistilBERT 형 모델
- 백지 상태에서 토크나이저 훈련시키기
- 바이트 수준 바이트 썅 인코딩
- 훈련된 토크나이저 저장
- 사전훈련 프로세스를 위한 토크나이저 재생성
- 백지 상테에서의 RoBERTa 모델 촉히ㅘ
- 모델의 구성 탐구
- 모델의 8천만 파라미터 타무
- 트레이너를 위한 데이터셋 구축
- 트레이너 초기화
- 모델 사전훈련
- 모델 저장
- 마스킹된 언어 모델링 다운스트림 작업에 모델 적용하기




KantaiBERT는 BERT 아키텍처를 기반으로 하는 RoBERT(Robustly Optimized BERT Pretraining Approach)형 모델



RoBERTa 다운스트림 작업을 우히나 트랜스포머 사전훈련 성능 항샹.   
사전훈련 메커니즘 개선
ex) WordPiece 토큰화 사용 x, 바이트 수준 BPE(Byte Pair Encoding. 바이트쌍 인코딩)


트랜스포머에 주로 사용되는 tokenizer (BPE, WordPiece, SentencePiece)    -> BERT, DistilBERT, Electra에서 사용

WordPiece는 먼저 훈련 데이터에 이는 모든 문자를 포함하도록 어휘를 초기화하고 주어진 수의 병합 규칙을 점진적으로 학습.  
가장 빈번한 기호 쌍응ㄹ 선택하지 않고 일단 어휘에 추가된 훈련 데이터의 우도를 최대화하는 기호 쌍을 선택



