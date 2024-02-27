# Big News!!!🎉🎉🎉
Our Paper "AirEyeSeg: Teacher-Student Insights into Robust Fisheye UAV Detection" won the **ICPRAM 2024 Best Student Paper Award**!!! 

In addition, **I am actively looking for any available PhD position in Computer Vision and Machine Learning**! If you have any available position, feel free to contact me via [zhenyue.gu22@imperial.ac.uk](mailto:zhenyue.gu22@imperial.ac.uk).

# AirEyeSeg
![Overview Diagram](https://github.com/Zane-Gu/AirEyeSeg/assets/109570480/81e358be-67fc-42d4-aa70-82b7229cfdcd)
This diagram provides an overview of our proposed Teacher-Student training scheme. The development process for fisheye detectors begins with converting standard image datasets to fisheye format. We then employ a computer vision foundation model, the Segment Anything Model (SAM), as the teacher. This guides efficient object detectors, specifically YOLOv8, as students to enhance detection and segmentation capabilities for obstacle avoidance. We trained two detectors using the Teacher-Student training method: (a) AirEyeSeg training and (b) AirEyeGT training, to validate the reliability of SAM-generated labels.

Here is a [demo](https://youtu.be/3Za_VRvaxb0) showcasing the performance comparison between AirEyeSeg and the original YOLOv8.

[![Demo Video](https://github.com/Zane-Gu/AirEyeSeg/assets/109570480/0cdcd775-f703-4325-94d5-54e245c190be)](https://youtu.be/3Za_VRvaxb0)

## Datasets
Before proceeding, please ensure you have access to the experimental datasets. Below are the links to the original datasets:
- **Visdrone**: https://github.com/VisDrone/VisDrone-Dataset
- **UAVid**: https://uavid.nl/
- **DDOS (Drone Depth and Obstacle Segmentation Dataset)**: https://huggingface.co/datasets/benediktkol/DDOS  
  This dataset was created by Benedikt Kolbeinsson. Should you have any questions, feel free to contact him via email at [benedikt.kolbeinsson15@imperial.ac.uk](mailto:benedikt.kolbeinsson15@imperial.ac.uk).
- **SEE**: A comprehensive genuine UAV dataset. Download it [here](https://drive.google.com/drive/folders/1EaHWAFhX9unhNe2xCXbdv9zwfDNlEIRL?usp=sharing).

## Getting Started

### Fisheye Images Generation

As illustrated in the diagram above, the first step involves converting standard frames into fisheye format. This can be accomplished using the provided [`fisheye_convert.py`](https://github.com/Zane-Gu/AirEyeSeg/blob/main/fisheye_convert.py) script. Before running the script, ensure to update the paths for the original (standard) images and the output (fisheye) images. Additionally, you'll need to adjust the parameters to fit your requirements. For example, in the code snippet `trans = FishEyeGenerator(150, [1280,1280])`, `150` represents the focal length, and `[1280,1280]` specifies the resolution of the output fisheye images.

> **Tip:** We will upload the comprehensive converted fisheye datasets and trained detectors in the near future. However, if you are in urgent need of them, feel free to email [me](mailto:zhenyue.gu22@imperial.ac.uk) directly.


### Teacher-Student Training


#### Distilling Knowledge from the Teacher Model

Upon acquiring the fisheye data, the subsequent phase involves leveraging the Segment Anything Model (SAM) for pseudo-labeling to curate the training dataset. This process can be approached via two methodologies:

1. **Semantic Segment Anything**: An open-source solution available at [Semantic Segment Anything on GitHub](https://github.com/fudan-zvg/Semantic-Segment-Anything), which provides a direct application of the SAM for generating annotations.
   
2. **Roboflow's Integrated SAM Tool**: For a more streamlined integration, Roboflow offers an in-built SAM tool accessible at [Roboflow](https://app.roboflow.com/), facilitating an easier annotation process.

Additionally, we are in the process of compiling a comprehensive dataset that will be made available shortly, aimed at further assisting your endeavors.



#### Training the Student Model with Distilled Knowledge

The training of the student model, utilizing the distilled knowledge, is designed to be straightforward. For detailed guidance on the training methodology, we recommend referring to the strategies outlined in our publication. These strategies will enable you to efficiently train YOLOv8 with the prepared data, culminating in the development of robust object detectors. Stay tuned for the release of our pre-trained detectors, which will be shared subsequent to the ICPRAM 2024 conference.


# Cite

> ```
> @inproceedings{Gu2024AirEyeSeg,
>   author    = {Gu, Z. and Kolbeinsson, B. and Mikolajczyk, K.},
>   title     = {AirEyeSeg: Teacher-Student Insights into Robust Fisheye UAV Detection},
>   booktitle = {Proceedings of the 13th International Conference on Pattern Recognition Applications and Methods},
>   year      = {2024},
>   pages     = {546--557},
>   isbn      = {978-989-758-684-2},
>   issn      = {2184-4313},
> }
> ```
