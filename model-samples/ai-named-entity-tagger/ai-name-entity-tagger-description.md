
**AI Model : AI Name Entity Tagger - Description**

**Overview**

This model annotates each word or term in a piece of text with a tag representing the entity type, taken from a list of 17 entity tags from the The Groningen Meaning Bank (GMB) dataset. These tags cover 8 types of named entities: persons, locations, organizations, geo-political entities, artifacts, events, natural objects, time, as well as a tag for 'no entity' (see the GMB dataset manual page for the full entity definitions). The entity types furthermore may be tagged with either a "B-" tag or "I-" tag. A "B-" tag indicates the first term of a new entity (or only term of a single-term entity), while subsequent terms in an entity will have an "I-" tag. For example, "New York" would be tagged as \["B-GEO", "I-GEO"\] while "London" would be tagged as "B-GEO".

The model consists of a recurrent neural network architecture with a bi-directional LSTM layer applied to character-level embedding vectors, which are combined with pre-trained GloVe 6B word vector embeddings; finally a second bi-directional LSTM layer is applied to this combined vector representation. The input to the model is a string and the output is a list of terms in the input text (after applying simple tokenization), together with a list of predicted entity tags for each term.

The model is based on Guillaume Genthial's Named Entity Recognition with TensorFlow model, adapted to use the Keras framework.

**Model Metadata**

Domain : NLP

Application : Named Entity Recognition

Industry : General

Framework : Keras

Training Data : Groningen Meaning Bank (GMB) Dataset

Input Data Format : Text

**Dockehub** **Link**

https://hub.docker.com/r/codait/max-named-entity-tagger

**Deployment**

Deployment from dockerhub:

docker run -it -p 5000:5000 codait/max-named-entity-tagger

**Model Testing**

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

**Sample Output**

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
