# Convolutional Neural Networks (CNNs)

Convolutional Neural Networks (CNNs) are a class of deep learning models specifically designed for processing structured grid data, such as images. CNNs are particularly effective in computer vision tasks like image classification, object detection, and segmentation.

## Key Concepts

### 1. Convolution Operation

The core building block of CNNs is the convolution operation, which involves sliding a filter (or kernel) across the input data to produce feature maps. This operation captures local patterns(edges) in the data.

**Mathematical Representation:**
$$
\text{Output}(i,j) = \sum_m \sum_n \text{Input}(i+m, j+n) \cdot \text{Filter}(m,n)
$$

### 2. Activation Function

After the convolution operation, an activation function is applied to introduce non-linearity into the model. The most commonly used activation function in CNNs is the ReLU (Rectified Linear Unit):

$$
\text{ReLU}(x) = \max(0, x)
$$

### 3. Pooling Layers

Pooling layers reduce the spatial dimensions of the feature maps, which helps decrease computational load and control overfitting. The most common type of pooling is max pooling, which takes the maximum value in each region of the feature map.

**Max Pooling Operation:**
$$
\text{Output}(i,j) = \max \{\text{Input}(m,n) | (m,n) \in \text{Region}\}
$$

### 4. Fully Connected Layers

After several convolutional and pooling layers, the high-level reasoning in the neural network is done through fully connected layers. These layers connect every neuron in one layer to every neuron in the next layer.

## Architecture of CNNs

A typical CNN architecture consists of the following layers:

1. **Input Layer**: Takes in the raw pixel values of the image.
2. **Convolutional Layers**: Extract features from the input image using filters.
3. **Activation Layers**: Apply non-linearity (e.g., ReLU).
4. **Pooling Layers**: Downsample the feature maps.
5. **Fully Connected Layers**: Classify the features extracted by the convolutional layers.
6. **Output Layer**: Produces the final predictions (e.g., class scores).

# Convolutional Neural Network (CNN) Structure

## 1. Convolutional Layer

The **Convolutional Layer** is the core building block of a CNN. It applies filters (kernels) to the input image to detect patterns such as edges, textures, or specific features.

### Convolution Operation
- The **convolution operation** involves sliding a filter (kernel) over the input image and computing the dot product between the filter and the image region.
- The output of the convolution operation is called a **feature map** or **activation map**.
- The size of the filter is typically smaller than the input image, allowing the network to learn spatial hierarchies.

#### Example
For a 3x3 filter sliding over a 5x5 input:
- The filter moves over different regions of the input image, computing the dot product at each position.
- This process extracts local features from the input.

## 2. Padding

**Padding** is used to control the spatial dimensions of the output feature map.
- It adds extra pixels (usually zeros) around the input image to preserve the original dimensions or prevent shrinking.

### Types of Padding
- **Valid Padding**: No padding, resulting in a smaller output size.
- **Same Padding**: Padding added such that the output size is the same as the input size.

## 3. Strides

**Strides** refer to the number of pixels by which the filter moves at each step during the convolution operation.
- **Stride of 1**: The filter moves one pixel at a time.
- **Stride of 2 or more**: The filter moves two or more pixels at each step, reducing the output dimensions.

## 4. Pooling Layer

The **Pooling Layer** is used to down-sample the feature map, reducing its spatial dimensions and the amount of computation.
- It helps in making the network invariant to small translations of the input image.

### Types of Pooling
- **Max Pooling**: Takes the maximum value from a region of the feature map.
- **Average Pooling**: Takes the average value from a region of the feature map.

#### Pooling Example
For a 2x2 max pooling over a 4x4 feature map:
- The output will be a 2x2 matrix where each element is the maximum value from the corresponding 2x2 region in the original feature map.

## 5. Fully Connected Layer

After several convolutional and pooling layers, the output is typically flattened and passed through one or more **fully connected layers**.
- The fully connected layers perform classification based on the learned features.

## Summary of Key Concepts

| Concept             | Description                                                  |
|---------------------|--------------------------------------------------------------|
| Convolution Layer   | Applies filters to extract features from the input image     |
| Convolution Operation | Dot product between filter and image region                 |
| Padding             | Adds extra pixels around the input to control output size    |
| Strides             | The step size of the filter during convolution               |
| Pooling Layer       | Reduces spatial dimensions by down-sampling the feature map  |
| Fully Connected Layer | Classifies the final output based on learned features       |


## Advantages of CNNs

- **Hierarchical Feature Learning**: CNNs automatically learn spatial hierarchies of features from low-level edges to high-level concepts.
- **Parameter Sharing**: Convolutional layers use the same filter across the input, reducing the number of parameters and computational cost.
- **Translation Invariance**: CNNs are effective at recognizing objects in images regardless of their position.

## Applications of CNNs

- **Image Classification**: Identifying the class of an image (e.g., cats vs. dogs).
- **Object Detection**: Locating and classifying multiple objects within an image.
- **Image Segmentation**: Partitioning an image into meaningful regions for analysis.
- **Facial Recognition**: Identifying and verifying individuals in images. 
