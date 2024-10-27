# Self-Attention in Transformer Architecture

## 1. What is Self-Attention?
   - **Definition**: Self-Attention allows each token in a sequence to focus on other tokens to understand contextual relationships.
   - **Purpose**: Captures dependencies regardless of distance between tokens.
   - **Use Case**: Vital for tasks like language translation, text generation, etc.
![image](https://github.com/user-attachments/assets/44d08c97-771f-4a9e-b7e4-117303758883)

## 2. Key Concepts
   - **Query (Q)**, **Key (K)**, **Value (V)**:
     - **Q**: Represents the current token seeking relevant information.
     - **K**: Represents other tokens to be attended to.
     - **V**: Holds the actual information associated with each token.
   - **Attention Score Calculation**:
     - Formula: `Attention(Q, K) = softmax((Q * K^T) / sqrt(d_k)) * V`
     - **d_k**: Dimension of the keys (scaling factor).
   - **Softmax**: Converts scores into probabilities.

## 3. Steps in Self-Attention
   1. **Linear Transformation**: Convert input token embeddings to Q, K, and V.
   2. **Compute Attention Scores**: Measure similarity between Q and K.
   3. **Apply Softmax**: Normalize scores into probabilities.
   4. **Weighted Sum of Values**: Multiply scores by V to produce the output.

## 4. Multi-Head Attention
   - **Multiple Heads**: Perform self-attention multiple times in parallel.
   - **Why Use Multiple Heads?**: Helps model different aspects of relationships.
   - **Concatenation and Linear Transformation**: Merge outputs of all heads.

## 5. Benefits of Self-Attention
   - **Parallelism**: Computation is independent of token position.
   - **Long-range Dependencies**: Effectively captures relationships across distant tokens.
   - **Scalability**: Easily scaled to large datasets.

## 6. Position Encoding
   - **Why Needed?**: Self-attention itself does not consider the order of tokens.
   - **Solution**: Positional encodings are added to the input embeddings.
   - **Types**: Sine and cosine functions encode token positions.

## 7. Common Applications
   - **NLP**: Text generation, translation, summarization.
   - **Computer Vision**: Image recognition, segmentation (Vision Transformers).

## 8. Key Formulas
