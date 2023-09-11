# Melanoma Detection
>  In this, we 'll build a CNN based model which can accurately detect melanoma.
>
>  Melanoma is a type of cancer that can be deadly if not detected early. It accounts for 75% of skin cancer deaths. A solution that can evaluate images and alert dermatologists about the presence of melanoma has the potential to reduce a lot of manual effort needed in diagnosis.


## Table of Contents
* [General Info](#general-information)
* [Conclusions](#conclusions)

<!-- You can include any other section that is pertinent to your problem -->

## General Information

- Dataset Info:
  1. The dataset is from ISIC - The International Skin Imaging Collaboration
      - Link: [Click Here](https://drive.google.com/u/0/uc?id=1xLfSQUGDl8ezNNbUkpuHOYvSpTyxVhCs&export=download)
  2. It has 2239 samples in training data and 118 samples in test data
  3. It has total 9 classes - 'actinic keratosis', 'basal cell carcinoma', 'dermatofibroma', 'melanoma', 'nevus', 'pigmented benign keratosis', 'seborrheic keratosis', 'squamous cell carcinoma' and 'vascular lesion'
     
- Model Building Steps:
  1. Downloaded the data from google drive link & unzip it.
  2. Created training & validation data uisng 'tf.keras.preprocessing.image_dataset_from_directory'
  3. Visualized one image from each class
  4. Created a base line model
     - 4 sets of 2D convolution & 2D max-pooling with dense layer at the end.
     - Activation function: 'relu'
  5. We find out that our model was highly overfit because of the huge gap b/w training & validation accuracy & loss. So, we did some data augmentation to resolve the issue
  6. Created 2nd model
      - All layers are same except a dropout layer is added.
      - A new model is trained on the augmented data.
  7. Improvement in model performance interms of gap b/w the training & validation accuracy as well as loss but the overall performance of the model is not good (Very low accuracy).
  8. I use 'Augmentor' to handle data imbalance by adding '500' samples in each class. Now, no class 'll have a very few data samples.
  9. Created 3rd Model
      - All the layers are same as in the 2nd model
      - The new model is trained on the newly augmented data.
  10. We saw a good improvement in the model accuracy as well as the loss .
      
<!-- You don't have to answer all the questions - just the ones relevant to your project. -->

## Conclusions
  1. Data augmentation has helped the model in handling overfitting
  2. Data imbalance augmentation has helped the model improve it's accuracy & loss.

<!-- As the libraries versions keep on changing, it is recommended to mention the version of library used in this project -->
