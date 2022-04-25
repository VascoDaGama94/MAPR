# Cityscapes

[Cityscapes](https://www.cityscapes-dataset.com/) is a large-scale database which focuses on semantic understanding of urban street scenes. It provides semantic, instance-wise, and dense pixel annotations for 30 classes grouped into 8 categories (flat surfaces, humans, vehicles, constructions, objects, nature, sky, and void). The dataset consists of around 5000 fine annotated images and 20000 coarse annotated ones. Data was captured in 50 cities during several months, daytimes, and good weather conditions. It was originally recorded as video so the frames were manually selected to have the following features: large number of dynamic objects, varying scene layout, and varying background.

## File descriptions

The folder structure of the Cityscapes dataset is as follows:

```
{root}/{type}{video}/{split}/{city}/{city}_{seq:0>6}_{frame:0>6}_{type}{ext}

```

The meaning of the individual elements is:

-   `root` the root folder of the Cityscapes dataset. Many of our scripts check if an environment variable `CITYSCAPES_DATASET` pointing to this folder exists and use this as the default choice.
-   `type` the type/modality of data, e.g. `gtFine` for fine ground truth, or `leftImg8bit` for left 8-bit images.
-   `split` the split, i.e. train/val/test/train_extra/demoVideo. Note that not all kinds of data exist for all splits. Thus, do not be surprised to occasionally find empty folders.
-   `city` the city in which this part of the dataset was recorded.
-   `seq` the sequence number using 6 digits.
-   `frame` the frame number using 6 digits. Note that in some cities very few, albeit very long sequences were recorded, while in some cities many short sequences were recorded, of which only the 19th frame is annotated.
-   `ext` the extension of the file and optionally a suffix, e.g. `_polygons.json` for ground truth files

Possible values of `type`

-   `gtFine` the fine annotations, 2975 training, 500 validation, and 1525 testing. This type of annotations is used for validation, testing, and optionally for training. Annotations are encoded using `json` files containing the individual polygons. Additionally, we provide `png` images, where pixel values encode labels. Please refer to `helpers/labels.py` and the scripts in `preparation` for details.
-   `gtCoarse` the coarse annotations, available for all training and validation images and for another set of 19998 training images (`train_extra`). These annotations can be used for training, either together with gtFine or alone in a weakly supervised setup.
-   `gtBbox3d` 3D bounding box annotations of vehicles. Please refer to [Cityscapes 3D (Gählert et al., CVPRW '20)](https://arxiv.org/abs/2006.07864) for details.
-   `gtBboxCityPersons` pedestrian bounding box annotations, available for all training and validation images. Please refer to `helpers/labels_cityPersons.py` as well as [CityPersons (Zhang et al., CVPR '17)](https://bitbucket.org/shanshanzhang/citypersons) for more details. The four values of a bounding box are (x, y, w, h), where (x, y) is its top-left corner and (w, h) its width and height.
-   `leftImg8bit` the left images in 8-bit LDR format. These are the standard annotated images.
-   `leftImg8bit_blurred` the left images in 8-bit LDR format with faces and license plates blurred. Please compute results on the original images but use the blurred ones for visualization. We thank [Mapillary](https://www.mapillary.com/) for blurring the images.
-   `leftImg16bit` the left images in 16-bit HDR format. These images offer 16 bits per pixel of color depth and contain more information, especially in very dark or bright parts of the scene. Warning: The images are stored as 16-bit pngs, which is non-standard and not supported by all libraries.
-   `rightImg8bit` the right stereo views in 8-bit LDR format.
-   `rightImg16bit` the right stereo views in 16-bit HDR format.
-   `timestamp` the time of recording in ns. The first frame of each sequence always has a timestamp of 0.
-   `disparity` precomputed disparity depth maps. To obtain the disparity values, compute for each pixel p with p > 0: d = ( float(p) - 1. ) / 256., while a value p = 0 is an invalid measurement. Warning: the images are stored as 16-bit pngs, which is non-standard and not supported by all libraries.
-   `camera` internal and external camera calibration. For details, please refer to [csCalibration.pdf](https://github.com/mcordts/cityscapesScripts/blob/master/docs/csCalibration.pdf)
-   `vehicle` vehicle odometry, GPS coordinates, and outside temperature. For details, please refer to [csCalibration.pdf](https://github.com/mcordts/cityscapesScripts/blob/master/docs/csCalibration.pdf)

More types might be added over time and also not all types are initially available. Please let us know if you need any other meta-data to run your approach.

Possible values of `split`

-   `train` usually used for training, contains 2975 images with fine and coarse annotations
-   `val` should be used for validation of hyper-parameters, contains 500 image with fine and coarse annotations. Can also be used for training.
-   `test` used for testing on our evaluation server. The annotations are not public, but we include annotations of ego-vehicle and rectification border for convenience.
-   `train_extra` can be optionally used for training, contains 19998 images with coarse annotations
-   `demoVideo` video sequences that could be used for qualitative evaluation, no annotations are available for these videos

**For the purpose of this project only the `gtFine` and `leftImg8bit` will be of relevance.**

## Resources

 - https://paperswithcode.com/dataset/cityscapes
 - https://arxiv.org/pdf/1604.01685.pdf
 - https://github.com/mcordts/cityscapesScripts
 - https://www.cityscapes-dataset.com/

