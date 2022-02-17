
**AI Model : AI Human Pose Estimator- Description**

**Overview**

This model generates captions from a fixed vocabulary that describe the contents of images in the COCO Dataset. The model consists of an encoder model - a deep convolutional net using the Inception-v3 architecture trained on ImageNet-2012 data - and a decoder model - an LSTM network that is trained conditioned on the encoding from the image encoder model. The input to the model is an image, and the output is a sentence describing the image content.  
  
The model is based on the Show and Tell Image Caption Generator Model.

**Model Metadata**

Domain : Vision

Application : Human Pose Estimation

Industry : Multi

Framework : Tensorflow

Training Data : COCO

Input Data Format : Image File

**Dockehub** **Link**

https://hub.docker.com/r/codait/max-human-pose-estimator

**Deployment**

Deployment from dockerhub:

docker run -it -p 5000:5000 codait/max-human-pose-estimator

**Model Testing**

**Model Testing cURL command**

curl -X POST "http://localhost:5001/model/predict" -H "accept: application/json" -H "Content-Type: multipart/form-data" -F [file=@dance\_image.PNG;type=image/png](mailto:file=@dance_image.PNG;type=image/png)  
  

**Model Testing Python Code**

· Download the test image from the link :  
[https://github.com/PrezSeah/pretrained-model-info/tree/main/model-samples/ai-human-pose-estimator/sample\_input](https://github.com/PrezSeah/pretrained-model-info/tree/main/model-samples/ai-human-pose-estimator/sample_input)

· Ensure to have python / anaconda in your system

· Run the following snippet (keep the test image in working directory or provide the image location in the code)

import requests

res = requests.post('http://localhost:5000/model/predict', 

 files = {'file' : ('dance\_image.PNG', open('sample\_input/dance\_image.PNG', 'rb'), 'image/png')})

res.content  

**Sample Input**

![](https://github.com/PrezSeah/pretrained-model-info/raw/main/model-samples/ai-human-pose-estimator/ai-human-pose-estimator-description_files/image001.png)

**Sample Response**

{

 "status": "ok",

 "predictions": \[

 {

 "human\_id": 0,

 "pose\_lines": \[

 {

 "line": \[

 123,

 52,

 },

"body\_parts": \[

 {

 "part\_id": 0,

 "part\_name": "Nose",

 "score": "0.85537",

 "x": 130,

 "y": 42

 },

 {

 "part\_id": 1,

 "part\_name": "Neck",

 "score": "0.68294",

 },

 {

 "part\_id": 2,

 "part\_name": "RShoulder",

 "score": "0.58194",

 }
