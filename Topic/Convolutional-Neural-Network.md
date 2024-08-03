A convolutional neural network (CNN) is a regularized type of feed-forward neural network that learns features 
by itself via filter (or kernel) optimization. Vanishing gradients and exploding gradients, 
seen during backpropagation in earlier neural networks, are prevented by using regularized weights over fewer connections. 
For example, for each neuron in the fully-connected layer, 10,000 weights would be required for processing an image sized 100 × 100 pixels.  
However, applying cascaded convolution (or cross-correlation) kernels, only 25 neurons are required to process 5x5-sized tiles.  
Higher-layer features are extracted from wider context windows, compared to lower-layer features.  

Feed-forward neural networks are usually fully connected networks, that is, each neuron in one layer is connected to all neurons in the next layer. 
The "full connectivity" of these networks makes them prone to overfitting data. Typical ways of regularization, or preventing overfitting, 
include: penalizing parameters during training (such as weight decay) or trimming connectivity (skipped connections, dropout, etc.) 
Robust datasets also increase the probability that CNNs will learn the generalized principles that characterize a given dataset rather than the biases of a poorly-populated set.
