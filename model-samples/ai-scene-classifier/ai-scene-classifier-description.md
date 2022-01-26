
**AI Model : AI Scene Classifier - Description**

**Overview**

This repository contains code to instantiate and deploy an image classification model. This model recognizes the 365 different classes of scene/location in the Places365-Standard subset of the Places2 Dataset. The model is based on the Places365-CNN Model and consists of a pre-trained deep convolutional net using the ResNet architecture, trained on the ImageNet-2012 data set. The pre-trained model is then fine-tuned on the Places365-Standard dataset. The input to the model is a 224x224 image, and the output is a list of estimated class probabilities.  
  

**Model Metadata**

Domain : Vision

Application : Image Classification

Industry : General

Framework : Pytorch

Training Data : Places365

Input Data Format : Image (RGB/HWC)

**Dockehub** **Link**

https://hub.docker.com/r/codait/max-scene-classifier

**Deployment**

Deployment from dockerhub:

docker run -it -p 5000:5000 codait/max-scene-classifier

**Model Testing**

curl -X POST "http://localhost:5000/model/predict" -H "accept: application/json" -H "Content-Type: multipart/form-data" -F "image=@rainforest.PNG;type=image/png"

**Sample Input**

![](https://github.com/PrezSeah/pretrained-model-info/raw/main/model-samples/ai-scene-classifier/ai-scene-classifier-description_files/image006.jpg)

**Sample Response**

{

 "status": "ok",

 "predictions": \[

 {

 "label\_id": "279",

 "label": "rainforest",

 "probability": 0.937177836894989

 },

 {

 "label\_id": "150",

 "label": "forest/broadleaf",

 "probability": 0.04333578050136566

 },

 {

 "label\_id": "151",

 "label": "forest\_path",

 "probability": 0.006666921079158783

 },

 {

 "label\_id": "323",

 "label": "swamp",

 "probability": 0.004010303411632776

 },

 {

 "label\_id": "36",

 "label": "bamboo\_forest",

 "probability": 0.0019691523630172014

 }

 \]

}