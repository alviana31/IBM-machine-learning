# KNN Decision Boundary

## 1. Definition

A decision boundary is a line or region that separates different predicted classes in a classification model.

In KNN, the decision boundary is determined by the distribution of training data points and the selected value of K.

## 2. How KNN Creates Decision Boundaries

KNN determines the class of a new observation by examining its nearest neighbors.

The predicted class depends on the majority class among those neighbors.

As a result, different regions of the feature space can be assigned to different classes.

The boundary between those regions is called the decision boundary.

## 3. Effect of the K Value

The selected K value affects the shape of the decision boundary.

### Small K

- Considers fewer neighbors.
- Can produce more detailed and irregular boundaries.
- Is more sensitive to noise and individual observations.

### Large K

- Considers more neighbors.
- Generally produces smoother boundaries.
- May overlook local patterns when the value is too large.

## 4. Example

Suppose a dataset contains two classes:

- Class A
- Class B

When a new observation is placed in the feature space, KNN examines its nearest neighbors and assigns the majority class.

The decision boundary separates the regions where the model predicts Class A from the regions where it predicts Class B.

## 5. Key Takeaways

- A decision boundary separates predicted classes.
- KNN creates decision boundaries based on nearby observations.
- The K value affects the shape and complexity of the boundary.
- Choosing K is important for balancing sensitivity to local patterns and smoother predictions.