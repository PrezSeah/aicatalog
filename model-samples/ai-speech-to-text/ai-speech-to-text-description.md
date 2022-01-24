
**AI Model : AI Speech to Text - Description**

**Overview**

This repository contains code to instantiate and deploy a speech recognition model. The model takes a short (~5 second), single channel WAV file containing English language speech as an input and returns a string containing the predicted speech.The model expects 16kHz audio.

The code for this model comes from Mozilla's Project DeepSpeech and is based on Baidu's Deep Speech research paper.

**Model Metadata**

Domain : Audio

Application : Speech Recognition

Industry : General

Framework : Tensorflow

Training Data : Mozilla Common Voice

Input Data Format : Audio (16 bit, 16 kHz, mono WAV file)

**Dockehub** **Link**

https://hub.docker.com/r/codait/max-speech-to-text-converter

**Deployment**

Deployment from dockerhub:

docker run -it -p 5000:5000 codait/max-speech-to-text-converter

**Model Testing**

curl -X POST "http://localhost:5000/model/predict" -H "accept: application/json" -H "Content-Type: multipart/form-data" -F "audio=@audio\_sample.wav;type\=audio/wav"

**Sample Input**

Audio file (~5 second)

**Sample Output**

{

 "status": "ok",

 "prediction": "experience proves this"

}