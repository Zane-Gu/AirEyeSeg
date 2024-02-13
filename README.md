# AirEyeSeg
![diagram](https://github.com/Zane-Gu/AirEyeSeg/assets/109570480/81e358be-67fc-42d4-aa70-82b7229cfdcd)
This is an overview diagram of our proposed Teacher-Student training scheme. The initial phase of developing fisheye detectors necessitates the transformation of standard image datasets into a fisheye format, and then we adopt a computer vision foundation model (Segment Anything Model, SAM) as the teacher, guiding efficient object detectors (YOLOv8) as students to enhance detection and segmentation for obstacle avoidance. Here, we trained two detectors using Teacher-Student training method( (a) AirEyeSeg training; (b) AirEyeGT training) to validate the reliablity of SAM-generated labels.

## Datasets
Before starting, please sure you can accesss to the experimental datasets. Here are the original datasets links:
* Visdrone: https://github.com/VisDrone/VisDrone-Dataset
* UAVid: https://uavid.nl/
* DDOS (The Drone Depth and Obstacle Segmentation Dataset): https://huggingface.co/datasets/benediktkol/DDOS  
  This dataset was created by Benedikt, if encounter any questions feel free to email [him](benedikt.kolbeinsson15@imperial.ac.uk)
* SEE: This dataset will be attached in this repository, please see
