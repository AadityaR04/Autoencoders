# Vanilla Autoencoders

## What are Vanilla Autoencoders?

<img src="https://lilianweng.github.io/posts/2018-08-12-vae/autoencoder-architecture.png" width="600">

[Image Source](https://lilianweng.github.io/posts/2018-08-12-vae/)

**Vanilla Autoencoders**, or simply Autoencoders is used to learn an identity function. 
The input x is passed through the encoder network to the bottleneck latent code and from the bottleneck to the decoder where the original image is reconstructed as x'. The loss is calculated between the input and reconstructed image.

Although we can reconstruct the input and obtain an identity function using a neural network without any bottleneck, in a network as shown below, the main advantage of vanilla autoencoder networks lies in the bottleneck layer.
The reduced dimensions latent code in the bottleneck is used to express the image by a very small number of feature vectors, hence compressiong the image.
So by reconstructing this compressed image, we can transmit the compressed version to the transmitting channel, and we can reduce the cost of bandwidth, which in turn will reduce the cost of telecommunication.

<img src="https://www.jeremyjordan.me/content/images/2018/03/Screen-Shot-2018-03-06-at-6.09.05-PM.png" width="400">

[Image Source](https://www.jeremyjordan.me/autoencoders/)

---
## Output obtained

### Using Linear Neural Network

<img src="https://i.imgur.com/Z3F101D.png" width="400">

### Using Convolutional Neural Network

<img src="https://i.imgur.com/EIL3G0o.png" width="400">

## Tools used:

* [Python](https://www.python.org/)
* [Jupyter Notebook](https://jupyter.org/)
* [Numpy](https://numpy.org/)
* [Matplotlib](https://matplotlib.org/)
* [Pytorch](https://pytorch.org/)
