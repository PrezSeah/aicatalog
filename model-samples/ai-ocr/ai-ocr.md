## Overview

This repository contains code to instantiate and deploy an optical character recognition model. This model takes an
image of text as an input and returns the predicted text. This model was trained on 20 samples of 94 characters from 8
different fonts and 4 attributes (regular, bold, italic, bold + italic) for a total of 60,160 training samples. Please
see the paper [An Overview of the Tesseract OCR Engine](https://storage.googleapis.com/pub-tools-public-publication-data/pdf/33418.pdf)
for more detailed information about how this model was trained.


## Model Metadata

| Domain        | Application                   | Industry | Framework  | Training Data          | Input Data Format |
|---------------|-------------------------------|----------|------------|------------------------|-------------------|
| Image & Video | Optical Character Recognition | General  | n/a        | Tesseract Data Files   | Image (PNG/JPG)   |



## Options available for deploying this model

* Deploy from Dockerhub:

  ```
  docker run -it -p 5000:5000 codait/max-ocr
  ```


### Test the model using cURL

Once deployed, you can test the model from the command line. For example if running locally:

```bash
$ curl -F "image=image-ocr.jpg" -XPOST http://localhost:5000/model/predict
```

```json
{
  "status": "ok",
  "text": [
    [
      "Text 1"
    ],
    [
      "This is testing of OCR capability",
      "Please try out"
    ]
  ]
}
```
