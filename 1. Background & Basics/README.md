## BACKGROUND & BASICS
  
### HUMAN EYE INTUITION

- *Everything w.r.t vision starts with our eyes. The eye is our vision sensor and similar to our eyes, we have the camera sensor, which reacts to the light based on the amplitude of the wavelength falling over it.*

<h3 align="center"> Understanding From Human EYE Anatomy </h3>

<p align = 'center'>
            <img src = Images/Anatomy_of_Eye.jpeg width="700" height="400"/>
</p>

<h3 align="center"> Here is how our physical camera systems look  </h3>
 
 <p align = 'center'>
            <img src = Images/Anatomy_of_Camera.jpeg width="700" height="400"/>
</p>

### This is how our retina would look under the electron microscope:

 <p align = 'center'>
            <img src = Images/View_Conversion_EYE.jpeg width="700" height="400"/>
</p>

- ***`This is where what we see gets converted into RGB or Black n White.`***

As you are aware, we have 3 channels (they are not purely RGB though) and this is how our camera sensor would look under the electron-microscope:

<p align = 'center'>
            <img src = Images/Camera_under_Microscope.jpeg width="700" height="400"/>
</p>

<h1 align='center'> CHANNELS </h1>

We need to start to think about channels in a different manner now.

### Channels :
                                          CHANNELS = SIMILAR_FEATURE_BAGS
                                          
<p align = 'center'>
            <img src = Images/collection_of_text.png width="800" height="500"/>
</p>
     
 - **`The Above Image contains all the Alphabets. In that the single 'a' is a Feature and Collection of all the 'a's is called "Feature Map" a.k.a "Channel".`**
 
 - Collection of Channels is Mapping to get Entire Image.
 
 - An image is not just about colors, but we can divide into simpler components (like edges, gradients, textures, patterns, part of objects, objects, etc). And each channel we can consider as an Individual Channel.
 
### Kernels :
                                           KERNEL = FEATURE_EXTRACTOR
                                         
   - **`A Kernel will change the value of any given pixel in the Image by combining it with different amounts of the neighboring pixels. The kernel is applied to every pixel in the image one-by-one to produce the final image.`**
     
        **Kernel = filters the Image**
        
        
### If we are focusing on CHANNELS then what would be "one" of the possible channel sets in the song being played below:

<p align = 'center'>
            <img src = Images/Music_Band_Channels.jpeg width="700" height="400"/>
</p>

- `When we think in terms of channels, you can split the song being played above in its individual components, like the sound made by piano, guitar, bass, drum, etc`

<h1 align='center'> NEURAL COMPUTING </h1>

    We need feature extraction methods and then combining methods

<p align = 'center'>
            <img src = Images/Neural_Layers.png width="700" height="400"/>
</p>

- We start simple, but then we can mix those simple building blocks and build something very beautiful and elegant!

<p align = 'center'>
            <img src = Images/Layers_of_Image.png width="700" height="400"/>
</p>


- `The connection to remember that very complex things can be built from simple strokes like we can make stories from only 26 alphabets.` 
