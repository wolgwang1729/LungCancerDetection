# LungCancerDetection
This repository contains scripts and models for lung cancer nodule detection from CT scans, developed using the Detectron2 framework. The primary focus is on preprocessing and detecting nodules in lung CT images, with the use of the LIDC-IDRI dataset.

 ## **NOTE:**  
 * I have done work related to lung segmentation in the repository:  
 * **https://github.com/wolgwang1729/LungSegmentation**
 

## Contents:
1.) **Script for Exploring the LIDC-IDRI Dataset (With and Without Windowing)**<br />
This script allows exploration of the LIDC-IDRI dataset, with the option to apply windowing techniques for enhancing lung-specific features in the images. Windowing is useful for improving the contrast of nodules against the background.

2.) **Script for Converting DICOM Files to JPG**<br />
This script converts raw DICOM files into 512x512 JPG images for easier visualization and model training.

3.) **Script for Making JSON Annotations from XML**<br />
A script that parses XML files containing nodule annotations and converts them into JSON format, suitable for use with Detectron2.

4.) **Script for Segmenting LIDC-IDRI Images Using LungSegmentation Model**<br />
This script utilizes the segmentation model from [LungSegmentation](https://github.com/wolgwang1729/LungSegmentation) to automatically segment lung regions in LIDC-IDRI CT images. The segmented masks can be used for preprocessing, focusing analysis on lung tissue, and improving downstream detection tasks.

5.) **Rad-5 Model Using Detectron2**<br />
Implementation of an Automated Image Processing System for Nodules (Rad-5), utilizing Detectron2 for detecting lung nodules based on bounding boxes.

- **V1:**  
  A beginner’s setup leveraging a standard Detectron2 Faster R‑CNN model with default settings and minimal hyperparameter adjustments.

- **V2:**  
  An improved pipeline with targeted hyperparameter tuning, consistent input dimensions, mixed‑precision training for speed, larger batch sizes, extended GPU training.

Google Drive Folder containing Dataset in .jpg format and Models : https://drive.google.com/drive/folders/1GUwyQHlrcm83dpVlTxQq1QFEGQf1wpfI?usp=drive_link


