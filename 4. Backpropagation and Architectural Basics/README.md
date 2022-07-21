## 4 - Backpropagation and Architectural Basics

*Architectural Basics: We go through 9 model iterations together, step-by-step to find the final architecture*

**Contents:**

- [BACK PROPAGATION](./README.md/#backpropagation)

- [FULLY CONNECTED LAYERS](./README.md/#FCL)

- [VGG - LAST AWESOME OLD ARCHITECTURE - PRE 2014](./README.md/#VGG)

- [MODERN ARCHITECTURE - POST 2014](./README.md/#resnet)

- [SOFTMAX](./README.md/#softmax)

- [ARCHITECTURAL BLOCKS](./README.md/#architecture)

      1. MAXPOOLING
      
      2. BATCH NORMALIZATION
      
      3. DROPOUT
      
      4. LEARNING RATE
      
      5. BATCH SIZE


<h1 align = 'center' id = "backpropagation"> BACKPROPAGATION</h1>

- `Neural networks come in many forms, but the main form we need to master is that of "fully connected layers".  A network with many such (or other) layers is called "deep".`

Let's look at a very simple neural network.

<p align = 'center'>
            <img src = Images/simple_perceptron_model.png width="900" height="400"/>
</p>

Let's make sure we talk about the Error and path small errors are taking to finally get accumulated at *E_Total.*

What is that σ doing there?

[Activation_Function](https://www.analyticssteps.com/blogs/7-types-activation-functions-neural-network)

`A linear activation function has two major problems:`

- 1. Not possible to use backpropagation (gradient descent) to train the model—the derivative of the function is a constant and has no relation to the input, X. So it’s not possible to go back and understand which weights in the input neurons can provide a better prediction.

- 2. All layers of the neural network collapse into one—with linear activation functions, no matter how many layers in the neural network, the last layer will be a linear function of the first layer (because a linear combination of linear functions is still a linear function). So a linear activation function turns the neural network into just one layer.

That is why we need activation functions (other than just linear).

-----------------------------------------------------------------------

---
Input	Weight	
Tem Out
No Act	ReLU	
Sigmoid
Tanh							
0.000	0.608	0.000	0.000				0.000	0.500	0.000				
-0.085		-0.052	-0.052	0.000	0.513	-0.052							
0.252		0.153	0.153				0.153	0.462	0.152				
4.566		2.777	2.777				2.777	0.059	0.992				
-2.888		-1.756	-1.756	0.000	0.853	-0.942							
3.146		1.914	1.914				1.914	0.129	0.957				
-1.421		-0.864	-0.864	0.000	0.704	-0.698							
0.408		0.248	0.248	                  0.248	0.438	 0.243							
-1.049		-0.638	-0.638	0.000	0.654	-0.563							
-0.576		-0.350	-0.350	0.000	0.587	-0.336							
-1.213		-0.738	-0.738	0.000	0.677	-0.628							
-6.948		-4.226	-4.226	0.000	0.986	-1.000							
-3.663		-2.228	-2.228	0.000	0.903	-0.977							
5.557		3.380	3.380	                  3.380	0.033	 0.998							
1.694		1.030	1.030	                  1.030	0.263	 0.774							
1.310		0.797	0.797	                  0.797	0.311	 0.662

Input: 0.000 -0.085 0.252 4.566 -2.888 3.146 -1.421 0.408 -1.049 -0.576 -1.213 -6.948 -3.663 5.557 1.694 1.310
Weight: 0.608
Tem Out: 0.350 0.237 0.0471.886 -0.120 -0.416 0.454 0.331 0.000 -0.374	-4.306 -1.822 0.995 0.000 0.628 0.512
No Activation: 

Weight TemOut NoAct ReLU Sigmoid Tanh
---
