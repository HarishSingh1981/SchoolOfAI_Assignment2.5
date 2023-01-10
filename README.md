# SchoolOfAI_Assignment2.5
Neural network to take Mnist data set and a random number as input and return 2 outputs. 

1. First output is label for the Mnist input image
2. Second output is sum of Mnist input label with random number

Data Representation:

Defined own dataset class called MyDataset. MyDataset provides multiple data
1. Mnist data i.e. tuple of image and label
2. Custom data i.e. tuple of random number and sum of respective Mnist data label with random number

random number is presented as array of 10 float32 numbers where respective position is set to 1 and rest are set to 0. For Ex. 7 is presented as [0000000100]
Sum [random number + Mnist label] is also presented as numpy array of 19 float32 numbers. where respective position is set to 1 and rest are set to 0. For Ex. 17 is
presented as [0000000000000000010]

Network Details:

Network consist of 2 convolution layer with kernel size=5 and 4 fully connected layer.
Third fully connected layer is predicting the output for Mnist input image. The output of 3rd fully connected layer[10 neurons] and random number input [10 neurons]
is connected to 4th FC layer with 19 output which is basically second prediction. [prediction of sum]
Finally softmax function is used before both the outputs to get the probability distribution and likliness of result.

Error Function:

cross_entropy error function is used for both the results and avg of error is used for back-propogation.
avg_error = 0.5*loss_mnist + 0.5*loss_sum

I have used CPU for training as google collab GPU was not available due to resource constraint.

Logs for training with total predictions of Mnist data and sum:

Length of Mnist dataset -- > 60000
Available device -- > cuda0

epoch --> 0 loss_mnist --> 515.3477172851562 and correct predictions --> 51408

epoch --> 0 loss_sum --> 2806.18017578125 and correct predictions of sum --> 8650

epoch --> 1 loss_mnist --> 137.37863159179688 and correct predictions --> 57901

epoch --> 1 loss_sum --> 1542.6768798828125 and correct predictions of sum --> 29731

epoch --> 2 loss_mnist --> 106.59422302246094 and correct predictions --> 58372

epoch --> 2 loss_sum --> 389.09991455078125 and correct predictions of sum --> 55082

epoch --> 3 loss_mnist --> 79.9377212524414 and correct predictions --> 58764

epoch --> 3 loss_sum --> 141.2874755859375 and correct predictions of sum --> 58287

epoch --> 4 loss_mnist --> 63.076053619384766 and correct predictions --> 59023

epoch --> 4 loss_sum --> 103.64910125732422 and correct predictions of sum --> 58636

epoch --> 5 loss_mnist --> 55.3194580078125 and correct predictions --> 59161

epoch --> 5 loss_sum --> 84.63861083984375 and correct predictions of sum --> 58841

epoch --> 6 loss_mnist --> 48.241661071777344 and correct predictions --> 59277

epoch --> 6 loss_sum --> 74.02021789550781 and correct predictions of sum --> 58975

epoch --> 7 loss_mnist --> 42.88951873779297 and correct predictions --> 59328

epoch --> 7 loss_sum --> 64.63426971435547 and correct predictions of sum --> 59100

epoch --> 8 loss_mnist --> 38.94873809814453 and correct predictions --> 59384

epoch --> 8 loss_sum --> 57.48320388793945 and correct predictions of sum --> 59159

epoch --> 9 loss_mnist --> 37.196250915527344 and correct predictions --> 59395

epoch --> 9 loss_sum --> 54.71113586425781 and correct predictions of sum --> 59218

Training Accuracy:

Accuracy of prediction of Mnist dataset is 98.9916%

Accuracy of prediction of sum of random number with Mnist dataset label is 98.6966 %

Validation Accuracy:

