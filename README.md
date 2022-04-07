# Charity_Funding_Predictor


## Sequential model
 
<p> Before talking about the sequential model and what it does. In the following code, tf stands for TensorFlow and is a free popular machine learning framework. Tensor is a term used for a multidimensional array of vectors, numbers, and matrixes. Then flows is a term for how the data flows through tensors. TensorFlow is a library used in Python. TensorFlow is made for enormous datasets and will not work for small datasets.  </p>

<p>Keras is another python open-source library that runs on TensorFlow. Again, like TensorFlow, it cannot run with small datasets. Keras features support multi-platforms allowing all encoders, to build any architecture, unique, and solid foundations of the development community. Some of the advantages of using Keras is processes large datasets quickly, supports many libraries like TensorFlow and is easier to understand. The data structure of Keras is made up of layers and models. One of the types of models used is the Sequential model. </p>

Code in program used is tf.keras.Sequential(layers=None, name=None)

#### What is the Sequential model and what does it do to the data?
<p>The Sequential model is not always appropriate to use. Only if the model has multiple inputs or outputs, layers have numerous inputs or considerable outputs and need to do layer sharing. A sequential model is a linear stack of layers. </p>


## Cleaning and Training data

<p> Before applying the Sequential model, the data must be trained and prepared or the model will not have sufficient accuracy. If someone wants to use machine learning, the data does not need all non-numeric columns. For this case, the data frame has seven-string columns and some should drop. How do you know which columns to drop, you ask? Typically machine learning data does not include the number id, name, or data not repeating the text itself.  </p>

![Columns Dropped](https://github.com/samuelroiz/Charity_Funding_Predictor/blob/main/Images/cleaning_data_part_1.png)

<p>Sometimes dropping columns is not always the case. You can group some of the text strings to avoid dropping useful information. The following image is a great example. It has lots of data on application type, but some of the data are too small. The small values are T9, T13, T12, T2, T14, T25, T29, T15, and T17, and convert these data into a category named other. If the data is smaller than the rest, training its model will affect the outcome and leave outliers in the data. Converting and grouping the small values into others is an acceptable method to avoid outliers.  </p>

![Outliers in Column Find](https://github.com/samuelroiz/Charity_Funding_Predictor/blob/main/Images/cleaning_data_part_1.png)

