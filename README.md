# Echocardiography-Analysis
Using Artificial Intelligence for medical image analysis




## 1. Mask Volume Folder

The maskvolume.py module contains functionality that computes an estimated volume by dividing the mask into segments, where the width of each segment is used to compute a cylindrical volume. This is then added up to produce a total volume. The greater the number of segments, the better the aproximation, however this would be computationally more expensive.

### 1.1. Mask Volume Usage
An example has been provided in main.py for calling the module.

### 1.2. Prerequisites
The code is dependent on the following external modules that may need to be installed.
1. opencv
2. sympy

### 1.3. Display usage:

The purple line is the line from the max-point to the bottom mid-point of the LV.
The green line is from the min-point to the max-point (i.e. longest distance between two points of the LV mask).


With K=20 and use_bottom_midpoint = True (segments are relative to the purple line) :

![image](https://user-images.githubusercontent.com/16832291/161746218-46d932d7-cd3e-4252-9067-900cd60df148.png)


With K=20 and use_bottom_midpoint = False (segments are relative to the green line):

![image](https://user-images.githubusercontent.com/16832291/161746430-87f15265-f0f9-46c0-8046-9ee4fe85e61e.png)


### 1.4. Future Additions:

Note: the current code only approximates a volume from a mask obtained from either the Apical 2-chamber or Apical 4-chamber view and not both.
Ideally, for a single LV mask, the volume could be computed using the length of segments from both views.



