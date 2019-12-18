# Object Detection with Deep Learning Model

The goal of this project is to perform something like below,

![][image_1] 
![][image_2]
![][image_3]

We want to draw a box around an object in an image, and put a text to show what objects we detected.

## Introduction

Object detection is a task to locate where the object is, and to label what the object is. Intuitively saying, it is to perform image classification all over the places in an image, extact important predictions, and draw graphics on the image such as boxes and tests to show that we succeeded in object detection.

## Methodology

The project covers the following methodologies,
* Neural network image classification
* Transfer learning
* Sliding windows
* Image pyramid

## Problem

This project is not completely done yet, because we still have the following problems,
* The model misclassifies some objects, and we fail to correctly detect objects. 
    * For example, the current model is sensitive to green color in an image. We want to detect a cat, but the model just looks at the grass, and detect there is a frog.

![][image_4]

* When there are multiple objects, we cannot draw multiple boxes around them.
    * For example like below, we want to detect one car at the left, and detect two trucks at the center and right. But, currently we only detect one object which we are the most confident at.
    
![][image_5]

* Detection algorithm is not efficient, so it requires high computation so the process is slow.

[image_1]: https://github.com/yukikitayama/object_detection/blob/master/images/single_box_dog_01_model2.png
[image_2]: https://github.com/yukikitayama/object_detection/blob/master/images/single_box_airplane_02_model2.png
[image_3]: https://github.com/yukikitayama/object_detection/blob/master/images/single_box_frog_01_model2.png
[image_4]: https://github.com/yukikitayama/object_detection/blob/master/images/single_box_cat_02_res.png
[image_5]: https://github.com/yukikitayama/object_detection/blob/master/images/single_box_automobile_truck_02_model2.png
