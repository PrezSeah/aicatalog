
**AI Model : AI Name Entity Tagger - Testing**

**Model Testing cURL command**

curl -X POST "http://localhost:5000/model/predict" -H "accept: application/json" -H "Content-Type: application/json" -d "{ \\"text\\": \\"John lives in Brussels and works for the EU. Soon he will be coming to India for Market Research.\\"}"

**Model Testing Python Code**

· Ensure to have python / anaconda in your system

· Run the following snippet Enter the desired customer text

import requests

res = requests.post('http://localhost:5000/model/predict',

 json = {'text':'John lives in Brussels and works for the EU. Soon he will be coming to India for Market Research'})

res.content  
  

**Sample Input**

John lives in Brussels and works for the EU. Soon he will be coming to India for Market Research.

**Sample Response**

{

 "status": "ok",

 "prediction": {

 "tags": \[

 "B-PER",

 "O",

 "O",

 "B-GEO",

 "O",

 "O",

 "O",

 "O",

 "B-ORG",

 "O",

 "O",

 "O",

 "O",

 "O",

 "O",

 "O",

 "B-GEO",

 "O",

 "B-ORG",

 "I-ORG",

 "O"

 \],

 "terms": \[

 "John",

 "lives",

 "in",

 "Brussels",

 "and",

 "works",

 "for",

 "the",

 "EU",

 ".",

 "Soon",

 "he",

 "will",

 "be",

 "coming",

 "to",

 "India",

 "for",

 "Market",

 "Research",

 "."

 \]

 }

}