# Dog-Breed-Classification

In this project I trained a neural network to recognise dog breeds. 

The dataset I’ve used during the project, was taken from Kaggle: 

https://www.kaggle.com/c/dog-breed-identification

Here some informations about the dataset: 
* There are 120 breeds of dogs (this mean there are 120 different classes).
* There are around 10,000+ in the training set (labels)
* There are around 10,000+ in the test set (no labels)

#### Steps I’ve followed during this project:

* Import the libary and the data: I’ve used TensorFlow2.0 and TensorFlow Hub.
* Getting data ready.
* Convert images into Tensors and creating label for every image.
* Turning data into batches.
* Create Callbacks for early-stopping and for TensorBoard.
* Fitting the model on a subset of 1000 images.
* FItting the model over all data
* Make predictions on the test set.
* Make predictions on custum images.

## Summarized workflow:

First of all, I’ve looked the data and the problem. Data are unstractured so I’ve decided to use a Deep Learning model using transfer learning, with TensorHub, and I’ve chosen a MobileNet V2.

Then I’ve imported the data: I’ve imported the data path and then, using a funciton, I imported images and label.

Here I've checked the distribution of breeds over the data:

![download](https://user-images.githubusercontent.com/109316190/193530839-28c26888-7a78-44ad-8499-8b30e22e3b07.png)

Then I’ve created my own train and validation sets.

After that I’ve preprocessed the data: I’ve turned images into Tensors, and labels into boolean arrays, then I’ve created batches from the data. 

> Batches are subset of data, composed by  couples `(image, label)` that we pass to the model, to train and make prediction. Passing all data to the model could be heavy in memory terms, so we can divide data into batches and passe them one at the time optimize memory usage during fitting and prediction processes. 

![download](https://user-images.githubusercontent.com/109316190/193532493-f190237a-0654-4b50-8d4a-46e2a50cc265.png)

After that I’ve created a model, importing MobileNet v2 from TensoHub, and created early-stop calback and TensorBoard callback. 

>Callbacks are helper functions a model can use during training to do such things as save its progress, check its progress or stop training early if a model stops improving.

Before using all data, I’ve trained the model on a subset of data (1000 images) to see if everything works and after that I’ve passed all data to model and trained it, evaluated it and made predictions over the test data. 

![download](https://user-images.githubusercontent.com/109316190/193533728-556332ff-649d-4768-bd87-aa17864fed53.png)
![download](https://user-images.githubusercontent.com/109316190/193533714-8ad07659-fd04-4ca1-b338-b1f71e19f63a.png)

Here some predictions with their output label: 

![download](https://user-images.githubusercontent.com/109316190/193534008-101c8069-d37e-4c7d-be83-c1d1220c1b10.png)

>Prediction are arrays of probabilities so I've created a funtion to grab the index where probability was maximum and visualize the input image and the conresponding breed, with green text if the prediction was equal to label.

At last I’ve selected some dog images from internet and passed to the model to see the predictions. Here the results.

![download](https://user-images.githubusercontent.com/109316190/193534998-8f13e3b7-aa94-4803-bb39-509a3cbbaf97.png)


