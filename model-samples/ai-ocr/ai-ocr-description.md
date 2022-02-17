
**AI Model : AI OCR - Description**

**Overview**

This repository contains code to instantiate and deploy an optical character recognition model. This model takes an image of text as an input and returns the predicted text. This model was trained on 20 samples of 94 characters from 8 different fonts and 4 attributes (regular, bold, italic, bold + italic) for a total of 60,160 training samples. Please see the paper An Overview of the Tesseract OCR Engine for more detailed information about how this model was trained.

**Model Metadata**

Domain : Image & Video

Application : Optical Character Recognition

Industry : General

Framework : N/A

Training Data : Tesseract Data Files

Input Data Format : Image (PNG/JPG)

**Dockehub** **Link**

https://hub.docker.com/r/codait/max-ocr

**Deployment**

Deployment from dockerhub:

docker run -it -p 5000:5000 codait/max-ocr

**Model Testing**

**Model Testing cURL command**

curl -X POST "http://localhost:5000/model/predict" -H "accept: application/json" -H "Content-Type: multipart/form-data" -F [image=@ocr\_sample.PNG;type=image/png](mailto:image=@ocr_sample.PNG;type=image/png)

**Model Testing Python Code**

· Download the test image from the link :  
https://github.com/PrezSeah/pretrained-model-info/tree/main/model-samples/ai-ocr/sample\_input

· Ensure to have python / anaconda in your system

· Run the following snippet (keep the test image in working directory or provide the image location in the code)

import requests

res = requests.post('http://localhost:5000/model/predict', 

 files = {'image' : ('ocr\_sample.PNG', open('sample\_input/ocr\_sample.PNG', 'rb'), 'image/png')})

res.content  
  
**Sample Input**

![](https://github.com/PrezSeah/pretrained-model-info/raw/main/model-samples/ai-ocr/ai-ocr-description_files/image001.png)

**Sample Output**

{

 "status": "ok",

 "text": \[

 \[

 "Explain",

 "that",

 "Stuff!",

 "01234567490"

 \]

 \]

}
