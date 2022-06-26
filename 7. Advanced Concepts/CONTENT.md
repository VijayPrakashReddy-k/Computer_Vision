## ATROUS OR DILATED CONVOLUTIONS

#### HOW DO WE GET 5x5 RF WITH 1 3x3 KERNEL?

We get a receptive field of 3x3 when we convolve by 3x3.

      What should we do to get a receptive field of 5x5 when we convolve by 3x3?
      

- `Dilated convolution is a way of increasing the receptive view (global view) of the network exponentially and linear parameter accretion. With this purpose, it finds usage in applications cares more about integrating the knowledge of the wider context with less cost.`

- The key application the dilated convolution authors have in mind is a *dense prediction: vision applications where the predicted object has a similar size and structure to the input image.*

**For example, semantic segmentation with one label per pixel, image super-resolution, denoising, demosaicing, bottom-up saliency, keypoint detection, etc.**

In many such applications one wants to integrate information from different spatial scales and balance two properties:

     1. Local, pixel-level accuracy, such as precise detection of edges, and

     2. Integrating the knowledge of the wider, global context
