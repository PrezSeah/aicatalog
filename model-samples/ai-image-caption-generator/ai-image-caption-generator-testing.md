
**AI Model : AI Image Caption Generator - Testing**

**Model Testing cURL command**

curl -X POST "http://localhost:5000/model/predict" -H "accept: application/json" -H "Content-Type: multipart/form-data" -F image=@football.PNG;type\=image/png

**Model Testing Python Code**

· Download the test image from the link :  
[https://github.com/PrezSeah/pretrained-model-info/tree/main/model-samples/ai-image-caption-generator/sample\_input](https://github.com/PrezSeah/pretrained-model-info/tree/main/model-samples/ai-image-caption-generator/sample_input)

· Ensure to have python / anaconda in your system

· Run the following snippet (keep the test image in working directory or provide the image location in the code)

import requests

res = requests.post('http://localhost:5000/model/predict', 

 files = {'image' : ('football.PNG', open('sample\_input/football.PNG', 'rb'), 'image/png')})

res.content

**Sample Input**

![](ai-image-caption-generator-testing_files/image002.jpg)

**Sample Response**

{

 "status": "ok",

 "predictions": \[

 {

 "index": "0",

 "caption": "a soccer player is kicking a soccer ball .",

 "probability": 0.0018393118846582502

 },

 {

 "index": "1",

 "caption": "a soccer player is kicking a soccer ball",

 "probability": 0.0004151401108329707

 },

 {

 "index": "2",

 "caption": "a soccer player is kicking a ball on the field .",

 "probability": 0.00022804233787542945

 }

 \]

}
