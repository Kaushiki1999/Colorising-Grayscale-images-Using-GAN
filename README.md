
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
