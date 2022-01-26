
**AI Model : AI Image Colorizer - Testing**

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

![](https://github.com/PrezSeah/pretrained-model-info/raw/main/model-samples/ai-image-colorizer/ai-image-colorizer-testing_files/image004.jpg)

**Sample Response**

![](https://github.com/PrezSeah/pretrained-model-info/raw/main/model-samples/ai-image-colorizer/ai-image-colorizer-testing_files/image006.jpg)
