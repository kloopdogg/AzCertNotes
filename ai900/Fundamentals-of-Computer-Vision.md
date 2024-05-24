# Computer Vision
Computer vision is one of the core areas of artificial intelligence (AI), and focuses on creating solutions that **enable AI applications to "see" the world and make sense of it**.

> An image is an array of numeric pixel values. A single layer of pixel values like this represents a grayscale image. Most digital images are multidimensional and consist of three layers (known as channels) that represent red, green, and blue (RGB) color hues. 

## Using filters to process images
A common way to perform image processing tasks is to **apply filters** that modify the pixel values of the image to create a visual effect. A filter is defined by **one or more arrays of pixel values, called filter kernels**.

![Filter to process images](../assets/ai900/filter-kernel.gif "Filter kernel applied to pixel patches")
The resulting array represents a new image in which the filter has transformed the original image. In this case, the filter has had the effect of **highlighting the edges of shapes** in the image.

Because the filter is convolved across the image, this kind of image manipulation is often referred to as `convolutional filtering`. The filter used in this example is a particular type of filter (called a `laplace filter`) that highlights the edges on objects in an image.

**Goal of computer vision** is often to extract meaning, or at least actionable insights, from images; which requires the **creation of machine learning models** that are trained to recognize features based on large volumes of existing images.

## Convolutional neural networks (CNNs)
CNNs use **filters to extract numeric feature maps** from images, and then **feed the feature values into a deep learning model to generate a label prediction**. 

> The name **convolutional** comes from the key operation in the network called convolution. It’s a mathematical way of combining two sets of information. In the case of CNNs, it’s used to blend the pixels of the image with the filters to find patterns

### What makes a system a neural network?
A CNN's structure and functionality are inspired by the human brain’s neural networks. Here are the key characteristics:
- **Layers of Neurons:** \
Neural networks consist of layers of interconnected nodes or ‘neurons’, each of which performs a simple computation. In CNNs, these layers are specialized to perform tasks such as convolution and pooling.
- **Connection Weights:** \
Each connection between neurons has an associated weight, which is adjusted during training. This is akin to how synaptic strengths are adjusted in the biological brain.
- **Activation Functions:** \
Neurons use activation functions to introduce non-linearities into the network, allowing it to learn complex patterns. Common functions include ReLU, sigmoid, and tanh.
- **Learning Ability:** \
Neural networks learn to perform tasks by considering examples, generally without task-specific programming. For CNNs, this often involves learning to recognize visual patterns.
- **Backpropagation:** \
This is a method used to train neural networks, where gradients are calculated and used to update the weights, minimizing the difference between the actual and predicted outputs.
- **Generalization:** \
After training, a neural network can generalize from the examples it has seen to make predictions about unseen data, which is a hallmark of intelligent behavior.

These components work together to process input data, learn from it, and make predictions or classifications, which is why CNNs are a powerful tool in the field of AI, particularly in image recognition tasks within Azure AI services.

### How does it work?
![Image classification model](../assets/ai900/convolutional-neural-network.png "CNN image classification model")

1. Images with **known labels** are fed in to train the model.
2. **Layers of filters** are used to extract features from each image. The filter kernels start with randomly assigned weights and generate arrays of numeric values called **feature maps**.
3. The feature maps are flattened into a single dimensional array of **feature values**.
4. The feature values are fed into a fully connected neural network.
5. The output layer of the neural network uses a **softmax**, or similar function, to produce a result that contains a probability value for each possible class (e.g., [0.2, 0.5, 0.3]).

#### During Training
1. Output probabilities are compared to the actual class label.
1. Difference between the predicted and actual class scores is used to calculate the loss in the model.
1. Weights,in the neural network and the filter kernels, are modified to reduce the loss.
1. Process repeats over multiple **epochs** until an optimal set of weights has been learned. 

## Transformers and multi-modal models
CNNs are also the basis for more complex computer vision models. **Object detection models** combine CNN feature extraction layers with the identification of regions of interest in images to locate multiple classes of object in the same image.

## Transformers
Natural language processing (NLP) is another type of neural network architecture, called a transformer. It has enabled the development of sophisticated models for language.

Transformers work by `processing huge volumes of data`, and `encoding language tokens` (representing individual words or phrases) as `vector-based embeddings` (arrays of numeric values). The embeddings are created such that tokens that are commonly used in the same context are closer together dimensionally than unrelated words.

### Multi-modal models
Multi-modal models are trained using a large volume of captioned images, with no fixed labels. An image encoder extracts features from images and combines them with text embeddings created by a language encoder. The overall model encapsulates relationships between natural language token embeddings and image features.


![Multi-modal models](../assets/ai900/multi-modal-model.png "Multi-modal models")

### Florence
**Microsoft's Florence model** is trained with huge volumes of captioned images from the Internet. It includes both a language encoder and an image encoder. Florence is a foundation model. 

> **Foundational Model**: a pre-trained general model on which you can build multiple adaptive models for specialist tasks. 

Florence can be used as a foundation model for adaptive models that perform:

- **Image classification:** Identifying to which category an image belongs.
- **Object detection:** Locating individual objects within an image.
- **Captioning:** Generating appropriate descriptions of images.
- **Tagging:** Compiling a list of relevant text tags for an image.

## Azure AI Vision
Azure AI Vision service provides prebuilt and customizable computer vision models, based on Florence foundation model, and provide various powerful capabilities.

### AI Vision Capabilities
Azure AI Vision supports multiple image analysis capabilities, including:

- **Optical character recognition (OCR)** - extracting text from images.
- **Generating captions** and descriptions of images.
- **Detection** of thousands of common objects in images.
- **Tagging** visual features in images

### Training custom models
You can use the service to train a custom model for image classification or object detection. Training sophisticated models can be done using relatively few training images.
