# UnetResnet for sUAV Image Segmentation (Pytorch)

### Context

A Kaggle competition was held at CentraleSupélec between teams of students; the goal was to provide the best algorithm possible to reach highest accuracy (computed with the _Dice coefficient_) while segmenting images taken from small UAVs.

We had toimplement and solve a remote sensing problem using recent deep learning techniques. In particular, the main objective of this challenge is to segment images acquired by a small UAV (sUAV) at the area on Houston, Texas. These images were acquired in order to assess the damages on residential and public properties after Hurricane Harvey. In total there are 25 categories of segments (e.g. roof, trees, pools etc.).

The task was to design and implement a deep learning model in order to perform the automatic segmentation of such images. The model could be trained using the train images which contain pixel-wise annotations. Using the trained model, a prediction on the test images had to be performed and submitted on the platform. Depending on the performance of the submitted file and the leaderboard you would be ranked accordingly using macro F1 score.

Following classes are present in the dataset:
0: Background
1: Property Roof
2: Secondary Structure
3: Swimming Pool
4: Vehicle
5: Grass
6: Trees / Shrubs
7: Solar Panels
8: Chimney
9: Street Light
10: Window
11: Satellite Antenna
12: Garbage Bins
13: Trampoline
14: Road/Highway
15: Under Construction / In Progress Status
16: Power Lines & Cables
17: Water Tank / Oil Tank
18: Parking Area - Commercial
19: Sports Complex / Arena
20: Industrial Site
21: Dense Vegetation / Forest
22: Water Body
23: Flooded
24: Boat

### Model

The model architecture used was based on the following architecture:

<a href="https://www.researchgate.net/" rel="Unet Resnet">![Unet Resnet](https://www.researchgate.net/publication/345841396/figure/fig5/AS:959983546019840@1605889321027/Architecture-of-ResNet-UNet-The-structure-of-the-ResNet-UNet-uses-the-traditional-UNet_W640.jpg)</a>

### Results

Model achieved **71% accuracy** on a train dataset of ~250 images, without using any pre-trained ResNet network inside the Unet network.

The "accuracy" was computed accordingly to the **_Sørensen-Dice Coefficient_**:
$$Dice = \frac{2 \mid A \cap B \mid}{\mid A \mid + \mid B \mid}$$
