## Overview

This model generates captions from a fixed vocabulary that describe the contents of images in the [COCO Dataset](http://cocodataset.org/#home). The model consists of an _encoder_ model - a deep convolutional net using the Inception-v3 architecture trained on [ImageNet-2012 data](http://www.image-net.org/challenges/LSVRC/2012/) - and a _decoder_ model - an LSTM network that is trained conditioned on the encoding from the image _encoder_ model. The input to the model is an image, and the output is a sentence describing the image content.

The model is based on the [Show and Tell Image Caption Generator Model](https://github.com/tensorflow/models/tree/archive/research/im2txt).

## Model Metadata

| Domain | Application | Industry  | Framework | Training Data | Input Data Format |
| ------------- | --------  | -------- | --------- | --------- | -------------- |
| Vision | Image Caption Generator | General | TensorFlow | [COCO](http://cocodataset.org/#home) | Images |


## Options available for deploying this model

This model can be deployed using the following mechanisms:

* Deploy from Dockerhub:

  ```
  docker run -it -p 5000:5000 codait/max-image-caption-generator
  ```

## Example Usage

You can test or use this model

 - [using cURL](#test-the-model-using-curl)

### Test the model using cURL

Once deployed, you can test the model from the command line. For example if running locally:

```
curl -F "image=@assets/surfing.jpg" -X POST http://127.0.0.1:5000/model/predict
```

```json
{
  "status": "ok",
  "predictions": [
    {
      "index": "0",
      "caption": "a man riding a wave on top of a surfboard .",
      "probability": 0.038827644239537
    },
    {
      "index": "1",
      "caption": "a person riding a surf board on a wave",
      "probability": 0.017933410519265
    },
    {
      "index": "2",
      "caption": "a man riding a wave on a surfboard in the ocean .",
      "probability": 0.0056628732021868
    }
  ]
}
```
