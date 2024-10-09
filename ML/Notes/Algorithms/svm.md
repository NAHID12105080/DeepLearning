# Support Vector Machine (SVM)

## Overview
Support Vector Machine (SVM) is a supervised machine learning algorithm used for classification and regression tasks. It works by finding the optimal hyperplane that best separates different classes in the data.

## Key Concepts

- **Hyperplane**: A decision boundary that separates different classes. In a 2D space, it's a line; in 3D, it's a plane; and in higher dimensions, it's a hyperplane.
- **Support Vectors**: Data points closest to the hyperplane that influence the position and orientation of the hyperplane.
- **Margin**: The distance between the hyperplane and the nearest support vector. SVM aims to maximize this margin.
- **Kernel Trick**: SVM can use kernel functions to map input data into higher dimensions, making it easier to find a separating hyperplane for non-linearly separable data.

## Types of SVM
- **Linear SVM**: Used when the data is linearly separable.
- **Non-Linear SVM**: Uses kernel functions (like RBF, polynomial, sigmoid) to handle non-linearly separable data.

## Kernel Functions
- **Linear Kernel**: For linearly separable data.
- **Polynomial Kernel**: Adds polynomial terms to make non-linearly separable data separable.
- **Radial Basis Function (RBF) Kernel**: A popular kernel used to transform data into a higher dimension for better separation.
- **Sigmoid Kernel**: Used to transform data similar to a neural network.

## Advantages
- Effective in high-dimensional spaces.
- Works well when there is a clear margin of separation between classes.
- Memory efficient, as it uses only a subset of training points (support vectors).

## Disadvantages
- Not suitable for large datasets as training time increases with dataset size.
- Inefficient when the data is noisy or classes are overlapping.
- Choosing the right kernel and tuning hyperparameters (like C, gamma) can be complex.

## Real-world Application
- **Image Classification**: Classifying images based on objects detected.
- **Text Classification**: Sorting emails into spam or non-spam categories.
- **Medical Diagnosis**: Predicting diseases based on patient data.

## Example
```python
from sklearn import svm
# Create a linear SVM classifier
classifier = svm.SVC(kernel='linear')
# Train on dataset
classifier.fit(X_train, y_train)
# Predict on new data
predictions = classifier.predict(X_test)
```
