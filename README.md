# object_detection

The goal of this project is to perform something like below,

![][image_1]

We want to draw a box around an object in an image, and put a text to show what objects we detected.

## Methodology

The project covers the following methodologies,
* Neural network image classification
* Transfer learning
* Sliding windows
* Image pyramid

## Problem

This project is not completely done yet, because we still have the following problems,
* The model misclassifies some objects, and we fail to correctly detect objects.
* When there are multiple objects, we cannot draw multiple boxes around them.
* Detection algorithm is not efficient, so it requires high computation so the process is slow.

[image_1]: https://github.com/yukikitayama/object_detection/blob/master/images/single_box_frog_01_model2.png
