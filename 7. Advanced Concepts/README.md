## 7 - ADVANCED CONCEPTS

*Advance Convolutions, Attention and Image Augmentation: Depthwise, Pixel Shuffle, Dilated, Transpose, Channel Attention, and Albumentations Library*

**Contents:**

- [Convolution](./README.md/#convolution)

- [Pointwise Convolutions](./README.md/#PC)

- [Concept of Channels](./README.md/#channels)

- [Receptive Field](./README.md/#RF)

- [Checkerboard Issue](./README.md/#issue)

- [Atrous or Dilated Convolutions](./README.md/#Atrous)

- [Dense Problems](./README.md/#dense-problem)

- [Deconvolutions or Transpose Convolutions](./README.md/#transpose)

- [Pixel Shuffle Algorithm (SKIPPED)](./README.md/#pixel)

- [Depthwise Separable Convolution](./README.md/#deptwise)

- [Spatially Separable Convolution (SKIPPED)](./README.md/#spatial)

- [Grouped Convolutions](./README.md/#grouped)

<h1 align = 'center' id = "convolution"> Convolution</h1>

**What is Convolution?**

    ⊛ The process of extracting features from input data using kernels/filters.
    
    ⊛ Filter moves discretely on top of the data-plane/channel, scale the input data equal to the size of its receptive field sums
    these results and creates a new feature map.

<h1 align = 'left'>Normal Convolutions</h1>

<p align = 'center'>
            <img src = Images/Normal_Convolution.gif width="700" height="400"/>
</p>

<p align = 'center'>
            <img src = Images/Maths_NC.gif width="700" height="400"/>
</p>

<h1 align = 'center' id = "PC"> Pointwise Convolutions </h1>

*Pointwise Convolution is a type of convolution that uses a 1x1 kernel: a kernel that iterates through every single point. This kernel has a depth of however many channels the input image has. It can be used in conjunction with depthwise convolutions to produce an efficient class of convolutions known as depthwise-separable convolutions.*

<p align = 'center'>
            <img src = Images/PC.png/>
</p>

<p align = 'center'>
            <img src = Images/Pointwise_Convolutions.png/>
</p>

<br>

<h1 align = 'center' id = "channels"> Concept of Channels </h1>

When we feed a CNN colored images, those images come in three channels: Red, Green, Blue.

Say we have a 32 x 32 image like in CIFAR-10. For each of the 32 x 32 pixels, there is a value for the red channel, the green, and the blue, (this value is likely different cross the channels). The CNN interprets one sample as 3 x 32 x 32 block.

In later layers of a CNN, you can have more than 3 channels, with some networks having 100+ channels. These channels function just like the RGB channels, but these channels are an abstract version of color, with each channel representing some aspect of information about the image.

<p align = 'center'>
            <img src = Images/Channels_Concept.gif/>
</p>

<h1 align = 'center' id = "RF"> RECEPTIVE FIELD </h1>

`The Receptive Field (RF) is defined as the size of the region in the input that produces the feature. Basically, it is a measure of association of an output feature (of any layer) to the input region (patch).`

    Insight: The idea of receptive fields applies to local operations (i.e. convolution, pooling).

<p align = 'center'>
            <img src = Images/RF.gif/>
</p>

A convolutional unit only depends on a local region (patch) of the input. That’s why we never refer to the RF on fully connected layers since each unit has access to all the input region.

