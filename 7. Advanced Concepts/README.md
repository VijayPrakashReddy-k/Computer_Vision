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

<h1 align = 'center',style="color:Tomato;",id = "convolution"> Convolution</h1>

**What is Convolution?**

    ⊛ The process of extracting features from input data using kernels/filters.
    
    ⊛ Filter moves discretely on top of the data-plane/channel, scale the input data equal to the size of its receptive field sums
    these results and creates a new feature map.

<h1 align = 'left'>Normal Convolutions</h1>
