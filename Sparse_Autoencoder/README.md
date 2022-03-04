# Sparse Autoencoders

## What are Sparse Autoencoders?

<img src="https://i.imgur.com/uCoai4y.png" width="400">

[Image Source](https://web.stanford.edu/class/cs294a/sparseAutoencoder.pdf)

**Sparse Autoencoder** applies a “sparse” constraint on the hidden unit activation to avoid overfitting and improve robustness. It forces the model to only have a small number of hidden units being activated at the same time, or in other words, one hidden neuron should be inactivate most of time.

<img src="https://www.jeremyjordan.me/content/images/2018/03/Screen-Shot-2018-03-07-at-1.50.55-PM.png" height="300">

[Image Source](https://www.jeremyjordan.me/autoencoders/)

Sparse autoencoders offer us an alternative method for introducing an information bottleneck without requiring a reduction in the number of nodes at our hidden layers. Rather, we'll construct our loss function such that we penalize activations within a layer. For any given observation, we'll encourage our network to learn an encoding and decoding which only relies on activating a small number of neurons. It's worth noting that this is a different approach towards regularization, as we normally regularize the *weights* of a network, not the *activations*.

This will force the sparse autoencoder to selectively activate regions of the network depending on the input data. As a result, we've limited the network's capacity to memorize the input data without limiting the networks capability to extract features from the data.

There are two main ways by which we can impose this sparsity constraint; both involve measuring the hidden layer activations for each training batch and adding some term to the loss function in order to penalize excessive activations.

* **L1 Regularization**: We can add a term to our loss function that penalizes the absolute value of the vector of activations a in layer h for observation i, scaled by a tuning parameter λ.

  <img src="https://i.imgur.com/8cca0kg.png" height="75"><img src="https://i.imgur.com/G7c1f0p.png" height="75">

* **KL-Divergence**: In essence, KL-divergence is a measure of the difference between two probability distributions. We can define a sparsity parameter ρ which denotes the average activation of a neuron over a collection of samples. In essence, by constraining the average activation of a neuron over a collection of samples we're encouraging neurons to only fire for a subset of the observations. We can describe ρ as a Bernoulli random variable distribution such that we can leverage the KL divergence (expanded below) to compare the ideal distribution ρ to the observed distributions over all hidden layer nodes ρ^.

  <img src="https://i.imgur.com/hZkL1OF.png" width="400" height="100"><img src="https://i.imgur.com/vqmscvv.png" height="100">
  
  ---
  
  ## Output

### Using Linear Neural Network

&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;**Using KL Divergence Loss** &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;**Using L1 Regularization Loss**

<img src="https://i.imgur.com/XG9RMKz.png" height="200" title="Using KL Divergence Loss">&emsp;</t> <img src="https://i.imgur.com/WCxxJYB.png" height="200" title="Using L1 regularization loss">

### Using Convolutional Neural Network

&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;**Using KL Divergence Loss** &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;**Using L1 Regularization Loss**

<img src="https://i.imgur.com/0MdPDHp.png" height="200" title="Using KL Divergence Loss">&emsp;<img src="https://i.imgur.com/q165SU9.png" height="200" title="Using L1 regularization Loss">

## Tools used:

* [Python](https://www.python.org/)
* [Jupyter Notebook](https://jupyter.org/)
* [Numpy](https://numpy.org/)
* [Matplotlib](https://matplotlib.org/)
* [Pytorch](https://pytorch.org/)
