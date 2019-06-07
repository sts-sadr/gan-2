# TensorFlow-GAN (TF-GAN)

TF-GAN is a lightweight library for training and evaluating [Generative
Adversarial Networks (GANs)](https://arxiv.org/abs/1406.2661).


* Can be installed with `pip` using `pip install tensorflow-gan`, and used
with `import tensorflow_gan as tfgan`
* [Well-tested examples](https://github.com/tensorflow/gan/examples/)
* [Interactive introduction to TF-GAN](https://github.com/tensorflow/gan) in colaboratory
* TPU support, an [interactive introduction to TF-GAN on cloud TPU](https://github.com/tensorflow/gan/examples/colab_notebooks/tfgan_on_tpus.ipynb), and a complete [DCGAN on TPU example](https://github.com/tensorflow/gan/)
* [Google internal interactive introduction to TF-GAN on TPU](https://github.com/tensorflow/gan), and [TPU examples on borg](https://github.com/tensorflow/gan/google/examples/mnist_estimator_tpu/)

## Structure of the TF-GAN Library

TF-GAN is composed of several parts, which are designed to exist independently:

*   [core](https://github.com/tensorflow/gan/python/train.py):
    the main infrastructure needed to train a GAN. Set up training with
    any combination of TF-GAN library calls, custom-code, native TF code, and other frameworks
*   [features](https://github.com/tensorflow/gan/python/features/):
    common GAN operations and
    normalization techniques, such as instance normalization and conditioning.
*   [losses](https://github.com/tensorflow/gan/python/losses/):
    losses and
    penalties, such as the Wasserstein loss, gradient penalty, mutual
    information penalty, etc.
*   [evaluation](https://github.com/tensorflow/gan/python/eval/):
    standard GAN evaluation metrics.
    Use `Inception Score`, `Frechet Distance`, or `Kernel Distance` with a
    pretrained Inception network to evaluate your unconditional generative
    model. You can also use your own pretrained classifier for more specific
    performance numbers, or use other methods for evaluating conditional
    generative models.
*   [examples](https://github.com/tensorflow/gan/)
    simple examples on how to use TF-GAN, and more complicated state-of-the-art examples

## Who uses TF-GAN?

Numerous projects inside Google. The following are some published papers that use TF-GAN:

* [Are GANs Created Equal? A Large-Scale Study](https://arxiv.org/abs/1711.10337)
* [The GAN Landscape: Losses, Architectures, Regularization, and Normalization](https://arxiv.org/abs/1807.04720)
* [Self-Attention Generative Adversarial Networks](https://arxiv.org/abs/1805.08318)
* [Large Scale GAN Training for High Fidelity Natural Image Synthesis](https://arxiv.org/abs/1809.11096)
* [Discriminator rejection sampling](https://arxiv.org/abs/1810.06758)
* [The GAN Landscape: Losses, Architectures, Regularization, and Normalization](https://arxiv.org/abs/1807.04720)
* [GANSynth: Adversarial Neural Audio Synthesis](https://arxiv.org/abs/1902.08710)

## Training a GAN model

Training in TF-GAN typically consists of the following steps:

1. Specify the input to your networks.
1. Set up your generator and discriminator using a `GANModel`.
1. Specify your loss using a `GANLoss`.
1. Create your train ops using a `GANTrainOps`.
1. Run your train ops.

At each stage, you can either use TF-GAN's convenience functions, or you can
perform the step manually for fine-grained control.

There are various types of GAN setup. For instance, you can train a generator
to sample unconditionally from a learned distribution, or you can condition on
extra information such as a class label. TF-GAN is compatible with many setups,
and we demonstrate in the well-tested [examples directory](https://github.com/tensorflow/gan/examples/)


## Maintainers

* Paolo Galeone, nessuno@nerdz.eu, [github](https://github.com/galeone)
* (Documentation) David Westbrook, westbrook@google.com
* Joel Shor, joelshor@google.com, [github](https://github.com/joel-shor)
* Aaron Sarna, sarna@google.com, [github](https://githun.com/aaronsarna)

## Authors
* Joel Shor, joelshor@google.com, [github](https://github.com/joel-shor)
