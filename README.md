## 1. Model 구성 
1. 1D CNN(1D Convolutional Neural Networks)
2. RELU Function
3. AvgPool
4. MSE Loss + AdamW
5. fully connected layer

## 2. 최종 성능최적화 방법
1. WINDOW_SIZE 조정
2. Threshold 조정
3. Epoch 조정
4. Feature Selection
5. 데이터 후 처리

## 3. 모델 선정 기준
1. TaR 점수가 높은 모델
2. Public 점수가 높은 모델

## 4. 최종 모델 성능
1. Test data TaPR : THRESHOLD: 0.0100 F1: 0.6169 (TaP: 0.7825, TaR: 0.5091) 
2. Public score : 0.50217
3. Private score : 0.53148

## 5. 시도한 방법론 (최종 사용X)
1. LSTM AutoEncoder
2. GramianAngularField를 이용해서 시계열 이미지를 이미지로 변환 후 2D CNN -> 용량이 너무 커서 후보 탈락
3. spectrogram, wavelet을 활용한 time series analysis -> 1초의 데이터양이 너무 적어 실패


## 6. Path 정보
- Data Path
  + traing data : ./data/train/
  + test data : ./data/test/
  + validation data : ./data/validation/

- Model Path
  + model 저장 경로 : ./data/{model_name}.model
  
- Submission Path
  + submission 저장 경로 : ./data/
  + sample path : ./data/sample_submission.csv
  + 최종제출 submisstion : ./data/ MODEL_NAME + '_threshold_' + str(THRESHOLD) + '_submissionVer4.csv'
  
- TaPR Lib path
  + whl file : ./eTaPR-21.8-py3-none-any.whl


## 7. Library 버전


## 8. 작업환경
