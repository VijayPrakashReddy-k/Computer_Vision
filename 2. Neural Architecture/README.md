### CONVOLUTIONS:

Here we see a 3x3 kernel convolving on an image/channel of size 4x4. 

Every purple pixel we see represents a value, so in total, we are looking at 16 values. These values are generated from the image on which we are convolving, so we have no control over them. 

 

The dark purple 3x3 moving box is our kernel. We initialize it (and all other kernels) randomly. We do have control over the values in the kernel, and that is what we want we (backpropagation) would be changing, such that they become the feature extractor (like a vertical edge detector). 

 

Whenever our kernel is stopping, we are looking at 9 multiplications, we then sum all these 9 values, and pass the sum to the green channel. This green channel is called an output channel. 

 

Whenever we perform a convolution with 3x3 kernel on an image of 4x4 in size, the output channel would have a resolution of 2x2. We essentially lose 2 pixels in x as well as the y-axis. 
  

Convolving a 3x3 channel on 5x5
 

Similarly, if we convolve a 3x3 kernel on a 5x5 image, the output channel we would create will have a resolution of 3x3. This is true only in the case when:

we are not using any padding (we are not adding additional 0s (what else can we add?) on the boundaries of our input image, changing its resolution, say from 5x5 to 7x7), and
we are not using a stride of more than 1. 
In the images above, you see, that whenever the kernel moves, it skips just 1 pixel. If it were to skip 2 pixels, that would be called a stride of 2. 
