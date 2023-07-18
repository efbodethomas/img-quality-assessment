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

7. This project uses several python libraries that need to be installed for the project to run successfully. 

## Installation

This guide assumes that you have a Python interpreter (version 3.7 or newer) installed on your system. Please download and install Python from the official website if you don't.

## Create a Virtual Environment (Optional)

To avoid conflicts with other projects, it's recommended to create a virtual environment. If you wish to do so, follow these steps:

## On Windows:
python -m venv env
env\Scripts\activate

## On Unix or MacOS:
python3 -m venv env
source env/bin/activate

## Install Dependencies

The dependencies for the project are listed in the requirements.txt file. To install them, use the pip tool (which comes with Python):

pip install -r requirements.txt

The requirements.txt file should contain the following:

asttokens==2.2.1
backcall==0.2.0
certifi==2022.12.7
charset-normalizer==2.1.1
colorama==0.4.6
comm==0.1.3
contourpy==1.0.7
cycler==0.11.0
debugpy==1.6.7
decorator==5.1.1
executing==1.2.0
filelock==3.9.0
fonttools==4.39.3
idna==3.4
imageio==2.27.0
ipykernel==6.22.0
ipython==8.12.0
jedi==0.18.2
Jinja2==3.1.2
joblib==1.2.0
jupyter_client==8.1.0
jupyter_core==5.3.0
kiwisolver==1.4.4
lazy_loader==0.2
MarkupSafe==2.1.2
matplotlib==3.7.1
matplotlib-inline==0.1.6
mpmath==1.2.1
nest-asyncio==1.5.6
networkx==3.0
numpy==1.24.1
opencv-python==4.7.0.72
packaging==23.1
pandas==2.0.0
parso==0.8.3
pickleshare==0.7.5
Pillow==9.3.0
platformdirs==3.2.0
prompt-toolkit==3.0.38
psutil==5.9.4
pure-eval==0.2.2
Pygments==2.15.0
pyparsing==3.0.9
python-dateutil==2.8.2
pytz==2023.3
PyWavelets==1.4.1
pywin32==306
pyzmq==25.0.2
requests==2.28.1
scikit-image==0.20.0
scikit-learn==1.2.2
scipy==1.10.1
seaborn==0.12.2
six==1.16.0
stack-data==0.6.2
sympy==1.11.1
threadpoolctl==3.1.0
tifffile==2023.4.12
torch==2.0.0+cu118
torchaudio==2.0.1+cu118
torchvision==0.15

