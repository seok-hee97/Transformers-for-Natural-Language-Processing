## [CH05. 트랜스포머 기계 번역]


#### [Subject]     
- 기계 번역 정의   
- 인간 트랜스덕션   
- 기계 트랜스덕션    
- WMT 데이터셋 전처리    
- BLEU로 기계 번역 평가    
- 기하적 평가    
- Chencherry 스무딩   
- 즉시 실행(eager execution) 활성화   
- Trax로 영어-독일어 문제 초기화하기    


#### 5.1 기계번역의 정의

##### 5.1.1 인간 트랜스덕션과 번역

인간 변환 언어 A의 문장을 가져와  의미를 인지적 표현(congitive representation)




###### 5.2.1 원시 데이터 전처리 
이 섹션에서는 europal-v7.fr-en.en alc europarl.fr-en.fr을 전처리함   

***read.py***


##### 5.2.2 데이터셋 전처리 마무리
이전 섹션에서 정리된 데이터셋들을 로드한 다음, 전처리가 마무리되면 그들을 저아한느 함수 정의   

***read_clean.py***



### 5.3 BLEU에 의한 기계 번역 평가

사람의 번역을 기계 번역과 단어 단위로 비교하면 효율적인 결과를 얻을 수 있음

BLEU(Bilingual Evaluation Understudy Score)라고 명명

이 섹션에서는 NLTK(Natural Langauge Toolkit)를 사용하여 BLEU 구현





##### 5.3.2 스무딩 기법 적용

스무딩은 매우 효율적인 방법. BLEU 스무딩은 트랜스포머의 softmax 출력에     
적용된 레이블 스무딩으로 거슬로 올라감


- A.Chencherry 스무딩   
  Chen과 Cherry(2014)는 0이 되었을 값들에 ε를 더함으로써 후보 평가를 스무딩하는    
  흥미로운 방법으로 색



##### 5.4 Trax에 의한 번역

***Trax_Translation.ipynb***