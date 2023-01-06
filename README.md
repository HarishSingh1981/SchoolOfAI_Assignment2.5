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
Available device -- > cpu

epoch --> 0 loss_mnist --> 2761.647705078125 and correct predictions --> 8217

epoch --> 0 loss_sum --> 3532.280517578125 and correct predictions of sum --> 4085

epoch --> 1 loss_mnist --> 2333.012451171875 and correct predictions --> 33738

epoch --> 1 loss_sum --> 3510.42236328125 and correct predictions of sum --> 5642

epoch --> 2 loss_mnist --> 1953.821533203125 and correct predictions --> 50204

epoch --> 2 loss_sum --> 3485.0546875 and correct predictions of sum --> 6801

epoch --> 3 loss_mnist --> 1922.014404296875 and correct predictions --> 51756

epoch --> 3 loss_sum --> 3471.4658203125 and correct predictions of sum --> 7548

epoch --> 4 loss_mnist --> 1907.6500244140625 and correct predictions --> 52449

epoch --> 4 loss_sum --> 3463.781982421875 and correct predictions of sum --> 8274

epoch --> 5 loss_mnist --> 1898.7264404296875 and correct predictions --> 52821

epoch --> 5 loss_sum --> 3452.42041015625 and correct predictions of sum --> 9528

Training Result:

epoch --> 99 loss_mnist --> 1858.3717041015625 and correct predictions --> 54477

epoch --> 99 loss_sum --> 3245.401611328125 and correct predictions of sum --> 19333

Accuracy of prediction of Mnist dataset is 90.795%

Accuracy of prediction of sum of random number with Mnist dataset label is 32.2216 %
