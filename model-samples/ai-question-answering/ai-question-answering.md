## Overview

Given a body of text (context) about a subject and questions about that subject, the model will answer questions based on the given context.

The model is based on the [BERT model](https://github.com/google-research/bert).

## Model Metadata

| Domain | Application | Industry  | Framework | Training Data | Input Data Format |
| ------------- | --------  | -------- | --------- | --------- | -------------- |
| Natural Language Processing (NLP) | Question and Answer | General | TensorFlow | [SQuAD 1.1](https://rajpurkar.github.io/SQuAD-explorer/) | Text |


## Options available for deploying this model

This model can be deployed using the following mechanisms:

* Deploy from Dockerhub:

```
docker run -it -p 5000:5000 codait/max-question-answering
```

## Example Usage

You can test or use this model

* [using cURL](#test-the-model-using-curl)

### Test the model using cURL

Once deployed, you can test the model from the command line. For example if running locally:

```shell
curl -X POST "http://localhost:5000/model/predict" -H "accept: application/json" -H "Content-Type: application/json" -d "{\"paragraphs\": [{ \"context\": \"John lives in Brussels and works for the EU\", \"questions\": [\"Where does John Live?\",\"What does John do?\",\"What is his name?\" ]},{ \"context\": \"Jane lives in Paris and works for the UN\", \"questions\": [\"Where does Jane Live?\",\"What does Jane do?\" ]}]}"
```

```json
{
  "status": "ok",
  "predictions": [
    [
      "Brussels",
      "works for the EU",
      "John"
    ],
    [
      "Paris",
      "works for the UN"
    ]
  ]
}
```

