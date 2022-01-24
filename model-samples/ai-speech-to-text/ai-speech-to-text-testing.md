
**AI Model : AI Speech to Text - Testing**

**Model Testing cURL command**

curl -X POST "http://localhost:5000/model/predict" -H "accept: application/json" -H "Content-Type: multipart/form-data" -F [audio=@audio\_sample.wav;type=audio/wav](mailto:audio=@audio_sample.wav;type=audio/wav)  
  

**Model Testing Python Code**

· Download the test image from the link :  
https://github.com/PrezSeah/pretrained-model-info/tree/main/model-samples/ai-speech-to-text/sample\_input

· Ensure to have python / anaconda in your system

· Run the following snippet (keep the test image in working directory or provide the image location in the code)

import requests

res = requests.post('http://localhost:5000/model/predict', 

 files = {'audio' : ('audio\_sample.wav', open('AI\_Images/audio\_sample.wav', 'rb'), 'audio/wav')})

res.content  
  

**Sample Input**

Audio file (~5 second)

**Sample Response**

{

 "status": "ok",

 "prediction": "experience proves this"

}