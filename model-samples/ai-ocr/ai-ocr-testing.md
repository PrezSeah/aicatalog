
**AI Model : AI OCR - Testing**

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

![](https://github.com/PrezSeah/pretrained-model-info/raw/main/model-samples/ai-ocr/ai-ocr-testing_files/image004.png)

**Sample Response**

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