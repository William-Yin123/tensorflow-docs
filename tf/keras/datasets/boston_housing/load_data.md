<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.datasets.boston_housing.load_data" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.datasets.boston_housing.load_data

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/datasets/boston_housing.py">View source</a>



Loads the Boston Housing dataset.

``` python
tf.keras.datasets.boston_housing.load_data(
    path='boston_housing.npz',
    test_split=0.2,
    seed=113
)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`path`</b>: path where to cache the dataset locally
    (relative to ~/.keras/datasets).
* <b>`test_split`</b>: fraction of the data to reserve as test set.
* <b>`seed`</b>: Random seed for shuffling the data
    before computing the test split.


#### Returns:

Tuple of Numpy arrays: `(x_train, y_train), (x_test, y_test)`.


## Compat aliases

* `tf.compat.v1.keras.datasets.boston_housing.load_data`
* `tf.compat.v2.keras.datasets.boston_housing.load_data`

