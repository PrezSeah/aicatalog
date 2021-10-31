## Overview

This model recognizes the objects present in an image from the 80 different high-level classes of objects in the [COCO Dataset](https://cocodataset.org/#home). The model consists of a deep convolutional net base model for image feature extraction, together with additional convolutional layers specialized for the task of object detection, that was trained on the COCO data set. The input to the model is an image, and the output is a list of estimated class probabilities for the objects detected in the image. The model is based on the [SSD Mobilenet V1 object detection model for TensorFlow](https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/tf1_detection_zoo.md).

## Model Metadata

| Domain | Application | Industry  | Framework | Training Data | Input Data Format |
| ------------- | --------  | -------- | --------- | --------- | -------------- |
| Vision | Object Detection | General | TensorFlow | [COCO Dataset](https://cocodataset.org/#home) | Image (RGB/HWC) |


## Options available for deploying this model

This model can be deployed using the following mechanisms:

* Deploy from Dockerhub:

  ```
  docker run -it -p 5000:5000 codait/max-object-detector
  ```


## Example Usage

You can test or use this model

 - [using cURL](#test-the-model-using-curl)


### Test the model using cURL

Once deployed, you can test the model from the command line. For example if running locally:

```
curl -F "image=@samples/dog-human.jpg" -XPOST http://127.0.0.1:5000/model/predict
```

You should see a JSON response like that below:

```json
{
  "status": "ok",
  "predictions": [
      {
          "label_id": "1",
          "label": "person",
          "probability": 0.944034993648529,
          "detection_box": [
              0.1242099404335022,
              0.12507188320159912,
              0.8423267006874084,
              0.5974075794219971
          ]
      },
      {
          "label_id": "18",
          "label": "dog",
          "probability": 0.8645511865615845,
          "detection_box": [
              0.10447660088539124,
              0.17799153923988342,
              0.8422801494598389,
              0.732001781463623
          ]
      }
  ]
}
```

