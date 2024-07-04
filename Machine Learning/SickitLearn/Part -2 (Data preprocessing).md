- - -
In machine learning, transformers are a type of estimator that is primarily used for data preprocessing and feature engineering. Unlike traditional estimators, transformers do not make predictions. Instead, they focus on transforming input data into a format that is suitable for machine learning algorithms.

Here are some key points about transformers in machine learning:

1. **Data Preprocessing**: Transformers are commonly used for preprocessing raw input data before it is fed into a machine learning model. This preprocessing step is essential for cleaning, normalizing, and transforming the data into a format that can be effectively used by the learning algorithm.
    
2. **Feature Engineering**: Transformers are also used for feature engineering, which involves creating new features or modifying existing ones to improve the performance of the machine learning model. Feature engineering can include tasks such as encoding categorical variables, scaling numerical features, and creating interaction terms.
    
3. **Fit and Transform Methods**: Similar to estimators, transformers in scikit-learn implement a `fit` method, which learns parameters from the training data, and a `transform` method, which applies the learned transformations to new data. Some transformers also implement a `fit_transform` method, which combines the `fit` and `transform` steps into a single operation for convenience.
    
4. **Examples of Transformers**:
    
    - `StandardScaler`: A transformer that standardizes features by removing the mean and scaling to unit variance.
    - `MinMaxScaler`: A transformer that scales features to a specified range, typically between 0 and 1.
    - `OneHotEncoder`: A transformer that converts categorical variables into a binary matrix representation (one-hot encoding).
    - `PCA (Principal Component Analysis)`: A transformer that performs dimensionality reduction by projecting data onto a lower-dimensional subspace.
    - `PolynomialFeatures`: A transformer that generates polynomial features up to a specified degree.
5. **Pipeline Compatibility**: Transformers are often used in conjunction with other transformers and estimators in scikit-learn's `Pipeline` objects. Pipelines allow you to chain together multiple preprocessing steps and a final estimator into a single object, making it easier to streamline the machine learning workflow.

- - -

![[Pasted image 20240309081732.png|700]]
- We can see that there is a small group of outliers on the extreme diagonal sides.
- Also , the x-axis and the y-axis are in completely different scale . So, we have to scale it.
### Rather than using Standard Scalar we will use

![[Pasted image 20240309122240.png|700]]
Using Quantiles we can see that the distance from the OUTLIERS to the 75th Quantile is a lot smaller. That is the distance between the normal values and the OUTLIERS have become smaller.

After applying Quantile Transformer.
So, the outliers have a less of a profound effect on the datasets.
![[Pasted image 20240309123838.png|700]]
