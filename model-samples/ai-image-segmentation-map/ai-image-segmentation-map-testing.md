
**AI Model : AI Image Segmentation Map - Testing**

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

![](https://github.com/PrezSeah/pretrained-model-info/raw/main/model-samples/ai-image-segmentation-map/ai-image-segmentation-map-testing_files/image001.jpg)

**Sample Response**

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