# Assignment: 

## 1.What are Channels and Kernels?

### Channels :
                                          CHANNELS = SIMILAR_FEATURE_BAGS
                                               
 - **`The Above Image contains all the Alphabets. In that the single 'a' is a Feature and Collection of all the 'a's is called "Feature Map" a.k.a "Channel".`**
 
 - Collection of Channels is Mapping to get Entire Image.
 
 - An image is not just about colors, but we can divide into simpler components (like edges, gradients, textures, patterns, part of objects, objects, etc). And each channel we can consider as an Individual Channel.
 
### Kernels :
                                           KERNEL = FEATURE_EXTRACTOR
                                         
   - **`A Kernel will change the value of any given pixel in the Image by combining it with different amounts of the neighboring pixels. The kernel is applied to every pixel in the image one-by-one to produce the final image.`**
     
        **Kernel = filters the Image**
     
## 2.Why should we only (well mostly) use 3x3 Kernels?

We will use Every time 3x3 kernel because :<br>
     
   - The 3x3 is odd and can't use even kernel because we may miss the **Access of Symmetry** in the Image and results to lose of Information.<br>
          
   - And then there are many odd why too 3x3 and why not 1x1 or 5x5? <br>
          
             Because 3x3 is collection of 1x1 's and also there will be more output layers when using 1x1 filters more memory will be required to store them as compared to 3x3 filters.
                    
             Now, 5x5 is nothing but 2 times of 3x3 filter.When we work with smaller filters, we focus on every minute details and capture smaller complex features from the Image, where as when we work with larger filters we tends to search for generic features which will give us basic components. 

## 3. How many times do we need to perform 3x3 convolution operation to reach 1x1 from 199x199 (showing calculations)

**Here, to reach from 199x199 to 1x1 with the 3x3 convolution operations are performed.**

<ol>
  <li> 199x199 | 3x3 > 197x197 </li><br>
  <li>197x197 | 3x3 > 195x195 </li><br>
  <li>195x195 | 3x3 > 193x193 </li><br>
  <li>193x193 | 3x3 > 191x191 </li><br>
  <li>191x191 | 3x3 > 189x189 </li><br>
  <li>189x189 | 3x3 > 187x187 </li><br>
  <li>187x187 | 3x3 > 185x185 </li><br>
  <li>185x185 | 3x3 > 183x183 </li><br>
  <li>183x183 | 3x3 > 181x181 </li><br>
  <li>181x181 | 3x3 > 179x179 </li><br>
  <li>179x179 | 3x3 > 177x177 </li><br>
  <li>177x177 | 3x3 > 175x175 </li><br>
  <li>175x175 | 3x3 > 173x173 </li><br>
  <li>173x173 | 3x3 > 171x171 </li><br>
  <li>171x171 | 3x3 > 169x169 </li><br>
  <li>169x169 | 3x3 > 167x167 </li><br>
  <li>167x167 | 3x3 > 165x165 </li><br>
  <li>165x165 | 3x3 > 163x163 </li><br>
  <li>163x163 | 3x3 > 161x161 </li><br>
  <li>161x161 | 3x3 > 159x159 </li><br>
  <li>159x159 | 3x3 > 157x157 </li><br>
  <li>157x157 | 3x3 > 155x155 </li><br>
  <li>155x155 | 3x3 > 153x153 </li><br>
  <li>153x153 | 3x3 > 151x151 </li><br>
  <li>151x151 | 3x3 > 149x149 </li><br>
  <li>149x149 | 3x3 > 147x147 </li><br>
  <li>147x147 | 3x3 > 145x145 </li><br>
  <li>145x145 | 3x3 > 143x143 </li><br>
  <li>143x143 | 3x3 > 141x141 </li><br>
  <li>141x141 | 3x3 > 139x139 </li><br>
  <li>139x139 | 3x3 > 137x137 </li><br>
  <li>137x137 | 3x3 > 135x135 </li><br>
  <li>135x135 | 3x3 > 133x133 </li><br>
  <li>133x133 | 3x3 > 131x131 </li><br>
  <li>131x131 | 3x3 > 129x129 </li><br>
  <li>129x129 | 3x3 > 127x127 </li><br>
  <li>127x127 | 3x3 > 125x125 </li><br>
  <li>125x125 | 3x3 > 123x123 </li><br>
  <li>123x123 | 3x3 > 121x121 </li><br>
  <li>121x121 | 3x3 > 119x119 </li><br>
  <li>119x119 | 3x3 > 117x117 </li><br>
  <li>117x117 | 3x3 > 115x115 </li><br>
  <li>115x115 | 3x3 > 113x113 </li><br>
  <li>113x113 | 3x3 > 111x111 </li><br>
  <li>111x111 | 3x3 > 109x109 </li><br>
  <li>109x109 | 3x3 > 107x107 </li><br>
  <li>107x107 | 3x3 > 105x105 </li><br>
  <li>105x105 | 3x3 > 103x103 </li><br>
  <li>103x103 | 3x3 > 101x101 </li><br>
  <li>101x101 | 3x3 > 99x99 </li><br>
  <li> 99x99 | 3x3 > 97x97 </li><br>
  <li>97x97 | 3x3 > 95x95 </li><br>
  <li>95x95 | 3x3 > 93x93 </li><br>
  <li>93x93 | 3x3 > 91x91 </li><br>
  <li>91x91 | 3x3 > 89x89 </li><br>
  <li>89x89 | 3x3 > 87x87 </li><br>
  <li>87x87 | 3x3 > 85x85 </li><br>
  <li>85x85 | 3x3 > 83x83 </li><br>
  <li>83x83 | 3x3 > 81x81 </li><br>
  <li>81x81 | 3x3 > 79x79 </li><br> 
  <li> 79x79 | 3x3 > 77x77 </li><br>
  <li>77x77 | 3x3 > 75x75 </li><br>
  <li>75x75 | 3x3 > 73x73 </li><br>
  <li>73x73 | 3x3 > 71x71 </li><br>
  <li>71x71 | 3x3 > 69x69 </li><br>
  <li>69x69 | 3x3 > 67x67 </li><br>
  <li>67x67 | 3x3 > 65x65 </li><br>
  <li>65x65 | 3x3 > 63x63 </li><br>
  <li>63x63 | 3x3 > 61x61 </li><br>
  <li>61x61 | 3x3 > 59x59 </li><br>
  <li> 59x59 | 3x3 > 57x57 </li><br>
  <li>57x57 | 3x3 > 55x55 </li><br>
  <li>55x55 | 3x3 > 53x53 </li><br>
  <li>53x53 | 3x3 > 51x51 </li><br>
  <li>51x51 | 3x3 > 49x49 </li><br>
  <li>49x49 | 3x3 > 47x47 </li><br>
  <li>47x47 | 3x3 > 45x45 </li><br>
  <li>45x45 | 3x3 > 43x43 </li><br>
  <li>43x43 | 3x3 > 41x41 </li><br>
  <li>41x41 | 3x3 > 39x39 </li><br>
  <li> 39x39 | 3x3 > 37x37 </li><br>
  <li> 37x37 | 3x3 > 35x35 </li><br>
  <li> 35x35 | 3x3 > 33x33 </li><br>
  <li> 33x33 | 3x3 > 31x31 </li><br>
  <li> 31x31 | 3x3 > 29x29 </li><br>
  <li>29x29 | 3x3 > 27x27 </li><br>
  <li>27x27 | 3x3 > 25x25 </li><br>
  <li>25x25 | 3x3 > 23x23 </li><br>
  <li>23x23 | 3x3 > 21x21 </li><br>
  <li>21x21 | 3x3 > 19x19 </li><br>
  <li>19x19 | 3x3 > 17x17 </li><br>
  <li>17x17 | 3x3 > 15x15 </li><br>
  <li>15x15 | 3x3 > 13x13 </li><br>
  <li>13x13 | 3x3 > 11x11 </li><br>
  <li>11x11 | 3x3 > 9x9 </li><br>
  <li>9x9 | 3x3 > 7x7 </li><br>
  <li>7x7 | 3x3 > 5x5 </li><br>
  <li>5x5 | 3x3 > 3x3 </li><br>
  <li>3x3 | 3x3 > 1x1 </li><br>
</ol>
