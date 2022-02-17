
**AI Model : AI Image Colorizer - Description**

**Overview**

This repository contains code to instantiate and deploy an image translation model. This model is a Generative Adversarial Network (GAN) that was trained on COCO dataset images converted to grayscale and produces colored images. The input to the model is a grayscale image (jpeg or png), and the output is a colored 256 by 256 imageThe code in this repository deploys the model as a web service in a Docker container.

**Model Metadata**

Domain : Vision

Application : Image Coloring

Industry : General

Framework : Tensorflow

Training Data : COCO Dataset

Input Data Format : PNG /JPEG Image

**Dockehub** **Link**

https://hub.docker.com/r/codait/max-image-colorizer

**Deployment**

Deployment from dockerhub:  
docker run -it -p 5000:5000 codait/max-image-colorizer

**Model Testing**

**Model Testing cURL command**

curl -X POST "http://localhost:5000/model/predict" -H "accept: application/json" -H "Content-Type: multipart/form-data" -F "image=@lion.jpg;type\=image/jpeg" --output lion\_c.jpg

**Model Testing Python Code**

· Download the test image from the link :  
https://github.com/PrezSeah/pretrained-model-info/tree/main/model-samples/ai-image-colorizer/sample\_input

· Ensure to have python / anaconda in your system

· Run the following snippet (keep the test image in working directory or provide the image location in the code)

import requests

res = requests.post('http://localhost:5001/model/predict', 

 files = {'image' : ('lion.jpg', open('sample\_input/lion.jpg', 'rb'), 'image/png')})

res.content  

**Sample Input**

![](https://github.com/PrezSeah/pretrained-model-info/raw/main/model-samples/ai-image-colorizer/ai-image-colorizer-description_files/image006.jpg)

**Sample Response**

![](https://github.com/PrezSeah/pretrained-model-info/raw/main/model-samples/ai-image-colorizer/ai-image-colorizer-description_files/image007.jpg)
