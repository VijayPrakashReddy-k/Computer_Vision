## 7 - ADVANCED CONCEPTS

*Advance Convolutions, Attention and Image Augmentation: Depthwise, Pixel Shuffle, Dilated, Transpose, Channel Attention, and Albumentations Library*

**Contents:**

- [Convolution](./README.md/#convolution)

- [Pointwise Convolutions](./README.md/#PC)

- [Concept of Channels](./README.md/#channels)

- [Receptive Field](./README.md/#RF)

- [Checkerboard Issue](./README.md/#issue)

- [Atrous or Dilated Convolutions](./CONTENT.md/#atrous)

- [Dense Problems](./CONTENT.md/#dense-problem)

- [Deconvolutions or Transpose Convolutions](./CONTENT.md/#transpose)

- [Pixel Shuffle Algorithm (SKIPPED)](./CONTENT.md/#pixel)

- [Depthwise Separable Convolution](./README.md/#depthwise)

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

<br>
<h1 align = 'center' id = "issue">  CHECKERBOARD ISSUE </h1>

<p align = 'center'>
            <img src = Images/CheckerBoard_Issue.png/>
</p>

- Mysteriously, the checkerboard pattern tends to be most prominent in images with strong colors. What’s going on? Do neural networks hate bright colors? The actual cause of these artifacts is actually remarkably simple, as is a method for avoiding them.

<br>
<p align = 'center'>
            <img src = Images/CheckerBoard_Solution.gif/>
</p>

<br>
<h1 align = 'center' id = "depthwise">  DEPTHWISE SEPARABLE CONVOLUTION </h1>

What is wrong with this convolution?

<p align = 'center'>
            <img src = Images/Separable_Convolutions.gif/>
</p>

### DEPTHWISE SEPARABLE CONVOLUTION

<p align = 'center'>
            <img src = Images/Depthwise_Separable_Convolution.png/>
</p>

<p align = 'center'>
            <img src = Images/Depthwise_Separable.gif/>
</p>

[Reference](https://eli.thegreenplace.net/2018/depthwise-separable-convolutions-for-machine-learning/)

For a depthwise separable convolution on the same example, we traverse the 16 channels with 1 3x3 kernel each, giving us 16 feature maps. Now, before merging anything, we traverse these 16 feature maps with 32 1x1 convolutions each and only then start to them add together.

- `This results in 656 (16x3x3 + 16x32x1x1) parameters opposed to the 4608 (16x32x3x3) parameters from above.`

<h1 align = 'center' id = "depthwise">  SPATIALLY SEPARABLE CONVOLUTION </h1>

- `SPATIALLY SEPARABLE CONVOLUTION Was  used immensely in different variants of Xception-Incepeption Networks as well as the MobileNet.`

<p align = 'center'>
            <img src = Images/Spatially_Separable_Convolution.gif/>
</p>

<h1 align = 'center' id = "grouped">  GROUPED CONVOLUTION </h1>

Grouped convolutions were initially mentioned in AlexNet and later reused in ResNext. The main motivation of such convolutions is to reduce computational complexity while dividing features into groups.

<p align = 'center'>
            <img src = Images/Spatially_Separable_Convolution.gif/>
</p>

<p align = 'center'>
            <img src = Images/Spatially_Separable_Convolution.gif/>
</p>
