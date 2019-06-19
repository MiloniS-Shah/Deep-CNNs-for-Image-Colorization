# Deep-CNNs-for-Image-Colorization
Using a convolutional neural network for image colorization which turns a grayscale image to a colored image.
<br>
Using the CIFAR-10 dataset. Downolad the dataset from http://www.cs.toronto.edu/~kriz/cifar-10-python.tar.gz.

From the train and test dataset, extract the class birds. We will focus on this class, which has 6000 members.
Those 6000 images have 6000 X 32 X 32 pixels. Choose at least 10% of the pixels randomly. You will have between P = 614400 and P = 6144000 pixels. Each pixel is an RGB vector with three elements.

<br>
We run K-MEANS CLUSTERING on the P vectors using k = 4.
<br>

The centers of the clusters will be your main colors. Convert the colored images to k-color images by converting each pixel's value to the closest main color in terms of Euclidean distance.
These are the outputs of your network, whose each pixel falls in one of those k classes.
<br>

Using scikit-learn we obtain grayscale 32X32X1 images from the original 32 X 32 X 3 images. 
The grayscale images are inputs of the network.

<br>
Set up a deep convolutional neural network with two convolution layers (or more) and two (or more) MLP layers. Use 5 X 5 filters and a softmax output layer.
We use a minimum of one max pooling layer. Use a classification scheme, which means your output must determine one of the k = 4 color classes for each pixel in your grayscale image.
<br>

Your input is a grayscale version of an image (32X32X1) and the output is 32 X 32 X 4. The output assigns one of the k = 4 colors to each of the 32X32 pixels; therefore, each of the pixels is classified into one of the
classes [1 0 0 0]; [0 1 0 0]; [0 0 1 0]; [0 0 0 1].
<br>

Add a softmax layer which will choose the highest value out of its k = 4 inputs for each of the 1024 pixels 
Therefore, the output of the MLP has to be reshaped into a 32 X 32 X 4 matrix, and to get the colored image, the RGB vector of each of the k = 4 classes has to be converted to the RGB vector, so an output image will be 32 X 32 X 3.
<br>

Plot training,(validation), and test errors in each epoch. 
Report the train and test errors and visually compare the artificially colored versions of the first 10 images in the test set with the original images
