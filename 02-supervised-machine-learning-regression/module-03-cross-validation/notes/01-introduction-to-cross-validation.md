# Introduction to Cross Validation

## 1. What is Cross Validation?

Cross-validation is a model evaluation technique that uses multiple training and validation splits to assess how well a machine learning model performs.

In a basic train-test split, the dataset is divided into training data and test data only once.

Cross-validation repeats the process using different subsets of the available data. The model is trained and evaluated several times, and the resulting performance scores are compared or averaged.

## 2. Why Use Cross Validation?

A single train-test split may produce an evaluation result that depends heavily on which observations were selected for the test set.

A model might perform well on one particular split but produce different results on another split.

Cross-validation helps address this limitation by evaluating the model across multiple splits.

Benefits include:

- Provides multiple performance measurements.
- Reduces dependence on a single data split.
- Helps compare different models.
- Gives a broader indication of how well a model may generalize to unseen data.

Cross-validation requires additional computation because the model must be trained and evaluated multiple times.

## 3. Training, Validation, and Test Data

These three datasets have different purposes.

### Training Data

Training data is used to fit the model and learn its parameters.

### Validation Data

Validation data is used during model development to compare models and make decisions about model settings.

In cross-validation, different portions of the available dataset are used as validation data across repeated splits.

### Test Data

Test data is generally kept separate until the modeling process is complete.

It is used for the final evaluation of the selected model.

## 4. Cross-Validation Workflow

A general cross-validation process follows these steps:

1. Start with the available historical dataset.
2. Divide the data into multiple training and validation combinations.
3. Train the model using the training portion of each split.
4. Evaluate the model using the corresponding validation portion.
5. Record the performance score for each split.
6. Compare or average the scores to assess model performance.

Each validation split should be kept separate from the training portion used in that particular iteration.

## 5. Single Split vs. Cross Validation

| Aspect | Train-Test Split | Cross Validation |
|---|---|---|
| Number of evaluations | One split | Multiple splits |
| Training process | Usually once | Repeated |
| Evaluation data | One test set | Different validation subsets |
| Computation | Lower | Higher |
| Performance assessment | Depends on one split | Based on multiple splits |

## 6. Important Considerations

- Cross-validation takes more time than a single train-test split.
- The model is trained separately for each split.
- Validation scores can vary between splits.
- Averaging scores provides a summary of performance across the selected splits.
- A final test dataset can still be reserved for evaluating the selected model.

## Key Takeaway

Cross-validation provides a more comprehensive evaluation by measuring model performance across multiple training and validation splits. It helps reduce the risk of relying on an unusually favorable or unfavorable single split.