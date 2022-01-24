
**AI Model : AI Text Sentiment Classifier - Testing**

**Model Testing cURL command**

curl -X POST "http://localhost:5000/model/predict" -H "accept: application/json" -H "Content-Type: application/json" -d "{ \\"text\\": \[ \\"The upcoming spiderman movie is highly awaited. I like the new cast chosen in the film.\\" \]}"

**Model Testing Python Code**

· Ensure to have python / anaconda in your system

· Run the following snippet - Enter the desired customer text

import requests

res = requests.post('http://localhost:5000/model/predict',

 json = {'text':\['The upcoming spiderman movie is highly awaited. I like the new cast chosen in the film.'\]})

res.content  
  

**Sample Input**

The upcoming spiderman movie is highly awaited. I like the new cast chosen in the film.

**Sample Response**

{

 "status": "ok",

 "predictions": \[

 {

 "positive": 0.9982256293296814,

 "negative": 0.0017743540229275823

 }

 \]

}