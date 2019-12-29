<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.datasets.cifar100.load_data" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.datasets.cifar100.load_data

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/datasets/cifar100.py">View source</a>



Loads CIFAR100 dataset.

``` python
tf.keras.datasets.cifar100.load_data(label_mode='fine')
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`label_mode`</b>: one of "fine", "coarse".


#### Returns:

Tuple of Numpy arrays: `(x_train, y_train), (x_test, y_test)`.



#### Raises:


* <b>`ValueError`</b>: in case of invalid `label_mode`.

## Compat aliases

* `tf.compat.v1.keras.datasets.cifar100.load_data`
* `tf.compat.v2.keras.datasets.cifar100.load_data`

