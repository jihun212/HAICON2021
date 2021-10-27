# 산업제어시스템 보안위협 탐지 AI 경진대회
> 산업제어시스템 보안위협 탐지

#### 참고문헌
- 본 대회 데이터셋(HAI 21.03, HAI 20.07), HAICon 2020, 평가도구를 활용한 논문 작성 시, 인용 문헌은 다음과 같습니다.
- HAI 21.03, HAICon 2020
> Hyeok-ki Shin, Woomyo Lee, Jeong-Han Yun, and Byung-Gil Min, "Two ICS Security Datasets and Anomaly Detection Contest on the HIL-based Augmented ICS Testbed", CSET'21: Workshop on Cyber Security Experimentation and Test, 2021
- HAI 20.07
> Hyeok-ki Shin, Woomyo Lee, Jeong-Han Yun, and Hyoungchun Kim, "HAI 1.0: HIL-based Augmented ICS Security Dataset", CSET'20: Workshop on Cyber Security Experimentation and Test, 2020. 
- TaPR
> Won-seok Hwang, Jeong-Han Yun, Jonguk Kim, and Hyoungchun Kim, "Time-Series Aware Precision and Recall for Anomaly Detection - Considering Variety of Detection Result and Addressing Ambiguous Labeling", CIKM'19: Proceedings of the 28th ACM International Conference on Information and Knowledge Management, 2019.

※ 대회 평가도구(eTaPR)는 TaPR의 업그레이드 버전입니다. 

### 팀
- **최원석 교수님**
- **이경연** : 한성대학교 사이버보안트랙 학부생
- **정예주** : 한성대학교 사이버보안트랙 학부생
- **최지훈** : 한성대학교 사이버보안트랙 학부생
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
- torch==1.9.0
- matplotlib==3.4.3
- pandas==1.3.3
- easydict==1.9
