# TuSimple

This dataset was released as part of the Tusimple Lane Detection Challenge. It contains 3626 video clips of 1 sec duration each. Each of these video clips contains 20 frames of which, the last frame is annotated. These videos were captured by mounting the cameras on a vehicle dashboard. You can download the dataset from [here](https://github.com/TuSimple/tusimple-benchmark/issues/3) or visit [https://github.com/TuSimple/tusimple-benchmark/issues/3](https://github.com/TuSimple/tusimple-benchmark/issues/3).

## File descriptions

Each sub-directory contains 20 sequential images of which, the last frame is annotated. label_data_(date).json contains labels in **JSON format** for the last frame. Each line in the JSON file is a dictionary with key values…

**raw_file:** string type. the file path in the clip

**lanes:** it is a list of list of lanes. Each list corresponds to a lane and each element of the inner list is x-coordinate of ground truth lane.

**h_samples:** it is a list of height values corresponding to the lanes. Each element in this list is y-coordinate of ground truth lane

In this dataset, at most four lanes are annotated - the two **ego lanes** (two lane boundaries in which the vehicle is currently located) and the lanes to the right and left of ego lanes. All the lanes are annotated at an equal interval of height, therefore h_samples contain only one list whose elements correspond to y-coordinates for all lists in lanes. For a point in h_samples, if there is no lane at the location, its corresponding x-coordinate has -2. For example, a line in the JSON file looks like :

```
{  
  "lanes": [  
        [-2, -2, -2, -2, 632, 625, 617, 609, 601, 594, 586, 578, 570, 563, 555, 547, 539, 532, 524, 516, 508, 501, 493, 485, 477, 469, 462, 454, 446, 438, 431, 423, 415, 407, 400, 392, 384, 376, 369, 361, 353, 345, 338, 330, 322, 314, 307, 299],  
        [-2, -2, -2, -2, 719, 734, 748, 762, 777, 791, 805, 820, 834, 848, 863, 877, 891, 906, 920, 934, 949, 963, 978, 992, 1006, 1021, 1035, 1049, 1064, 1078, 1092, 1107, 1121, 1135, 1150, 1164, 1178, 1193, 1207, 1221, 1236, 1250, 1265, -2, -2, -2, -2, -2],  
        [-2, -2, -2, -2, -2, 532, 503, 474, 445, 416, 387, 358, 329, 300, 271, 241, 212, 183, 154, 125, 96, 67, 38, 9, -2, -2, -2, -2, -2, -2, -2, -2, -2, -2, -2, -2, -2, -2, -2, -2, -2, -2, -2, -2, -2, -2, -2, -2],  
        [-2, -2, -2, 781, 822, 862, 903, 944, 984, 1025, 1066, 1107, 1147, 1188, 1229, 1269, -2, -2, -2, -2, -2, -2, -2, -2, -2, -2, -2, -2, -2, -2, -2, -2, -2, -2, -2, -2, -2, -2, -2, -2, -2, -2, -2, -2, -2, -2, -2, -2]  
       ],  
  "h_samples": [240, 250, 260, 270, 280, 290, 300, 310, 320, 330, 340, 350, 360, 370, 380, 390, 400, 410, 420, 430, 440, 450, 460, 470, 480, 490, 500, 510, 520, 530, 540, 550, 560, 570, 580, 590, 600, 610, 620, 630, 640, 650, 660, 670, 680, 690, 700, 710],  
  "raw_file": "path_to_clip"  
}
```

It says that there are four lanes in the image, and the first lane starts at (632,280), the second lane starts at (719,280), the third lane starts at (532,290) and the fourth lane starts at (781,270).

## Resources

 - https://paperswithcode.com/dataset/tusimple
 - https://github.com/TuSimple/tusimple-benchmark/blob/master/doc/lane_detection/readme.md
 - https://medium.com/analytics-vidhya/detecting-lanes-using-deep-neural-networks-eebf2d9e3603
 - https://www.kaggle.com/datasets/manideep1108/tusimple
