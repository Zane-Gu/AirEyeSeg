# AirEyeSeg
![diagram](https://github.com/Zane-Gu/AirEyeSeg/assets/109570480/81e358be-67fc-42d4-aa70-82b7229cfdcd)
This is an overview diagram of our proposed Teacher-Student training scheme. The initial phase of developing fisheye detectors necessitates the transformation of standard image datasets into a fisheye format, and then we adopt a computer vision foundation model (Segment Anything Model, SAM) as the teacher, guiding efficient object detectors (YOLOv8) as students to enhance detection and segmentation for obstacle avoidance. Here, we trained two detectors using Teacher-Student training method( (a) AirEyeSeg training; (b) AirEyeGT training) to validate the reliablity of SAM-generated labels.

Here is a [demo](https://youtu.be/3Za_VRvaxb0) illustrating the performance of AirEyeSeg vs. original YOLOv8.

[![Demo Video](https://github.com/Zane-Gu/AirEyeSeg/assets/109570480/0cdcd775-f703-4325-94d5-54e245c190be)](https://youtu.be/3Za_VRvaxb0)



## Datasets
Before starting, please sure you can accesss to the experimental datasets. Here are the original datasets links:
* Visdrone: https://github.com/VisDrone/VisDrone-Dataset
* UAVid: https://uavid.nl/
* DDOS (The Drone Depth and Obstacle Segmentation Dataset): https://huggingface.co/datasets/benediktkol/DDOS  
  This dataset was created by [Benedikt](benedikt.kolbeinsson15@imperial.ac.uk), if encounter any questions feel free to email him.
* SEE: This is a large genuine UAV dataset, please download via this [link](https://drive.google.com/drive/folders/1EaHWAFhX9unhNe2xCXbdv9zwfDNlEIRL?usp=sharing).


## 

