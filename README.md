## TU Wien: AI/ML in the Era of Climate Change (2024W)
The task involves quantizing both Object Detection models and LLM models.  
Since I was responsible for the Object Detection part, I will only elaborate on this section.

### Dataset
COCO dataset 2017  
https://cocodataset.org/#download

### Task
○ Get the model and use LiteRT (formerly TensorFlow Lite) to quantize the model
○ Choose the following three configurations (weights only):
  ■ float32
  ■ float 16
  ■ int8

### Backbone Model
Mask R-CNN with Inception ResNet V2 backbone
https://www.kaggle.com/models/tensorflow/mask-rcnn-inception-resnet-v2
○ Overview
    Mask R-CNN with Inception Resnet v2 (using regular Convolutions instead of Dilated ones). Trained on COCO 2017 dataset (Synchronous SGD across 8 GPUs) with batch size 16 (trained on images of 1024x1024 resolution).

### Result
![objectdetection](https://github.com/user-attachments/assets/38cc1853-a7fb-4bd9-ac38-4577fdd77803)
○ Significant Enhancement on Model Size and Inference Time for all configurations
○ Poor mean Average Precision

### Additional Result
<img width="1094" alt="스크린샷 2025-01-16 오전 2 21 11" src="https://github.com/user-attachments/assets/d7fb6bea-9cf0-463b-a8eb-10fa2f2a3797" />

### Further Discussion
Upon debugging the code, it was found that the low accuracy resulted from misalignment between the x-coordinates and y-coordinates of the ground truth and predictions. Despite making various efforts to fix this issue, no significant improvements could be achieved before the submission deadline. A proper method to align these coordinates needs to be explored in the future.



