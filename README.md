# DCGAN-for-classification-of-house-numbers

Spencer Gable-Cook, Bowei Li, Khoa Dang Nguyen, Sanket Kanubhai Yadav


Implement a Deep Convolutional Generative Adversarial Network, proposed by Radford et al. (Radford et al., 2015), to generate realistic images and access the performance of the network using K-Nearest Neighbour algorithm.

Data set: Street View House Number (SVHN), 68652 images of digits 0 to 10 taken from street addresses in 32x32 size.

The main differences between a traditional GAN and DCGAN include:

-Pooling layers are replaced with strided convolutions in the discriminator and fractional-strided convolutions in the generator

-Batchnorm is used in both the generator and discriminator

-Fully connected layers are removed

-Use ReLU activation in all layers of generator, except for Tanh in the output of generator and Sigmoid in output of discriminator

# Generator Architecture

Input: an vector of uniform noise distribution

Layers:

Number of layers are adjustable. We find the optimal number is 3.

Transpose convolution,

Batch normalized 

Rectified linear activation function	

Final layer: Tanh activation

Output : an image 32x32, 3 channels

Total trainable parameters = 2,962,307

# Discriminator Architecture

Input: 32x32, 3 channels images

Layers:

Number of layers are adjustable. We find the optimal number is 3.

Convolution,

Batch normalized 

Leaky rectified linear activation, slope of 0.2

Final layer:   sigmoid function 

Output: probability to be real

0 = fake, 1= real

Total trainable parameters = 2,759,424


# Result

K Nearest Neighbors (k-NN) was performed to classify each of the generated images to evaluate how realistic each generated image was.K-NN was tested on the original SVHN Dataset



  
Accuracy (%)

K value | Original Dataset | Fake Dataset | Combined Dataset

3       | 31.5             | 21.33        | 50.80

5       | 28.9             | 20.90        | 53.69

10      | 30.4             | 20.67        | 55.55





