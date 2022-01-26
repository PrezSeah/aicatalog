
**AI Model : AI Object Detector - Testing**

**Model Testing cURL command**

curl -X POST "http://localhost:5000/model/predict?threshold\=0.5" -H "accept: application/json" -H "Content-Type: multipart/form-data" -F [image=@x15.png;type=image/png](mailto:image=@x15.png;type=image/png)

**Model Testing Python Code**

· Download the test image from the link :  
https://github.com/PrezSeah/pretrained-model-info/tree/main/model-samples/ai-object-detector/sample\_input

· Ensure to have python / anaconda in your system

· Run the following snippet (keep the test image in working directory or provide the image location in the code)

import requests

res = requests.post('http://localhost:5000/model/predict', 

 files = {'image' : ('x15.PNG', open('sample\_input/x15.PNG', 'rb'), 'image/png')})

res.content  
  

**Sample Input**

![](https://github.com/PrezSeah/pretrained-model-info/raw/main/model-samples/ai-object-detector/ai-object-detector-testing_files/image002.jpg)

**Sample Response**

{

 "status": "ok",

 "predictions": \[

 {

 "label\_id": "18",

 "label": "dog",

 "probability": 0.8639843463897705,

 "detection\_box": \[

 0.41566020250320435,

 ...

 \]

 },

 {

 "label\_id": "1",

 "label": "person",

 "probability": 0.564839243888855,

 "detection\_box": \[

 0.893539309501648,

 ...

 \]

 },

 \]

}