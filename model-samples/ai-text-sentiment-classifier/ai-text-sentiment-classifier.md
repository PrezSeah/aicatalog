## Overview

This model is able to detect whether a text fragment leans towards a positive or a negative sentiment. The underlying neural network is based on the [pre-trained BERT-Base, English Uncased](https://github.com/google-research/bert/blob/master/README.md) model.

Optimal input examples for this model are short strings (preferably a single sentence) with correct grammar, although not a requirement.

## Benchmark
In the table below, the prediction accuracy of the model on the test sets of three different datasets is listed.

The first row showcases the generalization power of our model after finetuning on the IBM Claims Dataset.
 The Sentiment140 (Tweets) and IMDB Reviews datasets are only used for evaluating the transfer-learning capabilities of this model. The implementation in this repository was **not** trained or finetuned on the Sentiment140 or IMDB reviews datasets.

The second row describes the performance of the BERT-Base (English - Uncased) model when finetuned on the specific task. This was done simply for reference, and the weights are therefore not made available.


The generalization results (first row) are very good when the input data is similar to the data used for finetuning (e.g. Sentiment140 (tweets) when finetuned on the IBM Claims Dataset). However, when a different style of text is given as input, and with a longer median length (e.g. multi-sentence IMDB reviews), the results are not as good.

| Model Type | IBM Claims | Sentiment140 | IMDB Reviews |
| ------------- | --------  | -------- | -------------- |
| This Model <br> (finetuned) | 94% | 83.84% | 81% |
| Models finetuned on the specific dataset | 94% | 84% | 90% |


## Options available for deploying this model

This model can be deployed using the following mechanisms:

* Deploy from Dockerhub:

  ```
  docker run -it -p 5000:5000 codait/max-text-sentiment-classifier
  ```


## Example Usage

You can test or use this model
 - [using cURL](#test-the-model-using-curl)

### Test the model using cURL

Once deployed, you can test the model from the command line. For example:

```
curl -d "{ \"text\": [ \"The Model Catalogue is a crucial element of a developer's toolkit.\" ]}" -X POST "http://localhost:5000/model/predict" -H "Content-Type: application/json"
```

You should see a JSON response like that below:

```json
{
  "status": "ok",
  "predictions": [
    [
      {
        "positive": 0.9977352619171143,
        "negative": 0.0022646968718618155
      }
    ]
  ]
}
```
