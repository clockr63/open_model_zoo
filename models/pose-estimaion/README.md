# Pose Estimation Model

This model provides pose estimation.

## Model Description

Model is based on CPM[Convolutional Pose Machines] as a backbone architecture. This model is trained with Tensorflow and then converted to Tensorflow model.
This model is tested with Tensorflow Lite version 1.13 and ARMNN v19.11.1

### Models

#### Input Layers

- Name: `image`
- Shape: [1x192x192x3]
- Format: [NxCxHxW] where a
  - N: batch size
  - H: height of image(tensor)
  - W: width of image(tensor)
  - C: number of channels
- Order of channels: R-G-B
- Input image(tensor) should be normailized to 0.0 ~ 255.0


#### Output Layers

- Name: `Convolutional_Pose_Machine/stage_5_out`
- Shape: [1x96x96x14]
  - Denote locations. Shape is [1xHxWxK] where H is height of heatmap, and W is width of heatmap,
    and K is the key points which indicate the locations of human's body parts.
	[Ha][Wb][Kc] contains the confidence value of cth body part between 0 ~ 1.

| Model | CPM based Pose Estimation |
| --- | --- |
| input tensor size | 192 x 192 |
| mean | 0.0 |
| std  | 1.0 |
| order | NCHW |
| input layer | image |
| output layer | Convolutional_Pose_Machine/stage_5_out |


### Image

TODO.
