# Echocardiography-Analysis
Left Ventricular Volume Estimation from Echocardiographic Segmentation Using Simpson’s Method

This repository provides tools for estimating cardiac chamber volumes from echocardiographic segmentations using a Simpson’s method of disks-based approach. In echocardiography, the volume of the left ventricle (LV) is commonly quantified by dividing the ventricular cavity into a series of thin, stacked cylindrical segments (or disks) and summing their volumes — a technique known as Simpson’s method. This approach is widely adopted because it reduces geometric assumptions about ventricular shape

In this project, segmentations of the LV mask obtained from AI segmentation models are processed to compute an approximate three-dimensional volume. The mask is split into a user-defined number of segments perpendicular to a reference axis; each segment’s radius is used to compute the volume of a corresponding cylindrical disk. These disk volumes are then summed to produce a total volume estimate — improving in accuracy as the number of segments increases. This method forms the basis for deriving clinically relevant metrics such as end-diastolic volume, end-systolic volume, and ejection fraction when applied across cardiac phases.

## 1. Mask Volume Folder

The maskvolume.py module contains functionality that computes an estimated volume by dividing the mask into segments(circular disks), where the width of each segment is used as a radius to compute a cylindrical volume. This is then added up to produce a total volume. The greater the number of segments, the better the aproximation, however this would be computationally more expensive.

### 1.1. Mask Volume Usage
An example has been provided in main.py for calling the module.
Note, get_mask_volume_quick is substantially faster than get_mask_volume.
This is because get_mask_volume uses linear algebra to compute the line-polyline intersection whereas get_mask_volume_quick uses pixel iteration.
It is preferable to use get_mask_volume_quick.

### 1.2. Prerequisites
The code is dependent on the following external modules that may need to be installed.
1. opencv
2. sympy
3. scikit-image

### 1.3. Display usage:

The purple line is the line from the max-point to the bottom mid-point of the LV.
The green line is from the min-point to the max-point (i.e. longest distance between two points of the LV mask).
Note: The volume is computed relative to the purple line only.

Example 1:

With K=20 (segments are relative to the purple line) :
Green line is used only for visualisation to see where the min-max is located.

![image](https://user-images.githubusercontent.com/16832291/161746218-46d932d7-cd3e-4252-9067-900cd60df148.png)

Example 2:

![image](https://user-images.githubusercontent.com/16832291/162192735-7412bb44-400a-4348-84ec-a1583a04d2f7.png)



### 1.4. Future Additions:

Note: the current code only approximates a volume from a mask obtained from either the Apical 2-chamber or Apical 4-chamber view and not both.
Ideally, for a single LV mask, the volume could be computed by using the length of segments/discs from both views. However, instead of the disks being circular, they would be more elliptical, thus offering a better approximation of the LV volume.



