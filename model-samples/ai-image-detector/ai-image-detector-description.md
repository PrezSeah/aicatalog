           <!-- /\* Font Definitions \*/ @font-face {font-family:"Cambria Math"; panose-1:2 4 5 3 5 4 6 3 2 4; mso-font-charset:0; mso-generic-font-family:roman; mso-font-pitch:variable; mso-font-signature:-536869121 1107305727 33554432 0 415 0;} @font-face {font-family:Calibri; panose-1:2 15 5 2 2 2 4 3 2 4; mso-font-charset:0; mso-generic-font-family:swiss; mso-font-pitch:variable; mso-font-signature:-469750017 -1073732485 9 0 511 0;} @font-face {font-family:"Arial Unicode MS"; panose-1:2 11 6 4 2 2 2 2 2 4; mso-font-alt:Arial; mso-font-charset:0; mso-generic-font-family:roman; mso-font-pitch:variable; mso-font-signature:3 0 0 0 1 0;} /\* Style Definitions \*/ p.MsoNormal, li.MsoNormal, div.MsoNormal {mso-style-unhide:no; mso-style-qformat:yes; mso-style-parent:""; margin-top:0in; margin-right:0in; margin-bottom:8.0pt; margin-left:0in; line-height:105%; mso-pagination:widow-orphan; font-size:11.0pt; font-family:"Calibri",sans-serif; mso-ascii-font-family:Calibri; mso-ascii-theme-font:minor-latin; mso-fareast-font-family:Calibri; mso-fareast-theme-font:minor-latin; mso-hansi-font-family:Calibri; mso-hansi-theme-font:minor-latin; mso-bidi-font-family:"Times New Roman"; mso-bidi-theme-font:minor-bidi;} a:link, span.MsoHyperlink {mso-style-noshow:yes; mso-style-priority:99; color:#0563C1; text-decoration:underline; text-underline:single;} a:visited, span.MsoHyperlinkFollowed {mso-style-noshow:yes; mso-style-priority:99; color:#954F72; mso-themecolor:followedhyperlink; text-decoration:underline; text-underline:single;} p.msonormal0, li.msonormal0, div.msonormal0 {mso-style-name:msonormal; mso-style-unhide:no; mso-margin-top-alt:auto; margin-right:0in; mso-margin-bottom-alt:auto; margin-left:0in; mso-pagination:widow-orphan; font-size:12.0pt; font-family:"Times New Roman",serif; mso-fareast-font-family:"Times New Roman"; mso-fareast-theme-font:minor-fareast;} span.SpellE {mso-style-name:""; mso-spl-e:yes;} .MsoChpDefault {mso-style-type:export-only; mso-default-props:yes; font-size:10.0pt; mso-ansi-font-size:10.0pt; mso-bidi-font-size:10.0pt; font-family:"Calibri",sans-serif; mso-ascii-font-family:Calibri; mso-ascii-theme-font:minor-latin; mso-fareast-font-family:Calibri; mso-fareast-theme-font:minor-latin; mso-hansi-font-family:Calibri; mso-hansi-theme-font:minor-latin; mso-bidi-font-family:"Times New Roman"; mso-bidi-theme-font:minor-bidi;} /\* Page Definitions \*/ @page {mso-footnote-separator:url("ai-image-detector-description\_files/header.html") fs; mso-footnote-continuation-separator:url("ai-image-detector-description\_files/header.html") fcs; mso-endnote-separator:url("ai-image-detector-description\_files/header.html") es; mso-endnote-continuation-separator:url("ai-image-detector-description\_files/header.html") ecs;} @page WordSection1 {size:8.5in 11.0in; margin:1.0in 1.0in 1.0in 1.0in; mso-header-margin:.5in; mso-footer-margin:.5in; mso-paper-source:0;} div.WordSection1 {page:WordSection1;} -->  

**AI Model : AI Image Detector - Description**

**Overview**

This repository contains code to instantiate and deploy an image classification model. This model recognizes the 1000 different classes of objects in the ImageNet 2012 Large Scale Visual Recognition. The model consists of a deep convolutional net using the Inception-ResNet-v2 architecture that was trained on the ImageNet-2012 data set. The input to the model is a 299x299 image, and the output is a list of estimated class probabilities.

**Model Metadata**

Domain : Vision

Application : Image Classification

Industry : General

Framework : Keras

Training Data : Image Net

Input Data Format : Image (RGB/HWC)

**Dockehub** **Link**

https://hub.docker.com/r/codait/max-inception-resnet-v2

**Deployment**

Deployment from dockerhub:

docker run -it -p 5000:5000 codait/max-image-detector

**Model Testing**

curl -X POST "http://localhost:5000/model/predict" -H "accept: application/json" -H "Content-Type: multipart/form-data" -F "lion.png;type\=image/png"

**Sample Input**

![](ai-image-detector-description_files/image006.jpg)

**Sample Response**

{

 "status": "ok",

 "predictions": \[

 {

 "label\_id": "142",

 "label": "field\_road",

 "probability": 0.36829647421836853

 },

 {

 "label\_id": "359",

 "label": "wheat\_field",

 "probability": 0.29098382592201233

 },

 {

 "label\_id": "258",

 "label": "pasture",

 "probability": 0.0991949662566185

 },

 {

 "label\_id": "86",

 "label": "cemetery",

 "probability": 0.03284231573343277

 },

 {

 "label\_id": "341",

 "label": "tundra",

 "probability": 0.03229227662086487

 }

 \]

}