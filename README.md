# Echocardiography-Analysis
Using Artificial Intelligence for medical image analysis




### 1.1. Mask Volume Usage
An example has been provided in main.py for calling the module.

### 1.2. Prerequisites
The code is dependent on the following external modules that may need to be installed.
1. opencv
2. sympy

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


