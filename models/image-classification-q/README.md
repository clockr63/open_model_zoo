# Image Classification Model

This model provides image classification.

## Model Description

Model is based on quantized MobileNet-V1 as a backbone architecture. This model is trained with Tensorflow and then converted to Tensorflow-lite model.
This model is tested with Tensorflow Lite version 1.13 and ARMNN v19.11.1.

### Models

#### Input Layers

- Name: `input`
- Shape: [1x224x224x3]
- Format: [NxCxHxW] where a
  - N: batch size
  - H: height of image(tensor)
  - W: width of image(tensor)
  - C: number of channels
- Order of channels: R-G-B
- Input image(tensor) should be normailized to 0.0 ~ 255.0


#### Output Layers

- Name: `MobilenetV1/Predictions/Reshape_1`
- Shape: [1x1001]
  - Denote confidences and the  *n*th value indicates the *n*th label's confidence. For example, *10*th value is the confidence of that an given image belongs to `Book` which is listed in [a label file](ic_q_label.txt).

| Model | Quantized MobileNet-V1 |
| --- | --- |
| input tensor size | 224 x 224 |
| mean | 0 |
| std  | 1 |
| order | NCHW |
| input layer | input |
| output layer | MobilenetV1/Predictions/Reshape_1 |


### Image

Input image can be downloaed from [LINK](https://storage.googleapis.com/openimages/web/visualizer/index.html?set=train&type=detection&c=%2Fm%2F09qck&id=4bfe93da7a763143), which is originally from [India - Colours of India - Bananas 1 by McKay Savage](https://farm4.staticflickr.com/3219/2357421566_8378ebc4ba_o.jpg) with CC-BY-2.0.
![Example](openimage_banana_result.jpg)
