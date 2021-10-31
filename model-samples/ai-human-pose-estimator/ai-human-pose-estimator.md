## Overview

This model detects humans and their poses in a given image. The model first detects the humans in the input image and then identifies the body parts, including nose, neck, eyes, shoulders, elbows, wrists, hips, knees, and ankles. Next, each pair of associated body parts is connected by a pose line. The pose lines are assembled into full body poses for each of the humans detected in the image.

## Model Metadata

| Domain | Application | Industry  | Framework | Training Data | Input Data Format |
| ------------- | --------  | -------- | --------- | --------- | -------------- |
| Vision | Human Pose Estimation | Multi | Tensorflow | [COCO](http://cocodataset.org) | Image File |




## Options available for deploying this model

This model can be deployed using the following mechanisms:

* Deploy from Dockerhub:

  ```
  docker run -it -p 5000:5000 codait/max-human-pose-estimator
  ```


* Locally:

## Example Usage

You can test or use this model

 - [using cURL](#test-the-model-using-curl)


### Test the model using cURL

Once deployed, you can test the model from the command line. For example if running locally:

```
curl -F "image=@samples/p3.jpg" -XPOST http://localhost:5000/model/predict
```

You should see a JSON response like that below:

```
{
  "status": "ok",
  "predictions": [
    {
      "human_id": 0,
      "pose_lines": [
        {
          "line": [
            110,
            53,
            91,
            53
          ]
        },
        {
          "line": [
            110,
            53,
            129,
            50
          ]
        },
        .
        .
        .
        {
          "line": [
            114,
            35,
            119,
            32
          ]
        }
      ]
    }
  ]
}
```

