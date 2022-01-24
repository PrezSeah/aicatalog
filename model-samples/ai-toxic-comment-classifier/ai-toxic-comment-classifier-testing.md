
**AI Model : AI Toxic Comment Classifier - Testing**

**Model Testing cURL command**

curl -X POST "http://localhost:5000/model/predict" -H "accept: application/json" -H "Content-Type: application/json" -d "{ \\"text\\": \[ \\"Hitler was the most hated person in the history. He killed more than a million people.\\" \]}"

**Model Testing Python Code**

· Ensure to have python / anaconda in your system

· Run the following snippet - Enter the desired customer text

import requests

res = requests.post('http://localhost:5001/model/predict',

 json = {'text':\['Hitler was the most hated person in the history. He killed more than a million people.'\]})

res.content  
  

**Sample Input**

Hitler was the most hated person in the history. He killed more than a million people.

**Sample Response**

{

 "status": "ok",

 "results": \[

 {

 "original\_text": "Hitler was the most hated person in the history. He killed more than a million people.",

 "predictions": {

 "toxic": 0.8997440338134766,

 "severe\_toxic": 0.0021699105855077505,

 "obscene": 0.00200835894793272,

 "threat": 0.036008454859256744,

 "insult": 0.017589394003152847,

 "identity\_hate": 0.033290158957242966

 }

 }

 \]

}