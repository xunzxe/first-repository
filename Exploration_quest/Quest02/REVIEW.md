# AIFFEL Campus Code Peer Review Templete
> - 코더 : 강대식, 김동규, 서은재
> - 리뷰어 : 김기홍, 김주현
  
  
# PRT(Peer Review Template)
[ ]  **1. 주어진 문제를 해결하는 완성된 코드가 제출되었나요?**
* 문제에서 요구하는 기능이 모두 정상적으로 동작하는 것을 확인하였습니다. 
  
[ ]  **2. 핵심적이거나 복잡하고 이해하기 어려운 부분에 작성된 설명을 보고 해당 코드가 잘 이해되었나요?**
* 주석을 매우 적극적으로 사용해 전반적으로 코드의 가독성이 매우 높습니다.  
  
[ ]  **3. 에러가 난 부분을 디버깅하여 “문제를 해결한 기록”을 남겼나요? 또는 “새로운 시도 및 추가 실험”을 해봤나요?**
* 인코더 부분을 구성할 때 LSTM 레이어를 한 개 더 연결해 총 4개로 구성해서 훈련을 진행한 부분과, seq2seq with attention 모델과의 성능 비교를 위해 사전 훈련된 워드 임베딩 중 하나인 GloVe 데이터베이스를 활용하는 TextRank 모델의 훈련을 진행한 부분이 특히 인상적이었습니다. 
  ```python
  # 인코더 설계 시작
  embedding_dim = 128
  hidden_size = 256
  
  # 인코더
  encoder_inputs = Input(shape=(text_max_len,))
  
  # 인코더의 임베딩 층
  enc_emb = Embedding(src_vocab, embedding_dim)(encoder_inputs)
  
  # 인코더의 LSTM 1
  # encoder_lstm1 = LSTM(hidden_size, return_sequences=True, return_state=True ,dropout = 0.4, recurrent_dropout = 0.4)
  encoder_lstm1 = LSTM(hidden_size, return_sequences=True, return_state=True ,dropout = 0.4)
  encoder_output1, state_h1, state_c1 = encoder_lstm1(enc_emb)
  
  # 인코더의 LSTM 2
  encoder_lstm2 = LSTM(hidden_size, return_sequences=True, return_state=True, dropout=0.4)
  encoder_output2, state_h2, state_c2 = encoder_lstm2(encoder_output1)
  
  # 인코더의 LSTM 3
  encoder_lstm3 = LSTM(hidden_size, return_sequences=True, return_state=True, dropout=0.4)
  encoder_output3, state_h3, state_c3 = encoder_lstm3(encoder_output2)
  
  # 인코더의 LSTM 4
  encoder_lstm4 = LSTM(hidden_size, return_sequences=True, return_state=True, dropout=0.4)
  encoder_outputs, state_h, state_c = encoder_lstm3(encoder_output3)
  ```
  ```python
  # 사전 훈련된 GloVe 다운로드 (실습에서 사용)
  import numpy as np
  import gensim
  from urllib.request import urlretrieve, urlopen
  import gzip
  import zipfile
       
  urlretrieve("http://nlp.stanford.edu/data/glove.6B.zip", filename="glove.6B.zip")
  zf = zipfile.ZipFile('glove.6B.zip')
  zf.extractall()
  zf.close()
       
  glove_dict = dict()
  f = open('glove.6B.100d.txt', encoding="utf8") # 100차원의 GloVe 벡터를 사용
  
  for line in f:
      word_vector = line.split()
      word = word_vector[0]
      word_vector_arr = np.asarray(word_vector[1:], dtype='float32') # 100개의 값을 가지는 array로 변환
      glove_dict[word] = word_vector_arr
  f.close()
  ```
  
[ ]  **4. 회고를 잘 작성했나요?**
* README.md 파일에 회고가 잘 작성되어 있습니다.   
  
[ ]  **5. 코드가 간결하고 효율적인가요?**
* 코드가 간결하고 가독성이 좋도록 작성되어 있습니다. 
  
  
# 참고 링크 및 코드 개선
```
# 코드 리뷰 시 참고한 링크가 있다면 링크와 간략한 설명을 첨부합니다.
# 코드 리뷰를 통해 개선한 코드가 있다면 코드와 간략한 설명을 첨부합니다.
```
