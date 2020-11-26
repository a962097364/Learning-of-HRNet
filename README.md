# Learning of HRNet
## Introduction
This is a simulation experiment of HRNet. The main purpose of the repository is just for learning some basic knowledge about human pose estimiation, Linux and pytorch. 
If you want to browse the origin of HRNet
You can click this URL:<br>https://github.com/leoxiaobin/deep-high-resolution-net.pytorch<br>
Due to the limitation of environment and time. This work just finish the training and testing of MPII with Epoch==210 by using HRNet and training and testing of COCO with Epoch==50 by using HRNet w32.<br>It will be updated in the future.

Environment
---
The code running with python 3.6 on Ubuntu 16.04.6. NVIDIA GPUs are needed. The code is trained and tested by using a NVIDIA 1080Ti GPU cards.

Main Result
---
### Results on MPII val
 | Arch | Head | Shoulder | Elbow | Wrist | Hip | Knee | Ankle | Mean | Mean@0.1 |
 |---|---|---|---|---|---|---|---|---|---|
 | pose_hrnet_w32 | 97.101 | 95.941 | 90.336 | 86.449 | 89.095 | 87.084 | 83.278 | 90.330 | 37.702 |
### Results on COCO_val2017_detections_AP_H_56_person
 | Arch | AP | Ap .5 | AP .75 | AP (M) | AP (L) | AR | AR .5 | AR .75 | AR (M) | AR (L) |
 |---|---|---|---|---|---|---|---|---|---|---|
 | pose_hrnet_w32 | 0.744 | 0.905 | 0.819 | 0.708 | 0.810 | 0.798 | 0.942 | 0.865 | 0.757 | 0.858 |
 
 **Note:**
 Due to the limitation of experiment environment, it will spend about a week to train the code with Epoch is 210. I changed the number of Epoch from 210 to 50. There are some difference between this solution and the origin solution.
 
Description of important files and folds
---
**{POSE_ROOT}:** The root directory<br>**tools:** Store codes for training and testinng<br>**experiments::** Store modols of nets. The method to use these models in training and testing can be found from the URL below:<br>https://github.com/leoxiaobin/deep-high-resolution-net.pytorch<br>**visualization:** Store code for visualization<br>**mpiioutput:** Store the training progress file **w32_256x256_adam_lr1e-3_2020-11-22-08-54_train.log** and test result file **w32_256x256_adam_lr1e-3_2020-11-23-10-32_valid.log** of mpii dataset<br>**cocoputput:** Store the training progress file **w32_256x192_adam_lr1e-3_2020-11-23-14-16_train.log** and testing result file **w32_256x192_adam_lr1e-3_2020-11-25-08-50_valid.log** pf coco dataset<br>**demo:** Store the demo code and some results.

## Quick Start
All the operations and models can be downloaded from this URL:
https://github.com/leoxiaobin/deep-high-resolution-net.pytorch

## Visualization
### Visualizing predictions on COCO val
![](https://github.com/a962097364/LearningofHRNet/blob/main/%7BPOSE_ROOT%7D/figure/resultsscore_584_id_12639_000000012639.png)
![](https://github.com/a962097364/LearningofHRNet/blob/main/%7BPOSE_ROOT%7D/figure/resultsscore_614_id_138639_000000138639.png)
![](https://github.com/a962097364/LearningofHRNet/blob/main/%7BPOSE_ROOT%7D/figure/resultsscore_734_id_3156_000000003156.png)
![](https://github.com/a962097364/LearningofHRNet/blob/main/%7BPOSE_ROOT%7D/figure/resultsscore_846_id_64718_000000064718.png)

## Conclusions from Demo 
**All the demo videos' fps==12**<br>
### Output results of 1~5 persons
The inference time per frame will be 0.15 sec to 0.17 sec.<br>
The origin of video:https://www.bilibili.com/video/BV1G54y1S7ec?from=search&seid=10955257765089295267
![](https://github.com/a962097364/Learning-of-HRNet/blob/main/%7BPOSE_ROOT%7D/demo/1.png)
![](https://github.com/a962097364/Learning-of-HRNet/blob/main/%7BPOSE_ROOT%7D/demo/2.png)
### Output results about 5-10 persons
The inference time per frame will be 0.20 sec to 0.25 sec.<br>
The origin of video:https://www.bilibili.com/video/BV1Cz411i7wd?from=search&seid=9549336185157582037
![](https://github.com/a962097364/Learning-of-HRNet/blob/main/%7BPOSE_ROOT%7D/demo/3.png)
Some frames may rise to 0.45-0.50
![](https://github.com/a962097364/Learning-of-HRNet/blob/main/%7BPOSE_ROOT%7D/demo/5.png)
### Output results about 15~20 persons
The origin of video:https://www.bilibili.com/video/BV1M54y1k7cB?from=search&seid=7462601590228835064<br>
The inference time per frame will be 0.30 sec to 0.40 sec.<br>
![](https://github.com/a962097364/Learning-of-HRNet/blob/main/%7BPOSE_ROOT%7D/demo/11.png)
Some frames may rise to 0.60-0.70
![](https://github.com/a962097364/Learning-of-HRNet/blob/main/%7BPOSE_ROOT%7D/demo/12.png)
### Output results of more than 50 persons
Actually, the result of more than 50 persons is not good. The ability of detection is growing weaker.
The inference time per frame will be 0.20 sec to 0.25 sec.<br>
The origin of video1:https://www.bilibili.com/video/BV1wJ41127jV?t=138<br>
The origin of video2:https://www.bilibili.com/video/BV1As411N74f?t=38
![](https://github.com/a962097364/Learning-of-HRNet/blob/main/%7BPOSE_ROOT%7D/demo/6.png)
![](https://github.com/a962097364/Learning-of-HRNet/blob/main/%7BPOSE_ROOT%7D/demo/9.png)
### Compairation
So, we can see, it doesn't rise too much when the number of person rise from 1~5 to 5~10.Just about 0.05~ 0.1 sec<br>
When the number of people rise from 5~10 to 10~20, the time increases by 0.10~0.15 sec.<br>
The increasement of time is not to much but it exists.<br>
Also, we can see, if some person who is blocked or sheltered by others in the first frame, and appear in the next frame, the time will rise a lot.
![](https://github.com/a962097364/Learning-of-HRNet/blob/main/%7BPOSE_ROOT%7D/demo/4.png)
![](https://github.com/a962097364/Learning-of-HRNet/blob/main/%7BPOSE_ROOT%7D/demo/5.png)
![](https://github.com/a962097364/Learning-of-HRNet/blob/main/%7BPOSE_ROOT%7D/demo/11.png)
![](https://github.com/a962097364/Learning-of-HRNet/blob/main/%7BPOSE_ROOT%7D/demo/12.png)
### Summary
Therefore, it has some change of time when the number of persons is rising.<br>
Also, the effections of efficiency made by blocking should be resolved.
The ability of dection when the number of people is more than 50 should be solved, too.<hr>
The most important for human pose estimation, is to raise the ability of detection and the precision.

