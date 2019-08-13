# GAN

## Paper
https://papers.nips.cc/paper/5423-generative-adversarial-nets.pdf

#### Abstract

In Generative Adversarial Nets, we simultaneously train two models: 
- *generative* model G : captures the data distribution, 
- *discriminative* model D : estimates the probability that a sample came from the training data rather than G

The training procedure for G is to maximize the probability of D making a mistake.

In the case where G and D are defined by multilayer perceptrons, the entire system can be trained with backpropagation

It is a minimax two-player game. GANs are based on a minimax game rather than an optimization problem.

Our goal is to get a sample that looks like the real thing, so naturally we want to Generator wins, which means we want to generate a sample that Discriminator can not distinguish it.

## Applications
- Generating Images
- Image Modification
- Super Resolution
- Assisting Artists
- Photo-Realistic Images
- Speech Generation
- Face Ageing

## Generating Images
## Structure
- A Generator - this creates the images.
- A Discriminator - this assesses the images and tells the generator if they are similar to what it has been trained on. These are based off real world examples.

### Process 
1. training the discriminator
we input a random noise signal into the generator and creates some images, and provide the discriminator with some features/images we want it to learn 
and the discriminator outputs probabilities. The error is calculated and these are backpropagated through the discriminator, where the weights are updated.
2. Next we train the generator. 
We take the batch of images that it created and put them through the discriminator again. We do not include the feature images. The discriminator will provide an output of probabilities.  The error is calculated and backpropagated through the generator and the weights are updated.
3. the generator and discriminator are trained a little more. Through backpropagation the generator understands its mistakes and starts to make them more like the feature.
This is created through a Deconvolutional Neural Network.

## Code
https://www.kaggle.com/wendykan/gan-dogs-starter

## gan-introduction
https://www.kaggle.com/jesucristo/gan-introduction

## video
https://www.youtube.com/watch?v=O8LAi6ksC80
https://www.youtube.com/watch?v=9JpdAg6uMXs
