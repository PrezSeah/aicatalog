
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

curl -X POST "http://localhost:5000/model/predict" -H "accept: application/json" -H "Content-Type: multipart/form-data" -F "image=@x15.png;type\=image/png"

**Sample Input**

![](aI-image-segmentation-map-description_files/image002.jpg)

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