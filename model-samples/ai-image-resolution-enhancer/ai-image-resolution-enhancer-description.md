
**AI Model : AI Image Resolution Enhancer - Description**

**Overview**

This model is able to upscale a pixelated image by a factor of 4, while generating photo-realistic details. The backbone of this neural network is a Generative Adversarial Network (GAN) trained on 600,000 images of the OpenImages V4 dataset.

The GAN is based on SRGAN-tensorflow GitHub repository

**Model Metadata**

Domain : Vision

Application : Super-Resolution

Industry : General

Framework : Tensorflow

Training Data : OpenImages V4

Input Data Format : Image (RGB/HWC)

**Benchmark**

![](https://github.com/PrezSeah/pretrained-model-info/raw/main/model-samples/ai-image-resolution-enhancer/ai-image-resolution-enhancer-description_files/image004.png)

The performance of this implementation was evaluated on three datasets: Set5, Set14, and BSD100. The PSNR (peak signal to noise ratio) and SSIM (structural similarity index) metrics were evaluated, although the paper discusses the MOS (mean opinion score) as the most favorable metric. In essence, the SRGAN implementation trades a better PSNR or SSIM score for a result more appealing to the human eye. This leads to a collection of output images with more crisp and realistic details.

NOTE: The SRGAN in the paper was trained on 350k ImageNet samples, whereas this SRGAN was trained on 600k OpenImages V4 pictures.

**Dockehub Link**

https://hub.docker.com/r/codait/max-image-resolution-enhancer

**Deployment**

Deployment from dockerhub:

docker run -it -p 5000:5000 codait/max-image-resolution-enhancer

**Model Testing**

curl -X POST "http://localhost:5001/model/predict" -H "accept: application/json" -H "Content-Type: multipart/form-data" -F "image=@image\_enhancement.PNG;type=image/png"

**Sample Input**

![](https://github.com/PrezSeah/pretrained-model-info/raw/main/model-samples/ai-image-resolution-enhancer/ai-image-resolution-enhancer-description_files/image006.jpg)

**Sample Output**

![](https://github.com/PrezSeah/pretrained-model-info/raw/main/model-samples/ai-image-resolution-enhancer/ai-image-resolution-enhancer-description_files/image008.jpg)
