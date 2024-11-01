# A Graphical Tool for Designing and Training Deep Neural Networks
This work is the result of my bachelor thesis. The idea was to build a graphical tool to design, create, and test neural networks. Further the tool should be able to export the neural network to integrate it into other applications. On top of that it should be able to load and preprocessing the data.


## General information
<img align="right" width="300" height="" src="https://upload.wikimedia.org/wikipedia/commons/1/1e/Logo-Goethe-University-Frankfurt-am-Main.svg">

**Supervisor**
* [Prof. Dr. Detlef Kroemker](https://www.studiumdigitale.uni-frankfurt.de/75926978/Prof__Dr__Detlef_Kr%C3%B6mker__Pensioniert_seit_01_04_2020)

**Institutions**
* **[Goethe University](http://www.informatik.uni-frankfurt.de/index.php/en/)**
* **[GDV - Uni Frankfurt](https://www.gdv.informatik.uni-frankfurt.de/)**

**Project team**
* [Pascal Fischer](https://github.com/Psarpei/)

**Configuration**
* Python3.6.4
* pyqt5-5.15.2
* pillow-8.1.0 
* six-1.15.0 
* torchvision-0.4.1
* dataclasses-0.8 
* numpy-1.19.5 
* torch-1.7.1 
* typing-extensions-3.7.4.3


## Project
The software currently offers the following building blocks and functions to create artificial neural networks:

* Convolutional, dropout layers as well as fully connected layers.
* Max and average pooling
* The activation functions ReLU and sigmoid
* A function to transfer the neurons from several feature maps into a feature map for further processing
* Drawing connections between the layers with automatic creation of the connections of the correct neurons between the layers, depending on the selected type of layer
* Automatic application of any number of successively executed activation functions to the output neurons of a layer, depending on the selection of the activation functions and the type of layer.
* Unlimited area for adding neural network building blocks in the worldwidget.
* Automatic creation of an artificial neural network from the connected layers within the worldwidget

In addition to the building blocks and functions for creating artificial neural networks, the software contains the functions:

* Loading and saving artificial neural networks and their current weights.
* Training of artificial neural networks
* 2 different types for reading and automatic preprocessing of image data and their labels for training a neural network for object classification in images.
* Training artificial neural networks for classification of images.
* Test and evaluation of artificial neural networks for the classification of images with single images.
* Test and evaluation of datasets during training as well as outside of training.
* Exporting trained artificial neural networks to an executable Python script.
* Output of instructions on how to operate the software, the current training status, test results etc. in the console.

**GUI**

<p align="center">                                                                                                                    
    <img align="top" width="1300" height="" src="https://upload.wikimedia.org/wikipedia/commons/3/3e/Networkx1.jpg">
</p>

The basic part of the user interface consists of the so-called world widget, which represents the white horizontally and vertically scrollable area, and the console, which represents the white area directly below it. In addition, there is a toolbar directly at the top of the software, which provides functions for using the software in certain categories. The Worldwidget, through the submenus Layer and Functions, building blocks for the generation of artificial neural networks can be added. In the Worldwidget the
blocks can be linked to a graph and modified by their possible settings. settings. The input layer is marked in green and can be changed at any time. During the training or testing process, the software automatically creates an artificial neural network from the graph and processes the weights invisibly for the user. The console has the task of providing the user information about incorrect operation, training status, test results, etc. If the console size is not capable of displaying all previous outputs, it becomes scrollable, just like the Worldwidget. With the clear button on the left below the console can be used to clear the contents of the console. Besides the submenus
Layer and Functions, the software contains 4 more submenus. The File submenu, which provides functions for importing and exporting neural networks. The data submenu, which allows loading and processing of training data. The submenu Train which provides functions for training (currently only one type of training with different
training with different settings) and the submenu Test, which provides functions to provides functions for evaluation and testing. The size of the Worldwidgets and the
console can be resized by using the mouse on the gray border between them.

## Tutorial

In the following the use of Networkx will be explained by creating a convolutional neural network for recognizing digits with the [MNIST-Dataset](http://yann.lecun.com/exdb/mnist/).

**Creating a neural network**

The first step is to create a convolution layer. To add a convolution layer to the worldwidget, select the Layer submenu and click on the Convolution Layer tab. Now the convolution layer should appear in the upper left corner of the worldwidget. 


<p align="center">                                                                                                                    
    <img align="top" width="400" height="" src="https://upload.wikimedia.org/wikipedia/commons/3/3d/NeuronalesNetzErstellen1.jpg">
</p>

The building block can be moved like any other by holding down the mouse button and dragging it to the area of the building block. To change the parameters, the mouse must also be placed on the area of the building block and the right mouse button must be pressed.  A drop-down menu appears, which allows to execute the functions Edit, Draw, Delete, Delete links and First Layer. When Draw is pressed, the mouse can be used, left-click on another block to create a connection with it. By double-clicking with the left mouse button on a block, a connection can also be made from this block. The connection is made from the output of the block from which a connection is made to the input of the block to which the connection is to which the connection is subsequently closed with a left click. By pressing the left mouse button on the same block the creation of a connection can be canceled. Each block can have only one connection at the output and one at the input. An exception is the First Layer, which cannot have a connection at the input. The Delete function is used to delete the block. Delete Links deletes the connections of the block both at the input and at the output. By selecting First Layer, the current POU becomes the First Layer, turns green and is interpreted by the software as the input layer of the network when generating the artificial neural network. To edit the parameters of a modifiable block, press Edit.

<p align="center">                                                                                                                    
    <img align="top" width="400" height="" src="https://upload.wikimedia.org/wikipedia/commons/c/c0/NeuronalesNetzErstellen2.jpg">
</p>

To change the values, a popup window opens where the values can be selected. With the Ok button the values are taken over in the module, with the Cancel button the change is discarded. the change is discarded. In this case, the parameter in is set to 1, because the MNIST data are gray scale images, which have only one channel.
In order to add a Max-Pooling block the entry Max-Pool, as shown in Fig.4.8. The parameter kernel is changed in the same way as for the Convolution Layer. In this case a 2x2 kernel is needed for the desired architecture. Afterwards the Convolutional Layer and the Max-Pooling have to be connection from the output of the convolutional layer to the input. This is done as described before and should be done after moving the max-pooling block under the convolutional layer block. Now it should look like in the figure above.

**The neural Network**

The final convolutional neural network used here is shown below. 

<p align="center">                                                                                                                    
    <img align="top" width="1200" height="" src="https://upload.wikimedia.org/wikipedia/commons/3/34/NeuronalesNetzErstellen6.jpg">
</p>

The network can be created exactly as described before.

**Read in Data**

In order to supply the network with data for training, the data must be read in and preprocessed.  In the current state, the Data submenu contains 2 different types for processing image data. 

<p align="center">                                                                                                                    
    <img align="top" width="300" height="" src="https://upload.wikimedia.org/wikipedia/commons/b/b1/NeuronalesNetzErstellen7.jpg">
</p>

The basic difference between Picture1 and Picture2 is the way the data is stored. When one of the two is selected, a file dialog opens, which prompts to select the folder with the training data.

<p align="center">                                                                                                                    
    <img align="top" width="1000" height="" src="https://upload.wikimedia.org/wikipedia/commons/f/fc/NeuronalesNetzErstellen8.jpg">
</p>

In the case of Picture1, the images for training must be saved as follows.

<p align="center">                                                                                                                    
    <img align="top" width="1000" height="" src="https://upload.wikimedia.org/wikipedia/commons/4/48/NeuronalesNetzErstellen9.jpg">
</p>

Here the images are sorted into their own subfolders based on their labels. In this case, all zeros in the Zero folder, all ones in the One folder, and so on. Later, the neural network uses exactly the names of the individual folders as labels for the prediction. With Picture2 the whole thing looks a bit different. Here are all training data strored in one folder. The labels of the individual images are contained in the name of the image, which is irrelevant for Picture1. After selecting the training and test data, another popup window opens in which the individual categories for the labels can be entered. The software then automatically assigns the appropriate class to each
class as label, if the name of a class is contained in the title, as shown in the following on the basis of the Cats and Dog dataset.

<p align="center">                                                                                                                    
    <img align="top" width="1000" height="" src="https://upload.wikimedia.org/wikipedia/commons/7/70/NeuronalesNetzErstellen10.jpg">
</p>

After selecting the training dataset, a file dialog opens again, which now requests the test dataset. The same format applies for this as for the training data set.
Last but not least the already mentioned popup window will open.

<p align="center">                                                                                                                    
    <img align="top" width="300" height="" src="https://upload.wikimedia.org/wikipedia/commons/e/e1/NeuronalesNetzErstellen11.jpg">
</p>

The Resize parameter specifies the size in which the images are to be sent to the network. The numerical value specifies the pixel size of the images in X and Y direction. The edge of the images over this area around the center are then cut off by a so-called crop and not used further. For the here used mesh used here, 28 is chosen because the images already all have the same format. So nothing changes for the MNIST dataset in this case. For datasets like the Dogs vs Cats dataset and a static architecture like the one used here, a resize is necessary because the images are already in different shapes and sizes. The second parameter batch size specifies how much training data should be sent through the network in one batch per training step. The last two parameters normalize mean and normlize std, are optional. By specifying both parameters the images are normalized, which is useful if the images are heavily overexposed or underexposed. This hasthe effect that the brightest point is almost white and the darkest point is black. The parameter normalize mean specifies here in a stochastic sense the expected value of the entire data set and normalize std the standard deviation of a single image point. For gray scale images, only one value needs to be specified at a time. For color images, however, a separate value must be determined for each channel (RGB in exactly this order) and entered separated by commas. Since the MNIST dataset is already normalized, it would be useless to normalize it again. So the input fields remain empty! For the dogs vs cats dataset, however, normalization would also be advantageous. By pressing the OK button the data will be loaded and processed. The current status of the processing is displayed in the console, as follows.

<p align="center">                                                                                                                    
    <img align="top" width="300" height="" src="https://upload.wikimedia.org/wikipedia/commons/5/55/NeuronalesNetzErstellen12.jpg">
</p>

The output in the console takes place for each batch loaded where the batch number of the currently processed batch, as well as the percentage of the
loaded data set is specified.

**Training**

As soon as the data is loaded and processed, the training can be started by pressing the Train button in the toolbar. A popup window opens again, in which the properties of the training process can be defined.

<p align="center">                                                                                                                    
    <img align="top" width="300" height="" src="https://upload.wikimedia.org/wikipedia/commons/4/4a/NeuronalesNetzErstellen13.jpg">
</p>

The first parameter optimizer defines which training method should be used. Currently, there is the already known stochastic gradient descent (SGD) and the so-called Adam, which is available in PyTorch. For the MNIST data set SGD was chosen here, but this has no particular reason. The second parameter loss function, specifies the loss function. Again, there are already 2 options binary cross entropy and negative log likelihood, which are also included in PyTorch.  That binary cross entropy was chosen here has also no special reason. The number of epochs, i.e. the number of training runs of all training data, is determined by the parameter epochs. 5 runs should be sufficient for the MNIST dataset with its size to achieve an accuracy of more than 90 % in other datasets like the Dog vs Cats dataset, significantly more runs would be needed due to the high complexity. The learning rate determines the already known learning rate, which defines the training progress. The momentum is an additional option of Pytorch for the stochastic gradient descent, because it uses a version with momentum.  Finally, a checkmark can be placed next to GPU, which causes the training data and the artificial neural network to be loaded onto the GPU and the training to be executed there. This function requires a CUDA capable graphics card. After pressing the OK button, a further file dialog starts, which asks for a destination folder, in which the network and the weights are saved in separate files after each epoch. After that the training process starts. The training progress is displayed for each epoch in the console.

<p align="center">                                                                                                                    
    <img align="top" width="300" height="" src="https://upload.wikimedia.org/wikipedia/commons/a/a2/NeuronalesNetzErstellen14.jpg">
</p>

It should be noted that the training is started at epoch 0.
is started. The current error is output for each training step. At the end of each epoch to be epoch to be trained, the training stops briefly to evaluate the test data set. If GPU is selected, this is also loaded to the graphics card first. The accuracy of the prediction of the neural network on the test data set is then, besides the average error, also displayed in the console. The neural network for the recognition of handwritten digits, as shown in Fig. 4.18, achieves an accuracy of 95.44% after the training is an accuracy of 95.44%, which is a really good result without optimization.

**Test and Validation**

In order to test the trained net again with other data, there is a submenu Test in the toolbar, which so far has the functions Testset and Picture available.

<p align="center">                                                                                                                    
    <img align="top" width="300" height="" src="https://upload.wikimedia.org/wikipedia/commons/d/d7/NeuronalesNetzErstellen15.jpg">
</p>

By pressing Testset, a loaded test set is sent through the network and evaluated. The result is then displayed in the console. To make the prediction for a single image, Picture must be selected. A popup window similar to the one used for reading and preprocessing the training and test data set will open, in which the image can be preprocessed.
can be preprocessed. In addition, a file dialog opens again which can open the image. Here no label is needed, because the net simply makes a prediction here. The image and the subsequent prediction is then displayed in a new popup window.

<p align="center">                                                                                                                    
    <img align="top" width="300" height="" src="https://upload.wikimedia.org/wikipedia/commons/a/ab/NeuronalesNetzErstellen16.jpg">
</p>

Obviously, an image representing a handwritten 6 was chosen and displayed in the popup window along with the prediction Six of the trained network.

**Save, Load, Export**

During training, the artificial neural network and its weights are stored after each epoch, as mentioned earlier.

<p align="center">                                                                                                                    
    <img align="top" width="600" height="" src="https://upload.wikimedia.org/wikipedia/commons/d/dc/NeuronalesNetzErstellen17.jpg">
</p>

The weights are saved in a .pt file and the graphical mesh in a .nx file. When loading later on, make sure that both files are inside the same folder and that the names have not been changed. To load the neural network with its weights, only the .nx file must be loaded. To open a neural network in the software in the File submenu, the function Load Network must be used.

<p align="center">                                                                                                                    
    <img align="top" width="300" height="" src="https://upload.wikimedia.org/wikipedia/commons/5/59/NeuronalesNetzErstellen18.jpg">
</p>

A file dialog opens in which the .nx file must be selected. Afterwards the net is visible in the worldwidget and can be used as described before. To save a network without its weights, the function Save Network is available. Here a file dialog opens again, in which the storage location, as well as the name of the .nx file can be selected. The network can be saved without weights, just as the network with weights by Load Network. With Export.py an already trained network can be exported as a Python script. However, in addition to the net and its weights, because the script converts received data directly to the data to send them through the neural network. Network is available. Here a file dialog opens again, in which the storage location, as well as the name of the .nx file can be selected. The network can be saved without weights, just as the network with weights by Load Network. With Export.py an already trained network can be exported as a Python script.However, in addition to the network and its weights, data must also be loaded for this, since the script directly converts received data to then send it through the neural network. After pressing Export.py, a file dialog opens again in which the name of the .py file and its location must be selected. The python script as well as a .pt file, which contains the weights of the neural net are saved in the selected folder.

<p align="center">                                                                                                                    
    <img align="top" width="600" height="" src="https://upload.wikimedia.org/wikipedia/commons/8/81/NeuronalesNetzErstellen19.jpg">
</p>

In principle, the Python script can be easily integrated and used in other source code, since it is not necessary to understand the entire code. Lines 8-15 of the source code can be seen below.

<p align="center">                                                                                                                    
    <img align="top" width="800" height="" src="https://upload.wikimedia.org/wikipedia/commons/3/3e/NeuronalesNetzErstellen20.jpg">
</p>

In line 8 the file path of the .pt file with the weights of the neural network is specified and stored in the variable path_weights as a string. If the file should be moved, of course also the file path must be changed at this point. To read in an image from the harddisk the string Your Path here must be replaced in line 9 by the file path of the image. In line 12 in the variable categories the single labels are stored in a list. The names of the labels can be changed, but the order must remain the same. The remaining lines are rather insignificant for the use and refer only to the data processing. 

<p align="center">                                                                                                                    
    <img align="top" width="500" height="" src="https://upload.wikimedia.org/wikipedia/commons/7/7a/NeuronalesNetzErstellen21.jpg">
</p>

The prediction of the neural network is made in line
60, where the predicted category is output via the
the index of the list categories, so the order must not be changed. the variable prediction, stores and generates the index of the category the net predicted.
