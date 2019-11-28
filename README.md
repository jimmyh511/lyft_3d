# Lyft 3D Object Detection for Autonomous Vehicles

## Introduction
The success in 2D image segmentation and object detection using deep learning models motivates researchers to expand it to 3D case. Quickly analyzing surrounding objects’ location, size and type is essential for a self-driving system. In this project, we try to use various CNN to embed and model the camera, sensor and lidar images, and evaluate the model performance based on 3D IOU metric. This project is a part of Kaggle competition to build a level 5 self-driving system, and the baseline model is U-Net. The goal is to outperform the baseline and the result would be displayed in the Kaggle leaderboard. So far, we have understood the input categories and linkage between lidar, camera and map images, labeled instances and their geographical notations on cars’ views, also the methodology to rotate images and unify the cars’ view and birds’ view, successfully transformed unstructured birds-view lidar data to training inputs, and rendered correspondent cars-view instances location on map to outputs, then apply the baseline model U-Net to this dataset and record its performance. Currently, we experimented on combining U-Net with the ResNet as encoder, to predict length, width, location and class of objects around the car, then estimate their heights using the simple average of the predicted classes’ height.

## Directory contents
1. train_class_model.ipynb
   Estimate objects' location and class. Generate input and target data, then train Resnet34Unet and choose model by validation cross-entropy loss.

2. train_height_model.ipynb  
   Estimate objects' heights. Generate input and target data, then train Resnet34Unet and choose model by validation MSE loss.

2. prepare_test_input.ipynb
   Generate test input data.
   
2. test_combine_class_and_height.ipynb  
   Generate test data prediction, seperately on objects' class and height, then combine them together, finally generate output file.
