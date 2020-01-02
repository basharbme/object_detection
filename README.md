# Object Detection with Deep Learning Model

The goal of this project is to perform something like below. We want to draw a box around an object in an image, and put a text to show what objects we detected.

![][image_1] 
![][image_2]
![][image_3]

## Update

2020-01-02 Yuki Kitayama: added data augmentation to model 2, which was performed by keras ImageDataGenerator. I added this augmentation because I supposed that maybe it would improve frog false positiveness. Long story short, it failed to improve detection. I think maybe we need to change color of the images by using imgaug library, or improve layers in neural network.

## Introduction

Object detection is a task to locate where the object is, and to label what the object is. Intuitively saying, it is to perform image classification all over the places in an image, extact important predictions, and draw graphics on the image such as boxes and tests to show that we succeeded in object detection. For detail, please check the codes in this project and also read our [report](https://github.com/yukikitayama/object_detection/blob/master/documents/GR5291_Project_v22.pdf)

## Methodology

The project covers the following methodologies,
* Neural network image classification
* Transfer learning
* Sliding windows
    * I think sliding windows is the most intuitive idea that lets you know what object detection is. After developing image classification model, we use it to predict all over the places in a bigger image, and extract what we are confident at like below.
    
    ![][image_4]
    ![][image_5]
    
* Image pyramid

## Problem

This project is not completely done yet, because we still have the following problems,
* The model misclassifies some objects, and we fail to correctly detect objects. 
    * For example, the current model is sensitive to green color in an image. We want to detect a cat, but the model just looks at the grass, and detect there is a frog.

![][image_6]

* When there are multiple objects, we cannot draw multiple boxes around them.
    * For example like below, we want to detect one car at the left, and detect two trucks at the center and right. But, currently we only detect one object which we are the most confident at.
    
![][image_7]

* Detection algorithm is not efficient, so it requires high computation so the process is slow.

## Background

Originally, this was a group project in Adavanced Data Analysis course at Columbia University MA in Statistics. We were the team with the following people. We were busy at that time in job hunting and other final projects. I'm really sorry for having pushed you so much to deliever results. I also had arguments with several people, and I made you upset. But I really wanna say thank you for your help until the project deadline. I wish you success and find a nice job. Let me pursuit this object detection task as my personal project in this github. Thank you.
* Image classification model: Xinyue Li, Yicheng Li (Ethan), Xudong Guo (Tony)
* Detection algorithm: Yuki Kitayama, Sixuan Li (SL), Huaqiu Chen (Charles)
* Test dataset: Greg Lu, Chen Wang, Hang Hu (Hanna)
* Documentation: Jingwen Wang (Emily), Jinrong Cao (Carol), Hang Hu (Hanna), Greg Lu, Chen Wang  

[image_1]: https://github.com/yukikitayama/object_detection/blob/master/images/single_box_dog_01_model2.png
[image_2]: https://github.com/yukikitayama/object_detection/blob/master/images/single_box_airplane_02_model2.png
[image_3]: https://github.com/yukikitayama/object_detection/blob/master/images/single_box_frog_01_model2.png
[image_4]: https://github.com/yukikitayama/object_detection/blob/master/images/max_prob_matrix_airplane_02_model2.png
[image_5]: https://github.com/yukikitayama/object_detection/blob/master/images/multi_box_airplane_02_model2.png
[image_6]: https://github.com/yukikitayama/object_detection/blob/master/images/single_box_cat_02_res.png
[image_7]: https://github.com/yukikitayama/object_detection/blob/master/images/single_box_automobile_truck_02_model2.png
