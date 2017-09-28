hion MNIST is a drop-in replacement for the very well known, machine learning hello world, MNIST dataset. It has same number of training and test examples and the images have the same 28x28 size and there are a total of 10 classes/labels, you can read more about the dataset here : [Fashion-MNIST](https://github.com/zalandoresearch/fashion-mnist)


In this post we will be trying out a couple of different models to and compare their results:

## List of models

1. 2 Layer Neural Netwoek
2. CNN with 1 Convolutional Layer
3. CNN with 3 Convolutional Layers
4. VGG Like Model
5. VGG Like Model With Batchnorm


## Approach

I split the original training data into 80% training and 20% validation. This helps to see weather we're over-fitting on the training data and weather we should lower the learning rate and train for more epochs if validation accuracy is higher than training accuracy or stop over-training if training accuracy shift higher than the validation.

To be consistent here, all the models are initially trained for 10 epochs and another 10 epochs with a lower learning late. After the initial 20 epochs, I added data augmentation, which generates new training samples by rotating, shifting and zooming on the training samples, and trained for another 50 epochs.

Also, to avoid hot encoding the labels, I decided to use `sparse_categorical_crossentropy` when compiling the models.

## Observations
All the models achieved a higher accuracy after using data augmentation. Almost always use data augmentation !!


## Fun Fact

If you uncomment the code in **Drop-in Replacement you said?** section, you'll be able to run all the models on MNIST instead of Fashion-MNIST.
It is much easier to get +99.5% results on MNIST. However, as you can see by running the models on both datasets, it gets relatively harder to squeeze accuracy on the Fashion-MNIST dataset. 



