# Denoising Autoencoders

## What are Denoising Autoencoders?

<img src="https://lilianweng.github.io/posts/2018-08-12-vae/denoising-autoencoder-architecture.png" width="600">

[Image Source](https://lilianweng.github.io/posts/2018-08-12-vae/)

**Denoising Autoencoder** is a modification to the basic autoencoder. 
The input is partially corrupted by adding noises to the original dataset or masking some values of the input vector in a stochastic manner. 
Then the model is trained to recover the original input (note: not the corrupt one). The loss function is calculated between the output and original input (not the corrupted input)

This is done to avoid the risk of “overfitting” when there are more network parameters than the number of data points using Vanilla Autoencoders, and to improve robustness.

This design is motivated by the fact that humans can easily recognize an object or a scene even the view is partially occluded or corrupted. 
To “repair” the partially destroyed input, the denoising autoencoder has to discover and capture relationship between dimensions of input in order to infer missing pieces.

The noise is controlled by a stochastic mapping, and it is not specific to a particular type of corruption process (i.e. masking noise, Gaussian noise, salt-and-pepper noise, etc.). 
Naturally the corruption process can be equipped with prior knowledge.

For high dimensional input with high redundancy, like images, the model is likely to depend on evidence gathered from a combination of many input dimensions to recover the denoised version rather than to overfit one dimension. 
This builds up a good foundation for learning robust latent representation.

## Output

### Using Linear Neural Network

<img src="https://i.imgur.com/aQf5K7B.png" width="400">

### Using Convolutional Neural Network

<img src="https://i.imgur.com/R1XLgiq.png" width="400">

## Tools used:

* [Python](https://www.python.org/)
* [Jupyter Notebook](https://jupyter.org/)
* [Numpy](https://numpy.org/)
* [Matplotlib](https://matplotlib.org/)
* [Pytorch](https://pytorch.org/)
