## Overview

This model is able to upscale a pixelated image by a factor of 4, while generating photo-realistic details. The backbone of this neural network is a _Generative Adversarial Network_ (GAN) trained on 600,000 images of the [OpenImages V4](https://storage.googleapis.com/openimages/web/index.html) dataset.

The GAN is based on [SRGAN-tensorflow GitHub repository](https://github.com/brade31919/SRGAN-tensorflow)

## Model Metadata
| Domain | Application | Industry  | Framework | Training Data | Input Data Format |
| ------------- | --------  | -------- | --------- | --------- | -------------- |
| Vision | Super-Resolution | General | TensorFlow | [OpenImages V4](https://storage.googleapis.com/openimages/web/index.html) | Image (RGB/HWC) |

## Benchmark

| Set5 | Author's SRGAN | This SRGAN |
| -------- | ------------------ | ----------- |
| PSNR | 29.40 | 29.56 |
| SSIM | 0.85 | 0.85 |

| Set14 | Author's SRGAN | This SRGAN |
| -------- | ------------------ | ----------- |
| PSNR | 26.02 | 26.25 |
| SSIM | 0.74 | 0.72 |

| BSD100 | Author's SRGAN | This SRGAN |
| -------- | ------------------ | ----------- |
| PSNR | 25.16 | 24.4 |
| SSIM | 0.67  |  0.67 |

The performance of this implementation was evaluated on three datasets: Set5, Set14, and BSD100.
The PSNR (peak signal to noise ratio) and SSIM (structural similarity index) metrics were evaluated, although the paper discusses
the MOS (mean opinion score) as the most favorable metric. In essence, the SRGAN implementation trades a better PSNR or SSIM score for a result more appealing to the human eye. This leads to a collection of output images with more crisp and realistic details.


_NOTE: The SRGAN in the paper was trained on 350k ImageNet samples, whereas this SRGAN was trained on 600k [OpenImages V4](https://storage.googleapis.com/openimages/web/index.html) pictures._


## Options available for deploying this model

This model can be deployed using the following mechanisms:

* Deploy from Dockerhub:

  ```
  docker run -it -p 5000:5000 codait/max-image-resolution-enhancer
  ```


## Example Usage

You can test or use this model [using cURL](#test-the-model-using-curl)

### Test the model using cURL

Use the `model/predict` endpoint to load a test image (you can use one of the test images from the `assets/test_examples/low_resolution` folder) in order to get a high resolution output image returned.

Once deployed, you can test the model from the command line. For example:

```
curl -F "image=@samples/test_examples/low_resolution/food.png" -XPOST http://localhost:5000/model/predict > food_high_res.png
```

The above command will send the low resolution `food.png` file to the model, and save the high resolution output image to the `food_high_res.png` file in the root directory.

The ideal input image is a PNG file with a resolution between 100x100 and 500x500, preferably without any post-capture processing and flashy colors. The model is able to generate details from a pixelated image (low DPI), but is not able to correct a 'blurred' image.


