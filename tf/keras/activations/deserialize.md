<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.activations.deserialize" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.activations.deserialize

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/activations.py">View source</a>



Returns activation function denoted by input string.

``` python
tf.keras.activations.deserialize(
    name,
    custom_objects=None
)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`x`</b>: String


#### Returns:

TensorFlow Activation function denoted by input string.



#### For example:


>>> tf.keras.activations.deserialize('linear')
 <function linear at 0x1239596a8>
>>> tf.keras.activations.deserialize('sigmoid')
 <function sigmoid at 0x123959510>
>>> tf.keras.activations.deserialize('abcd')
Traceback (most recent call last):
...
ValueError: Unknown activation function:abcd

#### Args:


* <b>`name`</b>: The name of the activation function.
* <b>`custom_objects`</b>: A {name:value} dictionary for activations not build into
  keras.


#### Raises:


* <b>`ValueError`</b>: `Unknown activation function` if the input string does not
denote any defined Tensorflow activation function.

## Compat aliases

* `tf.compat.v1.keras.activations.deserialize`
* `tf.compat.v2.keras.activations.deserialize`

