# Deep learning project
This project which aims to develop a model to distinguish between xrays of people with pneumonia and people without pneumonia

##The project consists of the following parts:
1. Preparing the dataset 
2: Augment the data with a DataGenerators
3. Creating the model (visuals included)
4. Visualising the result

##Augment the data with a DataGenerators
Data augmentation, specifically image augmentation in our case, is a technique I can use to prevent overfitting. This is done by expanding the size of the training dataset by making transformed version of the images in the dataset. These transformations or modification I can somewhat control with the parameters in the function. I will be using the ImageDataGenerator from keras. This will only be applied to the training dataset as I am not interested in transforming the validation set and test set as the model needs to predict on unmodified data.


The model run fasted with smaller batch sizes and will update the gradient more often while trying to estimate the function.

I tested models with img size 250x250 and 500x500. The second gave us better performing models as normalized images were more detailed. However, smaller dimensions speeded up fitting the model 3





1. Using following non-deep learning to perform image classification (tumor detection): 
    - support vector machines 
    - random forests  
    - boosting 


2.	Using convolutional neural networks to perform image classification (tumor detection) and trying with alternative CNN models that includes:
a.	Spatial transformer networks.
b.	Discuss different optimization methods and motivate your final choice. Use visualizations to show the relative performance of the optimizers.
c.	Visualize how regularization (such as dropout, weight regularization, or early stopping) impacts the training of your model. Here, be sure to visualize plots of train and validation losses and accuracies both with and without the use of regularization. Discuss regularization and its relation to overfitting.
d.	Visualize how data augmentation impacts the training of your model. Here, be sure to visualize plots of train and validation losses and accuracies both with and without the use of data augmentation. Discuss data augmentation and its relation to overfitting. 
e.	Discuss and apply transfer learning. Motivate what type of transfer learning you use and how you apply it, including considerations for how to prepare the data for this. Here, be sure to visualize plots of train and validation losses and accuracies.
f.	Following up on the points made by Tan and Le (2020, EfficientNet) investigate and discuss how important image resolution is relative to network width and network depth.
3.	Having run the experiments above, select your preferred models (motivate why it is your preferred models). Calculate and report their performance on the test data.
