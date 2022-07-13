## HOW DO WE GET 5x5 RF WITH 1 3x3 KERNEL?

<h1 align = 'center' id = "atrous"> ATROUS OR DILATED CONVOLUTIONS </h1>

We get a receptive field of 3x3 when we convolve by 3x3.

***What should we do to get a receptive field of 5x5 when we convolve by 3x3?***
      

- Dilated convolution is a way of increasing the receptive view (global view) of the network exponentially and linear parameter accretion. With this purpose, it finds usage in applications cares more about integrating the knowledge of the wider context with less cost.

- The key application the dilated convolution authors have in mind is a *dense prediction: vision applications where the predicted object has a similar size and structure to the input image.*

**For example, semantic segmentation with one label per pixel, image super-resolution, denoising, demosaicing, bottom-up saliency, keypoint detection, etc.**

In many such applications one wants to integrate information from different spatial scales and balance two properties:

     1. Local, pixel-level accuracy, such as precise detection of edges, and

     2. Integrating the knowledge of the wider, global context


<p align = 'center'>
            <img src = Images/Atrous_or_Dilated_Convolutions.gif/>
</p>

<h1 align = 'center'> Dilation </h1>

<p align = 'center'>
            <img src = Images/Dilation.webp/>
</p>

<h1 align = 'center'> Atrous Convolutions Architecture </h1>

Deeper with Atrous Convolutions
<p align = 'center'>
            <img src = Images/Atrous_Architecture.png/>
</p>

<h1 align = 'center' id="dense-problem"> "DENSE" PROBLEMS </h1>

<p align = 'center'>
            <img src = Images/Segmentation_dense.png/>
</p>

*What is the above output?*    ***"Dense"***

**The Problem: "convolution is a rather local operation"**
 
Improving the resolution of segmentation results. **Dilated convolutions or atrous convolutions present a potential solution to this problem:**

   - `They are capable of capturing global context without reducing the resolution of the segmentation map.`

Normal convolutional neural networks (CNNs) are based on the fact that each convolutional layer collects information from a larger neighborhood around each pixel/voxel.This means that in the upper layers of the network, each pixel of a feature map could potentially hold information about a large region of the image.

However, experiments show that during learning this is usually not the case. Rather, the information in each pixel stays [localized](References/Information_in_each_pixel_stays_localized.pdf) and the network “does not live up to its full potential”. Dilated convolutions change the rules of the game by using kernels of the same size as normal convolutional layers but spread out over a larger area on the image.


## HOW DO WE INCREASE CHANNEL SIZE AFTER CONVOLUTION

<h1 align = 'center' id="transpose"> DECONVOLUTION  or FRACTIONALLY STRIDED </h1>

### OR
<h1 align = 'center'> TRANSPOSE CONVOLUTION </h1>

We have a kernel of size 3x3. If we convolve on 5x5 we get 3x3.

What do we do to get 7x7? Or get a larger channel size than we started with? 

A simple approach, but inefficient. 

<p align = 'center'>
            <img src = Images/simple_approach.gif/>
</p>

De-convolution (or Transpose Convolution) is a  Better approach, but..

<p align = 'center'>
            <img src = Images/De-Convolution_Transpose_Convolutions.gif/>
</p>

- ***`It introduces the checkerboard issue!`***

<p align = 'center'>
            <img src = Images/Perceptual_Losses.png/>
</p>

<h1 align = 'center' id="pixel"> PIXEL SHUFFLE  </h1>

<p align = 'center'>
            <img src = Images/Pixel_Shuffle.gif/>
</p>

[Jeremy Howard's Explanation](https://www.youtube.com/embed/nG3tT31nPmQ?start=2128)

[Pixel Shuffle Paper](References/Pixel_Shuffle.pdf)
