
**AI Model : AI Questioning and Answering - Testing**

**Model Testing cURL command**

curl -X POST "http://localhost:5000/model/predict" -H "accept: application/json" -H "Content-Type: application/json" -d "{ \\"paragraphs\\": \[ { \\"context\\": \\"On 22 December, The Spiderman movie will be released worldwide. Its under the Marvel Banner\\", \\"questions\\": \[ \\"When is The Spiderman movie released?\\" \] }, { \\"context\\": \\"Jane lives in Paris and works for the UN\\", \\"questions\\": \[ \\"Where does Jane Live?\\", \\"What does Jane do?\\" \] } \]}"

**Model Testing Python Code**

· Ensure to have python / anaconda in your system

· Run the following snippet - Enter the desired customer text

import requests

res = requests.post('http://localhost:5000/model/predict',

 json = { "paragraphs": \[ { "context": "On 22 December, The Spiderman movie will be released worldwide. Its under the Marvel Banner", "questions": \[ "When is The Spiderman movie released?" \] }, { "context": "Jane lives in Paris and works for the UN", "questions": \[ "Where does Jane Live?", "What does Jane do?" \] } \]})

res.content  
  

**Sample Input**

Context : On 22 December, The Spiderman movie will be released worldwide. Its under the Marvel Banner

Question : When is The Spiderman movie released?

Context : Jane lives in Paris and works for the UN

Question : Where does Jane Live?, What does Jane do?

**Sample Response**

{

 "status": "ok",

 "predictions": \[

 \[

 "22 December"

 \],

 \[

 "Paris",

 "works for the UN"

 \]

 \]

}