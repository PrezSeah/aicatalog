
**AI Model : AI Questioning and Answering - Description**

**Overview**

Given a body of text (context) about a subject and questions about that subject, the model will answer questions based on the given context.

The model is based on the BERT model.

**Model Metadata**

Domain : Natural Language Processing

Application : Question and Answer

Industry : General

Framework : TensorFlow

Training Data : SQuAD 1.1

Input Data Format : Text

**Dockehub** **Link**

https://hub.docker.com/r/codait/max-question-answering

**Deployment**

Deployment from dockerhub:

docker run -it -p 5000:5000 codait/max-question-answering

**Model Testing**

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
Question :  Where does Jane Live?, What does Jane do?

**Sample Output**

{

 "paragraphs": \[

 {

 "context": "On 22 December, The Spiderman movie will be released worldwide. Its under the Marvel Banner",

 "questions": \[

 "When is The Spiderman movie released?"

 \]

 },

 {

 "context": "Jane lives in Paris and works for the UN",

 "questions": \[

 "Where does Jane Live?",

 "What does Jane do?"

 \]

 }

 \]

}
