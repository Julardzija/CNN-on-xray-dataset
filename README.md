# Testing
Project which aims to develop a model to distinguish between xrays of people with pneumonia and people without pneumonia

The project consists of the following part

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
