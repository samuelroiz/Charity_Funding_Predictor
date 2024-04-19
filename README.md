---
# Charity_Funding_Predictor

## Sequential Model

Before discussing the sequential model and its functionality, it's essential to clarify some foundational concepts. In the following context, `tf` stands for TensorFlow, which is a popular, free machine learning framework. A tensor is a term used for multidimensional arrays that include vectors, numbers, and matrices. The term "flows" indicates how data flows through these tensors. TensorFlow, primarily a Python library, is designed for handling large datasets and is not suitable for small ones.

Keras, another Python open-source library, operates on TensorFlow. Like TensorFlow, Keras is not intended for small datasets. It features support for multiple platforms, enabling developers to build any architecture. Advantages of using Keras include its ability to process large datasets quickly, compatibility with many libraries like TensorFlow, and its user-friendly design. The data structure in Keras consists of layers and models, one of which is the Sequential model.

The code in the program used is: 

```python
tf.keras.Sequential(layers=None, name=None)
```

#### What is the Sequential Model and What Does It Do to the Data?

The Sequential model is a linear stack of layers. It is only appropriate if the model does not have multiple inputs or outputs, if layers do not have multiple inputs or outputs, and if there is no need for layer sharing.

## Modify and Train Data

Before applying the Sequential model, the data must be trained and prepared, or the model will not achieve sufficient accuracy. Machine learning models do not require all non-numeric columns. For this case, the dataframe has seven string columns, some of which should be dropped. Typically, machine learning data does not include columns like number IDs, names, or non-repetitive text.

![Columns Dropped](https://github.com/samuelroiz/Charity_Funding_Predictor/blob/main/Images/cleaning_data_part_1.png)

Sometimes, dropping columns is not necessary. You can group some of the text strings to avoid discarding useful information. The following image is a great example. It has extensive data on application type, but some of the data categories are too small. These small values are T9, T13, T12, T2, T14, T25, T29, T15, and T17, which are converted into a category named "other" to avoid outliers.

![Outliers in Column Find](https://github.com/samuelroiz/Charity_Funding_Predictor/blob/main/Images/cleaning_data_part_2.png)

This method avoids discarding valuable data and reduces outliers. The first code snippet runs a for loop to collect data that is an outlier due to a small number. Once appended to a list, the list replaces the values in the dataframe with "other". This method is also used for other columns. Additionally, columns can be filtered to exclude zeros and null values.

![Outliers Replaced in Column](https://github.com/samuelroiz/Charity_Funding_Predictor/blob/main/Images/cleaning_data_part_3.png)

Finally, the dataframe is ready for machine learning. It has been cleaned and modified to work effectively with machine learning models. The original dataframe had 34,299 rows and 12 columns, but with more varied values in each column. The revised dataframe with ten columns has fewer outliers and is easier to model.

![Data frame to model with](https://github.com/samuelroiz/Charity_Funding_Predictor/blob/main/Images/cleaning_data_part_3.png)

### Get_dummies() Section

#### Example

Here is an example of how `pd.get_dummies()` works:

![Get_Dummies() Part 1](https://github.com/samuelroiz/Predict_Credit_Risk/blob/main/Images/example_get_dummies_part_1.png)

The following dataframe named `preview_get_dummies` displays two non-numeric columns. Then apply the `get_dummies()` code:

```python
pd.get_dummies(preview_get_dummies)
```

![Get_Dummies() Part 2](https://github.com/samuelroiz/Predict_Credit_Risk/blob/main/Images/example_get_dummies_part_2.png)

Now, the `preview_get_dummies` dataframe has numeric columns, which means it meets the standards of machine learning models.

### Get Dummies Outcome

Applying the `get_dummies()` code to the dataframe results in a shape of 34,299 rows and 44 columns.

![Get Dummies Outcome](https://github.com/samuelroiz/Charity_Funding_Predictor/blob/main/Images/get_dummies_data_part_1.png)

### Train and Test Data

#### How Does Train and Test Work and What Is It Doing to the Data?

Training data helps with model prediction and develops an algorithm using 70% or more of the data. Large datasets typically use

 this training method to achieve the best results. Testing helps check the model's prediction rate by taking a small portion of the data and evaluating whether the model functions efficiently.

### Standard Scaler Section

#### How Does the Standard Scaler Work and What Is It Doing to the Data?

The Standard Scaler follows the formula:

```plaintext
z = (x - u) / s
```

where `z` is the scaled data, `x` is the data to be scaled, `u` is the average of the training samples, and `s` is the standard deviation of the training samples. The average or mean is the sum of all data points divided by the number of data points. The standard deviation formula starts by taking the given values and placing them in one column, squaring each value, and placing them in a second column. Find the sum of all values in the first column and square it. The value is divided by the number of data points in the first column and called this number `i`. Find the sum of all values in the created second column. Once you find the value, subtract it by `i`. The outcome will be divided by the number of data points minus one. This value leads to the `variance` of the sample and data. Finally, the variance will be square-rooted, leading to the standard deviation of the data.

#### Example of Standard Scaler

To demonstrate the algorithm and how it functions, consider the dataset `{1,2,3,4,5}`. The dataset consists of 5 one-dimensional data points, and each data point has one feature. Now apply the standard scaler() to the data. The dataset becomes `{-1.41, -0.71, 0, 0.71, 1.41}`.

The following example takes all of the data points and converts them to a closer range of 0 to 1. Standard scaler helps prevent outliers and keep the data closer to each other rather than gaps.

### Standard Scaler Outcome

Apply the standard scaler code to the dummies' data frame to demonstrate the algorithm and drive the data closer to each other.

![Standard Scaler X Values](https://github.com/samuelroiz/Charity_Funding_Predictor/blob/main/Images/standard_scaler_data_part_1.png)

## Contributing

Please read [CONTRIBUTING.md](https://gist.github.com/samuelroiz/1af49ec9eea365bc845ba04c5071a976) for details on our code of conduct, and the process for submitting pull requests to us.

## Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available, see the [tags on this repository](https://github.com/your/project/tags).

## Authors

* **Samuel Roiz** - *Data clean, Analyzed Data, SQL* - [Profile](https://github.com/samuelroiz)

See also the list of [contributors](https://github.com/samuelroiz) who participated in this project.

## License

This project is licensed under the MIT License - see the [LICENSE.md](https://gist.github.com/samuelroiz/1af49ec9eea365bc845ba04c5071a976) file for details

## Acknowledgments

* Charity Funding
* Non-profit foundation Alphabet Soup
* USC Data Visualization
* CSUN Mathematics
