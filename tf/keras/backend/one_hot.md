<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.one_hot" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.one_hot

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/backend.py">View source</a>



Computes the one-hot representation of an integer tensor.

``` python
tf.keras.backend.one_hot(
    indices,
    num_classes
)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`indices`</b>: nD integer tensor of shape
    `(batch_size, dim1, dim2, ... dim(n-1))`
* <b>`num_classes`</b>: Integer, number of classes to consider.


#### Returns:

(n + 1)D one hot representation of the input
with shape `(batch_size, dim1, dim2, ... dim(n-1), num_classes)`



#### Returns:

The one-hot tensor.


## Compat aliases

* `tf.compat.v1.keras.backend.one_hot`
* `tf.compat.v2.keras.backend.one_hot`

