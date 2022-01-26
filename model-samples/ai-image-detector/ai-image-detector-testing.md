
**AI Model : AI Image Detector - Testing**

**Model Testing cURL command**

curl -X POST "http://localhost:5000/model/predict" -H "accept: application/json" -H "Content-Type: multipart/form-data" -F "image=@lion.jpg;type\=image/jpeg" --output lion\_c.jpg

**Model Testing Python Code**

· Download the test image from the link :  
https://github.com/PrezSeah/pretrained-model-info/tree/main/model-samples/ai-image-detector /sample\_input

· Ensure to have python / anaconda in your system

· Run the following snippet (keep the test image in working directory or provide the image location in the code)

import requests

res = requests.post('http://localhost:5000/model/predict', 

 files = {'image' : ('lion.jpg', open('sample\_input/lion.jpg', 'rb'), 'image/png')})

res.content  
  

**Sample Input**

![](https://github.com/PrezSeah/pretrained-model-info/raw/main/model-samples/ai-image-detector/ai-image-detector-testing_files/image005.jpg)

**Sample Response**

{

 "status": "ok",

 "predictions": \[

 {

 "label\_id": "142",

 "label": "field\_road",

 "probability": 0.36829647421836853

 },

 {

 "label\_id": "359",

 "label": "wheat\_field",

 "probability": 0.29098382592201233

 },

 {

 "label\_id": "258",

 "label": "pasture",

 "probability": 0.0991949662566185

 },

 {

 "label\_id": "86",

 "label": "cemetery",

 "probability": 0.03284231573343277

 },

 {

 "label\_id": "341",

 "label": "tundra",

 "probability": 0.03229227662086487

 }

 \]

}
