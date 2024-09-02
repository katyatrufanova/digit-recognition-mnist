# Digit Recognition Report

## Problem Statement

The objective of this exercise is to classify a set of unknown digits (the test set) given a set of manually classified digits (the training set). The approach involves selecting an orthogonal basis with k dimensions and projecting the data into this subspace. The number of dimensions (k) is determined by selecting the optimal number of principal components to retain, maximizing the retained variance under projection.

## Methodology

### Vector Space Representation

Hand-written digit images are considered as vectors (or points) in a vector space. The assumption is that images of a certain digit will form a cluster of points in this space. If these clusters are well-separated, an unknown digit can be classified by determining which cluster it belongs to.

### Classification Process

1. Compute the distance (2-norm) between the projection of an unknown digit and the means of the projections of known digits.
2. Select the smallest norm to determine the classification.

### Singular Value Decomposition (SVD)

The variation within each digit class is modeled using k orthogonal basis vectors computed with SVD. The left-hand singular vectors (columns of U) form an orthogonal basis representing the dominant directions of the data matrix.

## Implementation

1. **Data Preparation**:
   - Compute the mean image of training images.
   - Subtract the mean from all training images.
   - Center the resulting matrix.

2. **SVD**:
   Perform Singular Value Decomposition on the centered matrix.

3. **Principal Component Selection**:
   The number of principal components to retain was determined using various techniques:
   - Scree plot
   - Cumulative percentage of total variation
   - Kaiser rule
   - Entropy
   - Approximation (Eckhart-Young theorem)

  Results:
   - Minimal value of k to retain 80% entropy: 62
   - Lowest value (used): 22 (from cumulative percentage of total variation criterion)

4. **Dictionary Computation**:
   - Dictionary of training digits
   - Dictionary of digit projections in the selected k-dimensional subspace
   - Dictionary of digit classes

5. **Classification**:
   Perform classification of test digits.

6. **Evaluation**:
   Compute confusion matrix and classification report.

## Results

### Confusion Matrix

![confusion_matrix](https://github.com/user-attachments/assets/9237c4ae-0b49-4d15-abfb-e299a73011a4)

The confusion matrix visualizes the accuracy of the classification. Each element Cij represents the number of observations known to be in group i and predicted to be in group j. Three test digits out of ten were classified incorrectly, while the remaining were classified correctly.

## Observations

1. Digits 3, 6, and 8 are missing from the confusion matrix and classification report, as they are not present in the test set.
2. The overall performance of the classification algorithm was relatively low.

## Conclusion

This implementation demonstrates the process of digit recognition using dimensionality reduction and classification techniques. While the current performance is modest, there is potential for improvement through further refinement of the method and expansion of the dataset.
