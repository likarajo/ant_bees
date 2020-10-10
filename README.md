# Ant Bees

Develop computer vision model to classify images of ant and bees using transfer learning.

## Transfer learning

Training large networks from scratch with limited resources and/or limited data sets is not
pragmatic. Recognizing this, **Transfer Learning** is quite popular for vision applications with pre-trained
encoders and language applications with pre-trained language models.

## Project

Here use two major transfer learning scenarios for our vision model:

* **Finetuning the ConvNet**
  Instead of random initializaion, we initialize the network with a pretrained network, like the one that is trained on imagenet 1000 dataset. Rest of the training looks as usual.
* **ConvNet as fixed feature extractor**
  We freeze the weights for all of the network except that of the final fully connected layer. The last fully connected layer is replaced with a new one with random weights and only this layer is trained.
  
## Data

We will use ***torchvision and torch.utils.data*** packages for loading the data.

We are training a model to classify ants and bees. We have about 120 training images each for ants and bees. There are 75 validation images for each class. Usually, this is a very small dataset to generalize upon, if trained from scratch. Since we are using transfer learning, we should be able to generalize reasonably well.

This dataset is a very small subset of imagenet. Download and extract it to the current directory. https://download.pytorch.org/tutorial/hymenoptera_data.zip

### Preprocessing

* Augment and normalize the training data
* Normalize the validation data
