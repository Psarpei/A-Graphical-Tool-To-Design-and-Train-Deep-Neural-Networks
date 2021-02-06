# Networkx-a-Graphical-Tool-for-Designing-and-Training-Deep-Neural-Networks
This work is the result of my bachelor thesis. The idea was to build a graphical tool for design, create, and test neural networks. Further the tool should be able to export the neural network to integrate it into other applications. On top of that it should be able to load and preprocessing the data.


## General information
<img align="right" width="300" height="" src="https://upload.wikimedia.org/wikipedia/commons/1/1e/Logo-Goethe-University-Frankfurt-am-Main.svg">

**Instructors**
* [Prof. Dr. Detlef Kroemker](https://www.studiumdigitale.uni-frankfurt.de/75926978/Prof__Dr__Detlef_Kr%C3%B6mker__Pensioniert_seit_01_04_2020)

**Institutions**
* **[Goethe University](http://www.informatik.uni-frankfurt.de/index.php/en/)**
* **[GDV - Uni Frankfurt](https://www.gdv.informatik.uni-frankfurt.de/)**

**Project team**
* [Pascal Fischer](https://github.com/Psarpei/)

**Tools**
* Python 3
* PyQT5
* PyTorch
* Pillow

## Networkx
The software currently offers the following building blocks and functions to
create artificial neural networks:

* Convolutional, dropout layers as well as fully connected layers.
* Max and average pooling
* The activation functions rectified linear unit (ReLu) and logistic function (sigmoid function)
* A function to transfer the neurons from several feature maps into a feature map for further processing
* Creation of connections between the layers with automatic creation of the connections of the correct neurons between the layers, depending on the selected type of layer
* Automatic application of any number of successively executed activation functions to the output eurons of a layer, depending on the selection of the activation functions and the type of layer.
* Unlimited area for adding neural network building blocks in the worldwidget.
* Automatic creation of an artificial neural network from the connected layers within the worldwidget

In addition to the building blocks and functions for creating artificial neural networks, the software contains the functions:

* Loading and saving artificial neural networks and their current weights.
* Training of artificial neural networks
* 2 different types for reading and automatic preprocessing of image data and their labels for training a neural network for object recognition in images.
* Training artificial neural networks for classification of images.
* Test and evaluation of artificial neural networks for the classification of images with single images.
* Test and evaluation of datasets during training as well as outside of training.
* Exporting trained artificial neural networks to an executable Python script.
* Output of instructions on how to operate the software, the current training status, test results etc. in the console.
