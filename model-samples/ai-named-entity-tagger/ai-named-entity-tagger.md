## Overview

This model annotates each word or term in a piece of text with a tag representing the entity type, taken from a list of 17 entity tags from the [The Groningen Meaning Bank (GMB) dataset](http://gmb.let.rug.nl/data.php). These tags cover 8 types of named entities: persons, locations, organizations, geo-political entities, artifacts, events, natural objects, time, as well as a tag for 'no entity' (see the [GMB dataset manual page](http://gmb.let.rug.nl/manual.php) for the full entity definitions). The entity types furthermore may be tagged with either a "B-" tag or "I-" tag. A "B-" tag  indicates the first term of a new entity (or only term of a single-term entity), while subsequent terms in an entity will have an "I-" tag. For example, "New York" would be tagged as `["B-GEO", "I-GEO"]` while  "London" would be tagged as `"B-GEO"`.

The model consists of a recurrent neural network architecture with a bi-directional LSTM layer applied to character-level embedding vectors, which are combined with pre-trained [GloVe 6B](https://nlp.stanford.edu/projects/glove/) word vector embeddings; finally a second bi-directional LSTM layer is applied to this combined vector representation. The input to the model is a string and the output is a list of terms in the input text (after applying simple tokenization), together with a list of predicted entity tags for each term.

The model is based on Guillaume Genthial's [Named Entity Recognition with TensorFlow model](https://github.com/guillaumegenthial/sequence_tagging), adapted to use the Keras framework. 

## Model Metadata
| Domain | Application | Industry  | Framework | Training Data | Input Data Format |
| ------------- | --------  | -------- | --------- | --------- | -------------- |
| Natural Language Processing | Named Entity Recognition | General | Keras | [Groningen Meaning Bank (GMB) Dataset](http://gmb.let.rug.nl/data.php) | Text |

*Note* the underlying dataset is primarily based on news articles and so the model should perform relatively better on input related to general news, business, geo-political and sporting events. The dataset covers a period up until 2014, which governs the entities the model will be aware of.


## Options available for deploying this model

This model can be deployed using the following mechanisms:

* Deploy from Dockerhub:

  ```
  docker run -it -p 5000:5000 codait/max-named-entity-tagger
  ```

## Example Usage

You can test or use this model
 - [using cURL](#test-the-model-using-curl)


### Test the model using cURL

Once deployed, you can test the model from the command line. For example:

```
curl -X POST -H 'Content-Type: application/json' -d '{"text":"John lives in Brussels and works for the EU"}' 'http://localhost:5000/model/predict'
```

You should see a JSON response like that below:

```json
{
    "status": "ok",
    "prediction": {
        "entities": [
            "B-PER",
            "O",
            "O",
            "B-GEO",
            "O",
            "O",
            "O",
            "O",
            "B-ORG"
        ],
        "input_terms": [
            "John",
            "lives",
            "in",
            "Brussels",
            "and",
            "works",
            "for",
            "the",
            "EU"
        ]
    }
}
```
