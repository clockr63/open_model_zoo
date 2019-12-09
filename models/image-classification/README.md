# Image Classification Model

This model provides image classification.

## Model Description

Model is based on MobileNet-V1 as a backbone architecture. This model is trained with Keras(2.2.4) and then converted to Tensorflow(1.13) model. Then, finally, it is converted to tensorflow-lite.
This model is tested with Tensorflow Lite version 1.13.

### Models

#### Input Layers

- Name: `input_2`
- Shape: [1x3x224x224]
- Format: [NxCxHxW] where a
  - N: batch size
  - C: number of channels
  - H: height of image(tensor)
  - W: width of image(tensor)
- Order of channels: R-G-B
- Input image(tensor) should be normailized to -1.0 ~ 1.0


#### Output Layers

- Name: `dense_3/Softmax`
- Shape: [1x74]
  - Denote confidences and the  *n*th value indicates the *n*th label's confidence. For example, *10*th value is the confidence of that an given image belongs to `Book` which is listed in [a label file](image-classification-label.txt).

| Model | MobileNet-V1 |
| --- | --- |
| input tensor size | 224 x 224 |
| mean | 127.5 |
| std  | 127.5 |
| order | NCHW |
| input layer | input_2 |
| output layer | dense_3/Softmax |


### Image

Input image can be downloaed from [LINK](https://storage.googleapis.com/openimages/web/visualizer/index.html?set=train&type=detection&c=%2Fm%2F09qck&id=4bfe93da7a763143), which is originally from [India - Colours of India - Bananas 1 by McKay Savage](https://farm4.staticflickr.com/3219/2357421566_8378ebc4ba_o.jpg) with CC-BY-2.0.
![Example](openimage_banana_result.jpg)
