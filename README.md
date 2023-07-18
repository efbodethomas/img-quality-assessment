# Image Quality Assessment

This repository contains code for training and evaluating models for image quality assessment. The code utilizes pre-trained models (DenseNet121) to assess the quality of images based on various features. The models are trained and evaluated on image data in different color spaces (RGB, HSV, LAB) using AdaBoost as the classification algorithm.

## Overview

The goal of this project is to assess the quality of images based on their color space and various features. The code performs the following tasks:

1. **Dataset Creation:** The `ColorSpaceDataset` class is defined to load images from a specified directory and apply color space conversions (RGB, HSV, LAB) to the images. Data transformations such as resizing, flipping, and normalization are also applied.

2. **Model Training:** Pre-trained models (DenseNet121) are initialized for each color space (RGB, HSV, LAB). The classifier layers of the models are modified to match the number of target classes. The models are then trained using the provided data and hyperparameters. The training process includes iterating over the specified number of epochs, computing loss and accuracy, and optimizing the model using the Adam optimizer.

3. **Evaluation:** Trained models are evaluated on the test data using metrics such as accuracy, classification reports, and confusion matrices. The evaluation results provide insights into the performance of each color space model in assessing image quality.

4. **AdaBoost Model Selection:** The code performs a grid search using an AdaBoost classifier with decision tree base estimators. The search identifies the best hyperparameters for the AdaBoost model by optimizing the maximum depth of the decision tree and the number of estimators. The best model is selected based on the highest accuracy achieved during the grid search.

5. **Feature Extraction:** The code provides the ability to extract features from the pre-trained models. Features are extracted from both the training and test datasets for each color space. The extracted features are then stacked together.

6. **Image Quality Assessment:** The best AdaBoost model is used to assess the quality of new images. Input images are preprocessed for different color spaces, and features are extracted using the pre-trained models. The extracted features are stacked, and the AdaBoost model predicts the quality of the input image.
