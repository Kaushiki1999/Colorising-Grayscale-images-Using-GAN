Introduction:
Colorization is a popular image-to-image translation problem. It is a process of converting
grayscale images into visually acceptable colour images. The main goal is to convince the
viewer of the authenticity of the result. Here we have implemented the GAN architecture for
colorization of grayscale image into RGB images. There are two competing neural network
models in generative adversarial networks (GAN). The generator generates a fake image using
the input. Together with the grayscale or edge-only input, the discriminator receives images
from both the generator and the label and attempts to determine which pair really comprises a
coloured image. Generator and discriminator engage in a constant game during training. The
discriminator becomes increasingly adept at identifying fake images, while the generator
becomes more realistic with each iteration.

PROPOSED ARCHITECTURE:
i) GENERATOR ARCHITECTURE:
The generator model consists of several layers that progressively transform an input image
into an output image. It starts with an input layer that takes images of size img_size x
img_size x 1 (grayscale). The input is then passed through a series of convolutional layers
with increasing numbers of filters, followed by leaky ReLU activation functions, which
introduce non-linearity to the model. The convolutional layers capture and learn features
from the input images.
After the initial convolutional layers, the model undergoes a series of transposed
convolutional layers (also known as up sampling) combined with concatenation operations.
These layers gradually increase the spatial resolution of the image while refining the
learned features. The transposed convolutional layers use the ReLU activation function to
introduce non-linearity and refine the generated features.
The final output layer of the generator model performs transposed convolution with a kernel
size of (5, 5) and 3 filters to generate the output image with three colour channels (RGB).
The activation function used in this layer is ReLU. The concatenation operations in the
intermediate layers help to combine low-level and high-level features from different stages
of the network, aiding in the generation of more detailed and realistic output images.
Overall, the generator model follows a U-NET architecture which consists encoderdecoder, where the initial layers act as an encoder to extract features, and the subsequent
layers perform decoding and up sampling to generate the final output image.

ii) DISCRIMINATOR ARCHITECTURE:
The provided code defines a discriminator model using the Keras API in TensorFlow. The
discriminator is a convolutional neural network (CNN) architecture that plays a crucial role in
generative adversarial networks (GANs). GANs consist of a generator and a discriminator, with
the discriminator tasked with distinguishing real data from fake or generated data produced by
the generator. The discriminator model is composed of multiple convolutional layers, each
followed by a max pooling layer for down sampling. These convolutional layers perform
feature extraction and capture increasingly complex patterns in the input images. The model
also includes fully connected layers that learn high-level representations from the extracted
features. The final layer of the discriminator is a dense layer with a sigmoid activation function,
which produces a single output value between 0 and 1. This output represents the probability
that the input image is real (closer to 1) or fake or generated (closer to 0).By training the
discriminator alongside the generator, the GAN system aims to improve the generator's ability
to produce more realistic samples. The discriminator's purpose is to accurately classify the
generated samples as fake, providing feedback to the generator for refinement. In summary,
the provided code defines a discriminator model that acts as a key component in GANs,
distinguishing real and generated data and contributing to the training process for generating
more realistic samples.
