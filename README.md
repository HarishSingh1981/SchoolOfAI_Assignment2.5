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
