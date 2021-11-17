# SK AI Challenge
진행 기간: 10/12~10/27
## 기술 주제  
SKT에서 제공하는 CCTV영상 이미지 데이터를 준지도학습 기반으로 학습하는 객체탐지 (Semi-supervised Object Detection) 모델 구현

* baseline code 없음  
* 평가지표 : mAP@IoU=0.5  
* 데이터 유출 방지와 GPU 할당을 위해 별도의 워크스페이스에서 진행하였습니다. *(파일을 pdf로밖에 가져오지 못했습니다.)*  


## 사용 모델 : Faster-RCNN
FasterRCNN API 사용 : torchvision.models.detection.fasterrcnn_resnet50_fpn(pretrained=True) 

## Source Code  
#### `EDA`  
#### `preprocessing`
          
#### `FasterRCNN_SSL_1`  
- labeled data로 모델 학습하여 구한 weight로 unlabeled data의 annotation 추론  

#### `FasterRCNN_SSL_2  `  
- annotation 구한 unlabeled data + labeled data로 모델 학습  

#### `utils_ObjectDetection.py  `  
- 모델 prediction mAP 계산  

#### `get_result_csv  `  
- 모델 weight 4개의 예측 결과에 WBF(Weighted Boxes Fusion) 적용, csv파일로 저장

## 결과
mAP@IoU = 0.5 기준으로 53.3 에 도달했습니다. (전체 순위 중 10위)
