# LearningofHRNet
## Introduction
This is a simulation experiment of HRNet. The main purpose of the repository is just for me to learn some basic knowledge about human pose estimiation, Linux and pytorch. 
If you want to browse the origin of HRNet
You can click this URL:

https://github.com/leoxiaobin/deep-high-resolution-net.pytorch

Environment
---
The code running with python 3.6 on Ubuntu 16.04.6. NVIDIA GPUs are needed. The code is trained and tested using a NVIDIA 1080Ti GPU cards.

Main Result
---
### Results on MPII val
 | Arch | Head | Shoulder | Elbow | Wrist | Hip | Knee | Ankle | Mean | Mean@0.1 |
 |---|---|---|---|---|---|---|---|---|---|
 | pose_hrnet | 97.101 | 95.941 | 90.336 | 86.449 | 89.095 | 87.084 | 83.278 | 90.330 | 37.702 |
### Results on COCO_val2017_detections_AP_H_56_person
 | Arch | AP | Ap .5 | AP .75 | AP (M) | AP (L) | AR | AR .5 | AR .75 | AR (M) | AR (L) |
 |---|---|---|---|---|---|---|---|---|---|---|
 | pose_hrnet | 0.744 | 0.905 | 0.819 | 0.708 | 0.810 | 0.798 | 0.942 | 0.865 | 0.757 | 0.858 |
 
 **Note:**
 Due to the limitation of experiment environment, it will spend about a week to train the code with Epoch is 210. I changed the number of Epoch from 210 to 50. There is some difference between this solution and the origin solution.
 
Description of important files and folds
---
**{POSE_ROOT}:** The root directory<br>**tools:** Store codes for training and testinng<br>**experiments::** Store modols of nets. The method to use these models in training and testing can be found from the URL below:<br>https://github.com/leoxiaobin/deep-high-resolution-net.pytorch<br>**visualization:** Store code for visualization<br>**mpiioutput:** Store the training progress file **w32_256x256_adam_lr1e-3_2020-11-22-08-54_train.log** and test result file **w32_256x256_adam_lr1e-3_2020-11-23-10-32_valid.log**

## Quick Start
All the operations and models can be downloaded from this URL:
https://github.com/leoxiaobin/deep-high-resolution-net.pytorch

## Visualization

![](https://github.com/a962097364/LearningofHRNet/blob/main/%7BPOSE_ROOT%7D/figure/resultsscore_584_id_12639_000000012639.png)
![](https://github.com/a962097364/LearningofHRNet/blob/main/%7BPOSE_ROOT%7D/figure/resultsscore_614_id_138639_000000138639.png)
![](https://github.com/a962097364/LearningofHRNet/blob/main/%7BPOSE_ROOT%7D/figure/resultsscore_734_id_3156_000000003156.png)
![](https://github.com/a962097364/LearningofHRNet/blob/main/%7BPOSE_ROOT%7D/figure/resultsscore_846_id_64718_000000064718.png)
