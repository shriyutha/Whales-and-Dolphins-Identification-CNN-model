# HAPPY WHALES AND DOLPHINS INDENTIFICATION - CNN Model

Competition Link: https://www.kaggle.com/competitions/happy-whale-and-dolphin

Data Source: https://www.kaggle.com/competitions/happy-whale-and-dolphin/data

### Files:

1. train_images/ - a folder containing the training images
2. train.csv - provides the species and the individual_id for each of the training images
3. test_images/ - a folder containing the test images; for each image, your task is to predict the individual_id; no species information is given for the test data; there are individuals in the test data that are not observed in the training data, which should be predicted as new_individual.
4. sample_submission.csv - a sample submission file in the correct format

### This notebook has the follow steps:

* Brief Description of the Problem and Data
* Exploratory Data Analysis (EDA) and Preprocessing
* Results and Analysis
* Conclusion

## Brief Description of the Problem and Data:

Whales and dolphins are a key component for the marine ecosystem so being able to identify species could be helpful for other research projects.

In this project, we are given 51033 images which are connected to the training dataframe, in which we are given the columns 'image id' as jpg, 'species', and 'individual_id'. We also are given testing images.

We also note that we do not have bounding boxes on the images and all the images are different shapes and resolutions.

The main task was to predict individual whales and dolphins from images of their fins. Whales and dolphins in this dataset can be identified by shapes, features and markings of dorsal fins, backs, heads and flanks.

### Set paths:

1. train = '../input/happy-whale-and-dolphin/train_images'
2. test = '../input/happy-whale-and-dolphin/test_images'

## Exploratory Data Analysis (EDA) and Preprocessing:

#### Summary of preprocessing steps we will perform:

* Loading the image
* Fix misspellings
* Properly group whales and dolphins
* Normalize images (multiply by 1/255)
* Crop images to 64x64 pixel and 3 channels (64, 64, 3)
* Split into training-validation sets (80-20 split)

## Model Construction and Architecture:

During model training, we shuffle the data, normalize the images, and crop them to 64x64 pixels. These steps can help make the model more robust and learn better because the images are all standardized and shown in more positions. We will be using Tensorflow layers to construct our models.

For this project we will use one very simple model. The model will have five layers after its "base" layer. We call it a "base" layer so that we may more easily compare the model later on. In addition, model's input will be with a shape of (64, 64, 3). And it has following layers:

* Average Pooling
* Dropout layer with 0.1 dropout
* BatchNormalization
* Output layer using Dense with unique categories and activation function as 'softmax'
* Optimizer Adam

## Results:

<img width="1401" alt="Screen Shot 2023-03-03 at 2 17 15 PM" src="https://user-images.githubusercontent.com/81925727/222844987-c823e53a-5da1-4966-993a-2a0b0c49c47c.png">
