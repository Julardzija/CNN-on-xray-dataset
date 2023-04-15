# Deep learning project [Open in Google Colab](https://colab.research.google.com/github/Julardzija/Deep-learning-on-pneumonia-xray-data/blob/main/CNN on Pneumonia Xray data.ipynb)
This project which aims to develop a model to distinguish between xrays of people with pneumonia and people without pneumonia

## The project consists of the following parts:
1. Preparing the dataset 
2: Augment the data with a DataGenerators
3. Building the model (visuals included)
4. Visualising the result

## Preparing the dataset
The dataset is available and shared through my Google Drive, which you are able to download in order to try and run the code. 

## Augment the data with a DataGenerators
Data augmentation, specifically image augmentation in our case, is a technique to prevent overfitting. This is done by expanding the size of the training dataset by making transformed version of the images in the dataset. These transformations or modification I can somewhat control with the parameters in the function. I will be using the ImageDataGenerator from keras. This will only be applied to the training dataset as I am not interested in transforming the validation set and test set as the model needs to predict on unmodified data.

**Note:** Data augmentation techniques used for any dataset must be chosen carefully and within the context of the dataset and knowledge of the problem domain. For this reason, I keep the augmentation fairly simple, as I am dealing with human physiology, and we are generally not symmetrical creatures, so mirroring images would not be beneficial as I want to keep left side of the body on the left. I do a few augmentations such as zoom, rotation, width and height shift but I keep the effects low to ensure that it does not look too far apart from realistic images

## Building the model
In order to best detect the patterns in the X-Ray images I chose to construct a Convolutional Neural Network.

I added Pooling layers to each Convolutional layer to be able to down-sample the input representation (image),
moreover, to decrease its dimensionality by retaining the maximum value (activated features) in the sub regions binding.

- Filter value tuning and found out that first 32 and later on 64 gave the most promising results.
- As mentioned above, I decided to design the model with a layer of Conv2D followed by a layer of MaxPooling.
- The kernel_size is 3 x 3 for every layer. I also experimented with adding Dropout layers without major improvement in the model.
- I tested various activation functions such as tanh, relu and leaky relu, but eventually decided to use relu as it performed best. Relu overcomes the problem of vanishing gradients, allowing models to learn faster and perform better.
- I decided to flatten the input after the CNN layers and add 3 ANN layers, afterwards I tuned its hyperparamaters together.
- The sigmoid activation function for the last layer was a straight-forward choice, since it is a binary classification problem.
- When compiling the model, it was again rather straight-forward to set the learning rate to "Adam", the loss function to "binary crossentropy", as well as the metrics to "accuracy". Adam is an adaptive learning rate method, meaning that it computes individual learning rates for different parameters. Since the nature of this problem is still binary classification, I used binary crossentropy for the evaluation of losses. Setting the metrics to "accuracy" measured the loss and accuracy of both the training and validation sets.

## Visualising the results
Here I am showing a confusion matrix, which is a contigency table, showing us True Positives, True Negatives, False Positives and False Negatives predictions. I also show a visualization of 9 predictions of the model and the confidence, expressed in % on how confident the model is in predicting classes Normal / Pneumonia. The example shows that the model gives us a good accuracy preformance on the test data and the misclassified image as Normal looks similar to the images of XRays from normal condions.  

## Conclusion
The evaluation of the model is made by making a prediction on the test data set. Looking at the results of that gives us an argument, that the model seems to be good at generalizing and making good prediction, as the test set accuracy is 95,53% which is close to the validation accuracy of 98,17%
