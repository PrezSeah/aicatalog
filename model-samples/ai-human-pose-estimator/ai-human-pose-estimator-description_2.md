

|<p></p><p>**AI Model : AI Human Pose Estimator- Description**</p><p></p>|
| :-: |
|**Overview**|<p>This model generates captions from a fixed vocabulary that describe the contents of images in the COCO Dataset. The model consists of an encoder model - a deep convolutional net using the Inception-v3 architecture trained on ImageNet-2012 data - and a decoder model - an LSTM network that is trained conditioned on the encoding from the image encoder model. The input to the model is an image, and the output is a sentence describing the image content.<br><br>The model is based on the Show and Tell Image Caption Generator Model.</p><p></p>|
|**Model Metadata**|<p>Domain : Vision</p><p>Application : Human Pose Estimation</p><p>Industry : Multi</p><p>Framework : Tensorflow</p><p>Training Data : COCO</p><p>Input Data Format : Image File</p>|
|**Dockehub Link**|https://hub.docker.com/r/codait/max-human-pose-estimator|
|**Deployment**|<p>Deployment from dockerhub:</p><p>docker run -it -p 5000:5000 codait/max-human-pose-estimator</p>|
|**Model Testing** |curl -X POST "http://localhost:5000/model/predict" -H "accept: application/json" -H "Content-Type: multipart/form-data" -F "file=@dance\_image.PNG;type=image/png"|
|**Sample Input**|<p>![](Aspose.Words.f36a12a5-cc31-463c-a8fc-3b4b9e673752.001.png)</p><p></p>|
|**Sample Response**|<p>{</p><p>Â  "status": "ok",</p><p>Â  "predictions": [</p><p>Â Â Â  {</p><p>Â Â Â Â Â  "human\_id": 0,</p><p>Â Â Â Â Â  "pose\_lines": [</p><p>Â Â Â Â Â Â Â  {</p><p>Â Â Â Â Â Â Â Â Â  "line": [</p><p>Â Â Â Â Â Â Â Â Â Â Â  123,</p><p>Â Â Â Â Â Â Â Â Â Â Â  52,</p><p>Â Â Â Â Â Â Â  },</p><p>"body\_parts": [</p><p>Â Â Â Â Â Â Â  {</p><p>Â Â Â Â Â Â Â Â Â  "part\_id": 0,</p><p>Â Â Â Â Â Â Â Â Â  "part\_name": "Nose",</p><p>Â Â Â Â Â Â Â Â Â  "score": "0.85537",</p><p>Â Â Â Â Â Â Â Â Â  "x": 130,</p><p>Â Â Â Â Â Â Â Â Â  "y": 42</p><p>Â Â Â Â Â Â Â  },</p><p>Â Â Â Â Â Â Â  {</p><p>Â Â Â Â Â Â Â Â Â  "part\_id": 1,</p><p>Â Â Â Â Â Â Â Â Â  "part\_name": "Neck",</p><p>Â Â Â Â Â Â Â Â Â  "score": "0.68294",</p><p>Â Â Â Â Â Â Â  },</p><p>Â Â Â Â Â Â Â  {</p><p>Â Â Â Â Â Â Â Â Â  "part\_id": 2,</p><p>Â Â Â Â Â Â Â Â Â  "part\_name": "RShoulder",</p><p>Â Â Â Â Â Â Â Â Â  "score": "0.58194",</p><p>Â Â Â Â Â Â Â  }</p>|

