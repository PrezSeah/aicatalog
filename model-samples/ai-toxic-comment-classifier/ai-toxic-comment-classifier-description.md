
**AI Model : AI Toxic Comment Classifier - Description**

**Overview**

This model is able to detect 6 types of toxicity in a text fragment. The six detectable types are toxic, severe toxic, obscene, threat, insult, and identity hate. The underlying neural network is based on the pre-trained BERT-Base, English Uncased model and was finetuned on the Toxic Comment Classification Dataset using the Huggingface BERT Pytorch repository.

**Model Labels**

A brief definition of the six different toxicity types can be found below.

Toxic: very bad, unpleasant, or harmful

Severe toxic: extremely bad and offensive

Obscene: (of the portrayal or description of sexual matters) offensive or disgusting by accepted standards of morality and decency

Threat: a statement of an intention to inflict pain, injury, damage, or other hostile action on someone in retribution for something done or not done

Insult: speak to or treat with disrespect or scornful abuse

Identity hate: hatred, hostility, or violence towards members of a race, ethnicity, nation, religion, gender, gender identity, sexual orientation or any other designated sector of society

**Model Metadata**

Domain : NLP

Application : Text Classification

Industry : General

Framework : PyTorch

Training Data : Toxic Comment Classification Dataset

Input Data Format : Text

**Dockehub** **Link**

https://hub.docker.com/r/codait/max-toxic-comment-classifier

**Deployment**

Deployment from dockerhub:

docker run -it -p 5000:5000 codait/max-toxic-comment-classifier

**Model Testing**

curl -X POST "http://localhost:5000/model/predict" -H "accept: application/json" -H "Content-Type: application/json" -d "{ \\"text\\": \[ \\"Hitler was the most hated person in the history. He killed more than a million people.\\" \]}"

**Sample Input**

Hitler was the most hated person in the history. He killed more than a million people.

**Sample Output**

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