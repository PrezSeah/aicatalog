
**AI Model : AI Image Segmentation Map - Description**

**Overview**

Model takes an image file as an input and returns a segmentation map containing a predicted class for each pixel in the input image. This repository contains 2 models trained on PASCAL VOC 2012. One model is trained using the xception architecture and produces very accurate results.

**Model Labels**

The segmentation map returns an integer between 0 and 20 that corresponds to one of the labels below for each pixel in the input image. The first nested array corresponds to the top row of pixels in the image and the first element in that array corresponds to the pixel at the top left hand corner of the image.

**Model Metadata**

Domain : Image & Video

Application : Object Detection

Industry : General

Framework : Tensorflow

Training Data : VOC2012 ~10k images

Input Data Format : Image (PNG/JPG)

**Dockehub** **Link**

https://hub.docker.com/r/codait/max-image-segmenter

**Deployment**

Deployment from dockerhub:

docker run -it -p 5000:5000 codait/max-image-segmenter

**Model Testing**

**Model Testing cURL command**

curl -X POST "http://localhost:5000/model/predict" -H "accept: application/json" -H "Content-Type: multipart/form-data" -F "image=@x15.png;type=image/png"

**Model Testing Python Code**

· Download the test image from the link :  
https://github.com/PrezSeah/pretrained-model-info/tree/main/model-samples/ai-image-segmentation-map/sample\_input

· Ensure to have python / anaconda in your system

· Run the following snippet (keep the test image in working directory or provide the image location in the code)

import requests

res = requests.post('http://localhost:5000/model/predict', 

 files = {'image' : ('x15.png', open('sample\_input/x15.png', 'rb'), 'image/png')})

res.content  
  
**Sample Input**

![](https://github.com/PrezSeah/pretrained-model-info/raw/main/model-samples/ai-image-segmentation-map/ai-image-segmentation-map-description_files/image002.jpg)

**Sample Output**

{

 "status": "ok",

 "image\_size": \[

 256,

 128

 \],

 "seg\_map": \[

 \[

 0,

 0,

 ...,

 15,

 ...,

 \],

 ...,

 ...,

 ...,

 \[

 ...,

 15,

 15,

 15,

 ...,

 0

 \]

 \]

}
