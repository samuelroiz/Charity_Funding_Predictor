# Charity_Funding_Predictor


## Sequential model
 
<p> Before talking about the sequential model and what it does. In the following code, tf stands for TensorFlow and is a free popular machine learning framework. Tensor is a term used for a multidimensional array of vectors, numbers, and matrixes. Then flows is a term for how the data flows through tensors. TensorFlow is a library used in Python. TensorFlow is made for enormous datasets and will not work for small datasets.  </p>

<p>Keras is another python open-source library that runs on TensorFlow. Again, like TensorFlow, it cannot run with small datasets. Keras features support multi-platforms allowing all encoders, to build any architecture, unique, and solid foundations of the development community. Some of the advantages of using Keras is processes large datasets quickly, supports many libraries like TensorFlow and is easier to understand. The data structure of Keras is made up of layers and models. One of the types of models used is the Sequential model. </p>

Code in program used is tf.keras.Sequential(layers=None, name=None)

#### What is the Sequential model and what does it do to the data?
<p>The Sequential model is not always appropriate to use. Only if the model has multiple inputs or outputs, layers have numerous inputs or considerable outputs and need to do layer sharing. A sequential model is a linear stack of layers. </p>