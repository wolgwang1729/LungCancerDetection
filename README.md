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

- **V3:**  
  A further improved pipeline trained on segmented CT scans using the LungSegmentation model, focusing on lung regions; earlier versions were trained on unsegmented scans.

6.) **Notebook for Inference Pipeline**  
   This Jupyter Notebook (`InferencePipeline.ipynb`) demonstrates the end‑to‑end inference workflow:  
   - Loads a CT image  .
   - Applies lung segmentation using the LungSegmentation model.
   - Runs the Rad‑5 detector on the segmented region  
   - Outputs predictions for five radiological features: malignancy, sphericity, margin, spiculation, and texture  .


## Metrics

### Segmentation Model:

- On **Validation** Set(Vessel 12):

#### BBOX:
| AP     | AP50   | AP75   | APs    | APm    | APl    |
|--------|--------|--------|--------|--------|--------|
| 83.5287| 87.5968| 83.6156| 2.6997 | 69.9006| 97.8596|

#### SEGM:
| AP     | AP50   | AP75   | APs    | APm    | APl    |
|--------|--------|--------|--------|--------|--------|
| 76.1599| 90.8345| 81.9858| 2.7424 | 56.7885| 89.7311|

### Rad-5 Model(V3):

- On **Validation** Set(LIDC-IDRI):

#### AP50 BBOX scores:
| Malignancy | Sphericity | Margin  | Spiculation | Texture  |
|------------|------------|---------|-------------|----------|
| 24.9661    | 24.3374    | 23.1560 | 23.2624    | 16.7609  |



## Supplementary Data

Google Drive Folder containing Dataset in .jpg format, segmented Dataset and Models : https://drive.google.com/drive/folders/1GUwyQHlrcm83dpVlTxQq1QFEGQf1wpfI?usp=drive_link


