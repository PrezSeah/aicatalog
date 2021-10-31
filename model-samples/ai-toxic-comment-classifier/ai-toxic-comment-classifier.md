## Overview

This model is able to detect 6 types of toxicity in a text fragment. The six detectable types are toxic, severe toxic, obscene, threat, insult, and identity hate. The underlying neural network is based on the [pre-trained BERT-Base, English Uncased model](https://github.com/google-research/bert/blob/master/README.md) and was finetuned on the [Toxic Comment Classification Dataset](https://www.kaggle.com/c/jigsaw-toxic-comment-classification-challenge/data) using the [Huggingface BERT Pytorch repository](https://github.com/huggingface/pytorch-pretrained-BERT).

A brief definition of the six different toxicity types can be found below.

```
Toxic: very bad, unpleasant, or harmful

Severe toxic: extremely bad and offensive

Obscene: (of the portrayal or description of sexual matters) offensive or disgusting by accepted standards of morality and decency

Threat: a statement of an intention to inflict pain, injury, damage, or other hostile action on someone in retribution for something done or not done

Insult: speak to or treat with disrespect or scornful abuse

Identity hate: hatred, hostility, or violence towards members of a race, ethnicity, nation, religion, gender, gender identity, sexual orientation or any other designated sector of society
```

## Model Metadata
| Domain | Application | Industry  | Framework | Training Data | Input Data |
| --------- | --------  | -------- | --------- | --------- | --------------- |
| Natural Language Processing (NLP) | Text Classification | General | PyTorch | [Toxic Comment Classification Dataset](https://www.kaggle.com/c/jigsaw-toxic-comment-classification-challenge/data) | Text |


## Benchmark

This model achieves a column-wise ROC AUC score of 0.98355 (private score) in the [Kaggle Toxic Comment Classification Competition](https://www.kaggle.com/c/jigsaw-toxic-comment-classification-challenge). This implementation is trained with a maximum sequence length of 256 instead of 512 to have higher inference speed. For most applications outside of this Kaggle competition, a sequence length of 256 is more than sufficient.


## Options available for deploying this model

This model can be deployed using the following mechanisms:

* Deploy from Dockerhub:
  ```
  docker run -it -p 5000:5000 codait/max-toxic-comment-classifier
  ```


## Example Usage

You can test or use this model
 - [using cURL](#test-the-model-using-curl)

### Test the model using cURL

Once deployed, you can test the model from the command line. For example:

```
curl -d "{ \"text\": [ \"I would like to punch you.\", \"In hindsight, I do apologize for my previous statement.\" ]}" -X POST "http://localhost:5000/model/predict" -H "Content-Type: application/json"
```

You should see a JSON response like that below:

```json
{
  "status": "ok",
  "predictions": [
    {
      "toxic": 0.9796434044837952,
      "severe_toxic": 0.07256636023521423,
      "obscene": 0.058431386947631836,
      "threat": 0.8635178804397583,
      "insult": 0.11121545732021332,
      "identity_hate": 0.013826466165482998
    },
    {
      "toxic": 0.00029103411361575127,
      "severe_toxic": 0.00012417171092238277,
      "obscene": 0.0001522742968518287,
      "threat": 0.00008440738747594878,
      "insult": 0.00016013195272535086,
      "identity_hate": 0.00012860879360232502
    }
  ]
}
```
