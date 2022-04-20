# Charity_Funding_Predictor


## Sequential model
 
<p> Before talking about the sequential model and what it does. In the following code, tf stands for TensorFlow and is a free popular machine learning framework. Tensor is a term used for a multidimensional array of vectors, numbers, and matrixes. Then flows is a term for how the data flows through tensors. TensorFlow is a library used in Python. TensorFlow is made for enormous datasets and will not work for small datasets.  </p>

<p>Keras is another python open-source library that runs on TensorFlow. Again, like TensorFlow, it cannot run with small datasets. Keras features support multi-platforms allowing all encoders, to build any architecture, unique, and solid foundations of the development community. Some of the advantages of using Keras is processes large datasets quickly, supports many libraries like TensorFlow and is easier to understand. The data structure of Keras is made up of layers and models. One of the types of models used is the Sequential model. </p>

Code in program used is tf.keras.Sequential(layers=None, name=None)

#### What is the Sequential model and what does it do to the data?
<p>The Sequential model is not always appropriate to use. Only if the model has multiple inputs or outputs, layers have numerous inputs or considerable outputs and need to do layer sharing. A sequential model is a linear stack of layers. </p>


## Modify and Training data

<p> Before applying the Sequential model, the data must be trained and prepared or the model will not have sufficient accuracy. If someone wants to use machine learning, the data does not need all non-numeric columns. For this case, the data frame has seven-string columns and some should drop. How do you know which columns to drop, you ask? Typically machine learning data does not include the number id, name, or data not repeating the text itself.  </p>

![Columns Dropped](https://github.com/samuelroiz/Charity_Funding_Predictor/blob/main/Images/cleaning_data_part_1.png)

<p>Sometimes dropping columns is not always the case. You can group some of the text strings to avoid dropping useful information. The following image is a great example. It has lots of data on application type, but some of the data are too small. The small values are T9, T13, T12, T2, T14, T25, T29, T15, and T17, and convert these data into a category named other. If the data is smaller than the rest, training its model will affect the outcome and leave outliers in the data. Converting and grouping the small values into others is an acceptable method to avoid outliers.  </p>

![Outliers in Column Find](https://github.com/samuelroiz/Charity_Funding_Predictor/blob/main/Images/cleaning_data_part_2.png)

<p> The method avoids throwing valuable data away and reducing outliers. The first code is an example and a method used. It runs a for loop to collect data that marks an outlier due to a small number. Once appended to a list, the list will be replaced with the data frame in the second code to replace the values with others. Code is used for other columns also. You can also filter the column to greater than one if a column has some zero and null values.  </p>

![Outliers Replaced in Column](https://github.com/samuelroiz/Charity_Funding_Predictor/blob/main/Images/cleaning_data_part_3.png)

<p>Finally, the data frame is ready to go for machine learning. The data frame is already cleaned up and modified to work with machine learning. The data frame has thirty-four thousand two-hundred ninety-nine rows and ten columns. The original data frame had thirty-four thousand two-hundred ninety-nine rows and twelve columns, but with more different values in each column. The big difference between the two data frames is the data frame with ten columns has fewer outliers and is easier to model. The data frame with twelve columns has important specific data but cannot be used to train and model due to outliers and unique values.  </p>

![Data frame to model with](https://github.com/samuelroiz/Charity_Funding_Predictor/blob/main/Images/cleaning_data_part_3.png)

### Get_dummies() Section

#### Example.

<p>
Here is an example of how pd.get_dummies() work.
</p> 

![Get_Dummies() Part 1](https://github.com/samuelroiz/Predict_Credit_Risk/blob/main/Images/example_get_dummies_part_1.png) <p> The following data frame is named <i> preview_get_dummies </i> displays two non-numeric columns. </p>

<p>
  Then apply the get_dummies() code: <b> pd.get_dummies(<i> preview_get_dummies </i>) </b>
</p>

![Get_Dummies() Part 2](https://github.com/samuelroiz/Predict_Credit_Risk/blob/main/Images/example_get_dummies_part_2.png)

<p>
Now the <i> preview_get_dummies </i> data frame has numeric columns which means it meets the standards of machine learning models.
</p>

### Get Dummies Outcome
<p>
Apply the get_dummies() code to the data frame and the data frame ends up having a shape of thirty-four thousand two-hundred ninety-nine rows and forty-four columns.
</p>

![Get Dummies Outcome](https://github.com/samuelroiz/Charity_Funding_Predictor/blob/main/Images/get_dummies_data_part_1.png)

### Train and Test Data

#### How does train and test work and what is it doing to the data?

### Standard Scaler Section

#### How does the Standard scaler work and what is it doing to the data? 

<p> Standard Scaler has a formula, let's assume the formula is <b> z = (x - u) / s </b> where <b> z </b> is the scaled data, <b> x </b> is to be the scaled data, <b> u </b> is the average of the training samples, and <b> s </b> is the standard deviation of the training samples. The average or mean is the sum of all data points divided by the number of data points. In this case, <b> u </b> is going to add up all of the training samples divided by several training samples. The standard deviation formula starts by taking the given values and placing them in one column. Square each value and place them in a second column. Find the sum of all values in the first column and square it. The value is divided by the number of data points in first the column and called this number <b> i </b>. Find the sum of all values in the created second column. Once find the value, subtract it by <b> i </b>. The outcome will be divided by the number of data points minus one. Value leads to the <b> variance </b> of the sample and data. Finally, the variance will be square rooted leading to the value standard deviation of the data. 
</p>

#### Example of Standard Scaler
<p>
To demonstrate the algorithm and how it functions, consider the data set {1,2,3,4,5}. The data set consists of 5 one dimensional data points and each data point has one feature. Now apply the standard scaler() to the data. The data set becomes {−1.41,−0.71,0.,0.71,1.41}.
</p>

<p>
  The following example takes all of the data points and converts them to a closer range of 0 to 1. Standard scaler helps prevent outliers and keep the data closer to each other rather than gaps. 
  </p>

### Standard Scaler Outcome 

<p>
 Apply the standard scaler code to the dummies' data frame to demonstrate the algorithm and drive the data closer to each other. 
</p>

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
* non-profit foundation Alphabet Soup
* USC Data Visualization
* CSUN Mathematics
