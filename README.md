# GAN-for-Face-Image-Generation
Generative Adversarial Networks for generation of facial images of celebrities

<h2>Dataset</h2>

You can download the dataset from [here](https://s3.amazonaws.com/video.udacity-data.com/topher/2018/November/5be7eb6f_processed-celeba-small/processed-celeba-small.zip)

This is a zip file that you'll need to extract in the home directory of this notebook for further loading and processing. After extracting the data, you should be left with a directory of data `processed_celeba_small/`

The [CelebA](http://mmlab.ie.cuhk.edu.hk/projects/CelebA.html) dataset contains over 200,000 celebrity images with annotations. Since you're going to be generating faces, you won't need the annotations, you'll only need the images.

<h2>Architecture</h2>

<h3>Discriminator</h3>
The inputs to the discriminator are 32x32x3 tensor images -> conv1 -> 16x16x32 -> conv2 8x8x64 -> conv3 -> 4x4x128 -> linear fully connected layer -> (2048,1).
Used batch norm in all layers except the first. Activation function - leaky relu.
The outputs are a single value that will indicate whether a given image is real or fake.

<h3>Generator</h3>
The inputs to the generator are 100 dimensional vectors -> Linear fully connected layer -> (100, 2048) -> tconv1 -> 8x8x64 -> tconv2 -> 16x16x32 -> 32x32x3.
Used batch norm in all layers except the last. Activation function - relu for all except final layer where tanh was used.
The output is an image of shape `32x32x3`.

## Files
GAN-Face-Generator notebook is the mainfile that you need to run.
