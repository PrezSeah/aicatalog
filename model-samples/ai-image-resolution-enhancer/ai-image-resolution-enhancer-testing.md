
**AI Model : AI Image Resolution Enhancer - Testing**

**Model Testing cURL command**

curl -X POST "http://localhost:5000/model/predict" -H "accept: application/json" -H "Content-Type: multipart/form-data" -F "image=@image\_enhancement.PNG;type\=image/png"

**Model Testing Python Code**

· Download the test image from the link :  
 [https://github.com/PrezSeah/pretrained-model-info/tree/main/model-samples/ai-image-resolution-enhancer/sample\_input](https://github.com/PrezSeah/pretrained-model-info/tree/main/model-samples/ai-image-resolution-enhancer/sample_input)

· Ensure to have python / anaconda in your system

· Run the following snippet (keep the test image in working directory or provide the image location in the code)

import requests

res = requests.post('http://localhost:5000/model/predict', 

 files = {'image' : ('image\_enhancement.PNG', open('sample\_input/image\_enhancement.PNG', 'rb'), 'image/png')})

res.content

**Sample Input**

![](https://github.com/PrezSeah/pretrained-model-info/raw/main/model-samples/ai-image-resolution-enhancer/ai-image-resolution-enhancer-testing_files/image002.jpg)

**Sample Response**

![](https://github.com/PrezSeah/pretrained-model-info/raw/main/model-samples/ai-image-resolution-enhancer/ai-image-resolution-enhancer-testing_files/image004.jpg)
