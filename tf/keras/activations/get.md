<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.activations.get" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.activations.get

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/activations.py">View source</a>



Returns function.

``` python
tf.keras.activations.get(identifier)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`identifier`</b>: Function or string


#### Returns:

Activation function denoted by input:
- `Linear activation function` if input is `None`.
- Function corresponding to the input string or input function.



#### For example:



```
>>> tf.keras.activations.get('softmax')
 <function softmax at 0x1222a3d90>
>>> tf.keras.activations.get(tf.keras.activations.softmax)
 <function softmax at 0x1222a3d90>
>>> tf.keras.activations.get(None)
 <function linear at 0x1239596a8>
>>> tf.keras.activations.get(abs)
 <built-in function abs>
>>> tf.keras.activations.get('abcd')
Traceback (most recent call last):
...
ValueError: Unknown activation function:abcd
```

#### Raises:


* <b>`ValueError`</b>: Input is an unknown function or string, i.e., the input does
not denote any defined function.

## Compat aliases

* `tf.compat.v1.keras.activations.get`
* `tf.compat.v2.keras.activations.get`

