# Recurrent Neural Networks (RNN) 
A **Recurrent Neural Network (RNN)** is a type of ANN (artificial neural network) designed to recognize *patterns in sequential* data by maintaining a "**memory**" of *previous inputs*. It processes inputs one at a time, with each output influenced not only by the current input but also by information from previous time steps, enabling it to capture temporal dependencies in data such as time-series, text, or speech.
## Structure of RNN
![image](https://github.com/user-attachments/assets/142ce791-4cb9-418e-b81c-dfdda087ac65)

| Component            | Description                                                                 |
|----------------------|-----------------------------------------------------------------------------|
| Input Layer          | Takes a sequence of inputs (e.g., time series data, text).                  |
| Hidden Layer (state) | Processes each input sequentially and maintains a hidden state.             |
| Output Layer         | Produces an output for each time step or the final time step.               |
| Feedback Loop        | The hidden state at time `t` is fed back as input for the next time step.   |

## Types of RNN
| Type                | Description                                                                 |
|---------------------|-----------------------------------------------------------------------------|
| Vanilla RNN         | Basic RNN structure with one hidden layer. Prone to vanishing gradient issue.|
| Long Short-Term Memory (LSTM) | RNN with special units (memory cells) to capture long-term dependencies.|
| Gated Recurrent Unit (GRU)    | Simplified version of LSTM, using fewer parameters.                |
| Bidirectional RNN   | Processes sequences in both forward and backward directions.                 |
| Echo State Network (ESN) | Uses random fixed weights for hidden layers; trains only output weights.|
## RNN Architectures based on the relationship between input and output sequences

## One to Many
- **Definition**: An RNN structure that takes a single input and produces a sequence of outputs.
- **Applications**:
  - **Text Generation**: Generating sentences word by word based on an initial prompt.
  - **Music Composition**: Creating musical notes from a single starting note or melody.
  - **Image Captioning**: Generating a sequence of words to describe the content of an image.

## Many to One
- **Definition**: An RNN structure that takes a sequence of inputs and produces a single output.
- **Applications**:
  - **Text Classification**: Classifying a sentence or document as positive, negative, or neutral.
  - **Sentiment Analysis**: Determining the sentiment expressed in a piece of text.
  - **Fraud Detection**: Analyzing sequences of transactions to classify whether they are fraudulent.
## Many to Many
- **Definition**: An RNN structure that takes a sequence of inputs and produces a sequence of outputs.
- **Applications**:
  - **Machine Translation**: Translating sentences from one language to another word by word.
  - **Video Captioning**: Generating a sequence of captions for a video based on its frames.
  - **Dialogue Systems**: Producing a sequence of responses in a conversation based on user input.

## RNN vs. ANN vs. CNN
| Feature                        | RNN                                        | ANN                        | CNN                           |
|--------------------------------|--------------------------------------------|----------------------------|-------------------------------|
| Data Type                      | Sequential data (e.g., text, time series)  | Structured data             | Image, spatial data            |
| Memory                         | Maintains memory across time steps         | No memory                   | Limited receptive field        |
| Weight Sharing                 | Across time steps                          | No weight sharing           | Across spatial locations       |
| Handling Long Dependencies     | Difficult for vanilla RNNs (better with LSTM/GRU) | Not suitable               | Not designed for sequential data|
| Typical Use Cases              | Language modeling, speech recognition      | Classification, regression  | Image recognition, object detection|

## Advantages and Disadvantages of RNN
| Aspect          | Advantages                                      | Disadvantages                                 |
|-----------------|-------------------------------------------------|-----------------------------------------------|
| Learning        | Learns from sequential data, captures context   | Prone to vanishing/exploding gradient problem |
| Flexibility     | Can process variable-length input sequences     | Training can be slow                          |
| Architecture    | More expressive than ANNs for time-series data  | Hard to train on long sequences               |
| Applications    | Effective in language modeling, translation     | Sensitive to input noise                      |

## Common Use Cases
- Language modeling and text generation
- Speech recognition
- Time-series forecasting
- Machine translation
- Music composition
